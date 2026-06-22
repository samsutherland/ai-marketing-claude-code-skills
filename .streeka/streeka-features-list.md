Based on my thorough exploration of the workspace, here is an exhaustive feature list organized by domain area:

---

# 📱 **STREEKA WORKSPACE — EXHAUSTIVE FEATURE LIST**

## **PART 1: STREEKA FLUTTER MOBILE APP**

### **🏠 Home & Core Experience**

- **Home Dashboard** — Main entry point showing user greeting, navigation to all features, access to streak tracking
- **Welcome Screen** — Initial onboarding introduction to the app experience
- **Streeka Login Screen** — Native authentication UI with Entra ID (MSAL) integration
- **Bottom Navigation** — Multi-tab UI structure routing to Home, Planner, Insights, Chat, Account
- **Drawer Menu** — Side menu for app navigation and account access
- **Onboarding Explainer Screen** — Feature walkthroughs and educational content for new users

### **🔐 Authentication & Account Management**

- **Native Auth Service** (`auth_service.dart`) — Handles token acquisition, validation, and refresh via MSAL CIAM
- **Auth Interceptor** — Automatically injects auth tokens into all API requests
- **Auth Token Store** (`auth_token_store.dart`) — Secure persistent storage of JWT tokens
- **User Settings Screen** — Edit profile, preferences, and personal settings
- **Account Settings Screen** — Manage account-level configuration, integrations
- **Account Deletion** — Full user deletion workflow with status tracking
- **Unit Preferences Cubit** — Toggle metric system (imperial/metric) with persistent storage

### **📅 Planner (AI-Driven Workout Planning)**

- **Overall Plan Generation** — Long-term training goal and plan creation using Azure OpenAI
- **Overall Plan Viewing** — Display structured multi-week training plans with weekly summaries
- **Weekly Plan Generation** — Auto-generation of weekly workouts based on athlete availability and goals
- **Weekly Plan Management** — View, edit, and customize weekly workout schedules
- **Activity Feedback Dialog** — Capture post-workout RPE, difficulty, mood, and notes
- **Day Availability Selection** — Athletes specify available training days/times
- **Question-Based Onboarding** — Dynamic questionnaires for goal setting (MCQ, datepicker, checkbox, distance input)
- **Goal Summary Display** — Show athlete goals with structured details (duration, focus, target metrics)
- **Ride DNA Section** — Visualize athlete's characteristic power output patterns and workout preferences
- **Workout Structure Visualization** — Display workout phases (warmup, main, cooldown) with intensity zones
- **Workout Intensity Chart** — Zone-based power/HR distribution graph for each workout
- **Elite Stats Card** — Display cyclist FTP estimates and benchmark comparisons
- **Ride Energy Fingerprint** — Visual representation of typical energy expenditure patterns
- **Plan Persistence** — Local Hive cache with Stale-While-Revalidate pattern for offline access

### **💡 Insights & Analytics**

- **Weekly Summary** — Aggregated performance metrics for the selected week
- **Daily Load Chart** — Cumulative training stress distribution over time
- **Fitness Trend** — Long-term fitness trajectory visualization (CTL, ATL, TSS)
- **Flow Field Visualization** — Visual representation of power-duration relationship and athlete efficiency envelope
- **Personality Profile** — AI-derived coach personality label (e.g., "Consistency Specialist", "Intensity Hunter") based on historical patterns
- **Power Insights** — FTP estimates, power zones, and power balance analysis
- **Efficiency Factor Insights** — Normalized power vs. actual power comparison (workout economy)
- **Personality Compass Card** — Multi-dimensional athlete profile visualization
- **Power Sparklines** — Quick mini-charts for power trends
- **Efficiency Sparklines** — Quick mini-charts for efficiency trends
- **Insights Sharing** — Export and share insight summaries via social media or messaging
- **Insights Repository** — Stale-While-Revalidate caching of all analytics data with TTL ~30-60 min

### **🤖 Chat with SAMI (AI Coach Assistant)**

- **Chat Interface** — Real-time messaging with AI coach (SAMI)
- **SAMI Typing Indicator** — Visual feedback while AI is generating response
- **Chat History** — Full message history per user with context persistence
- **Question-Answering** — SAMI answers training, nutrition, recovery, and motivation questions
- **Plan Adjustment Suggestions** — SAMI proactively suggests plan modifications based on athlete feedback
- **Activity Commentary** — SAMI analyzes recent activities and provides feedback
- **Custom Chat Input** — Dark-themed input field optimized for mobile messaging
- **Message Serialization** — Support for images, links, and rich text formatting

### **📱 Wearable Integrations**

- **Wearable Connect Screen** — OAuth flow UI for connecting Garmin and Wahoo devices
- **Garmin OAuth Flow** — Complete Garmin Connect authorization with activity sync backfill
- **Wahoo OAuth Flow** — Wahoo Cloud authorization and activity sync
- **Manage Connections Screen** — View and disconnect linked wearable accounts
- **Automatic Activity Sync** — Background activity sync from wearables (Garmin, Wahoo)
- **Connection Status** — Display current provider connection health and sync status
- **Provider Selector** — UI to choose between Garmin, Wahoo, or manual entry
- **Activity Backfill** — Fetch historical activities on first connection

### **📊 Training Zones Management**

- **Training Zones Screen** — Display power zones and heart rate zones
- **Power Zones** — Display FTP-derived power zone thresholds (Z1-Z7)
- **Heart Rate Zones** — Display HR-based training zones with threshold calculations
- **Zones Cubit** — State management for zone data loading and updates

### **🎯 Goal Management**

- **Athlete Goals Repository** — Manage current and historical training goals
- **General Goal** — Broader fitness direction (e.g., "Build endurance")
- **Specific Goals** — Time-bound, measurable objectives (e.g., "Complete 50km gravel in 2h30m")
- **Goal History** — Archive ended goals with completion tracking
- **Goal Upsert** — Create or update goals with TTL caching

### **💳 Subscription & In-App Purchases**

- **Revenue Cat Paywall Screen** — Display subscription tiers and pricing
- **Revenue Cat Customer Center** — User-facing subscription management portal
- **In-App Purchase Integration** — Powered by RevenueCat (purchases_flutter plugin)
- **Subscription Status** — Check active subscription tier and entitlements

### **🛠️ Support & Utilities**

- **Support Feature Module** — Framework for in-app help and troubleshooting (in-progress)
- **Deep Linking** — App links support for OAuth callbacks and activity details
- **Share Functionality** — Export insights and achievements via system share dialog
- **Rate & Review** — Built-in feedback mechanism for app store reviews

### **📊 Analytics & Crash Reporting**

- **Analytics Service** — Mixpanel event tracking for user behavior
- **Crashlytics Service** — Firebase Crashlytics for error reporting and diagnostics
- **Event Tracking** — Screen views, button clicks, error events, plan generation progress
- **User Property Tracking** — Athlete demographics, wearable connections, subscription status

---

## **PART 2: STREEKA API (.NET AZURE FUNCTIONS)**

### **📋 Plans (Overall & Weekly)**

- **Trigger Overall Plan Generation** — `POST /api/user/{externalUserId}/plans/overall` — Enqueue async plan generation job; returns planId and pending status
- **Get Latest Overall Plan** — `GET /api/user/{externalUserId}/plans/overall/latest` — Fetch current completed overall plan with week-by-week breakdown
- **Process Overall Plan Job** — Queue-triggered background job; calls Azure OpenAI to generate multi-week training structure
- **Trigger Weekly Plan Generation** — `POST /api/user/{externalUserId}/plans/weekly` — Generate single week of workouts based on availability
- **Get Latest Weekly Plan** — `GET /api/user/{externalUserId}/plans/weekly/latest` — Fetch current week's scheduled workouts
- **Get Weekly Plans** — `GET /api/user/{externalUserId}/plans/weekly` — Paginated list of historical weekly plans
- **Update Weekly Plan** — `PUT /api/user/{externalUserId}/plans/weekly/{weekId}` — Replace entire weekly plan
- **Patch Weekly Plan** — `PATCH /api/user/{externalUserId}/plans/weekly/{weekId}` — Partial update (e.g., mark day as rest)
- **Process Weekly Plan Job** — Queue-triggered; generates AI-powered weekly workout schedule
- **Replace Weekly Workout** — `PUT /api/user/{externalUserId}/plans/weekly/{weekId}/workouts/{workoutId}` — Swap out single workout
- **Delete Weekly Workout** — `DELETE /api/user/{externalUserId}/plans/weekly/{weekId}/workouts/{workoutId}` — Remove workout from plan
- **Get Weekly Workout** — `GET /api/user/{externalUserId}/plans/weekly/{weekId}/workouts/{workoutId}` — Single workout details
- **Garmin Sync** — `ProcessGarminWeeklyPlanSyncJob` — Automatically push weekly plans to Garmin device
- **Provider Sync** — `ProcessProviderWeeklyPlanSyncJob` — Push plans to third-party training platforms

### **🎯 Goals (Athlete Training Objectives)**

- **Get Athlete Goals** — `GET /api/user/{externalUserId}/goal?isGeneral={bool}&includeHistory={bool}` — Fetch current or historical goals
- **Upsert Athlete Goal** — `PUT /api/user/{externalUserId}/goal` — Create or update goal (idempotent by IsGeneral flag)
- **Goal Models** — Supports general fitness direction goals and specific time-bound objectives
- **Goal History** — Track ended goals with completion metadata

### **🏃 Activities (Workout Recording & Sync)**

- **Get User Streaks** — `GET /api/streaks/user/{externalUserId}` — Fetch consistency streak counts
- **Get User Activities** — `GET /api/activities/user/{externalUserId}` — Paginated list of all user activities (auto-synced or manual)
- **Get My Activities** — `GET /api/activities/me` — Fetch authenticated user's activities
- **Delete My Activity** — `DELETE /api/activities/me/{activityId}` — Remove activity from user's history
- **Delete User Activity** — `DELETE /api/activities/user/{externalUserId}/{activityId}` — Admin-only activity deletion
- **Get My Activity Details** — `GET /api/activities/me/{activityId}` — Detailed activity data with laps, segments, efforts
- **Get My Activity Efforts** — `GET /api/activities/me/{activityId}/efforts` — Power/speed efforts detected in activity
- **Get User Activity Efforts** — `GET /api/activities/user/{externalUserId}/{activityId}/efforts` — Coach-accessible effort data
- **Wearable Activity Sync** — Automatic sync from Garmin, Wahoo
- **Manual Activity Import** — Allow manual entry of activities (type, duration, intensity)
- **Activity Calculations** — TSS, Normalized Power, Intensity Factor, VAM computations
- **Lap & Segment Data** — Support for lap-level metrics (HR, power, cadence averages)
- **Best Efforts** — Detect and store best 1min, 5min, 20min, 1hr power efforts per activity

### **💡 Insights (Performance Analytics)**

- **Get Fitness Trend** — `GET /api/insights/user/{externalUserId}/fitness-trend` — CTL, ATL, TSS progression over time
- **Get Daily Load** — `GET /api/insights/user/{externalUserId}/daily-load` — Daily training stress accumulation
- **Get Flow Field** — `GET /api/insights/user/{externalUserId}/flow-field` — Power-duration curve and efficiency envelope
- **Get Weekly Summary** — `GET /api/insights/user/{externalUserId}/weekly-summary` — Aggregate weekly metrics (TSS, VLaX, variability index)
- **Get Power Insights** — `GET /api/insights/user/{externalUserId}/power` — FTP estimate, power zones, power balance
- **Get Efficiency Factor Insights** — `GET /api/insights/user/{externalUserId}/efficiency` — Normalized power comparisons
- **Get Personality Profile** — `GET /api/insights/user/{externalUserId}/personality?sport=cycling` — AI-derived coach personality label
- **Insights Processors** — Background jobs (`InsightsDailyProcessor`, `PowerInsightsProcessor`, `UserInsightsProcessor`) compute/update metrics
- **TTL-Based Caching** — ~30-60 min cache for insights data with refresh on demand

### **📱 Users & Authentication**

- **Link User** — `POST /api/user/{externalUserId}/link` — Link Entra ID principal to app user account
- **Get User** — `GET /api/user/{externalUserId}` — Fetch user profile (name, email, timezone, connections)
- **Get Current User** — `GET /api/user/me` — Return authenticated user's data
- **Get User Availability** — `GET /api/user/{externalUserId}/availability` — Fetch weekly time availability for training
- **Upsert User Availability** — `PUT /api/user/{externalUserId}/availability` — Set available days/times for plan generation
- **Account Deletion** — Full GDPR-compliant user deletion with cascading data removal
- **Entra ID Integration** — OAuth 2.0 with Microsoft Entra ID for SSO

### **⌚ Wearables (Device Integrations)**

- **Wearable Auth Start** — `POST /api/auth/wearables/{provider}/start` — Initiate OAuth flow for Garmin/Wahoo (returns authorize URL)
- **Wearable Auth Callback** — `POST /api/auth/wearables/{provider}/callback` — OAuth callback handler (exchanges code for token)
- **Wearable Connection Status** — `GET /api/wearables/{externalUserId}/status` — Check if connected and last sync time
- **Wearable Disconnect** — `DELETE /api/wearables/{externalUserId}/{provider}` — Revoke provider access
- **Garmin Integration** — Full OAuth, activity webhook sync, plan push support
- **Wahoo Integration** — OAuth, activity webhook, plan sync capability
- **Activity Backfill Service** — Fetch historical activities on first connection
- **Webhook Handlers** — `WahooActivityWebhook` receives real-time activity events
- **Provider Pattern** — Abstracted `IExternalAuthProvider` allows easy addition of new wearable providers

### **💬 Feedback & Coaching**

- **Create Workout Feedback** — `POST /api/feedback/workout` — Record RPE, difficulty, mood, notes post-activity
- **Get Workout Feedback** — `GET /api/feedback/workout?userId={id}&date={range}` — Fetch athlete feedback history
- **Process Workout Feedback Job** — Background job that triggers SAMI to analyze feedback and suggest plan adjustments
- **Feedback Models** — RPE (1-10), difficulty, mood, optional text notes

### **🔔 Notifications**

- **Send Notification** — `POST /api/notifications/send` — Push notification to user (Firebase Cloud Messaging)
- **Admin Test Weekly Workout Notification** — `POST /api/admin/notifications/test-weekly-workout` — Test notification template
- **Admin Weekly Plan Nudge Test** — `POST /api/admin/notifications/test-nudge` — Trigger manual nudge reminder
- **Weekly Plan Nudge Processor** — Scheduled job sends "don't forget your plan" reminders

### **🤖 Assistants (SAMI AI Chat)**

- **Create/Ensure Assistant** — `PUT /api/assistants/{assistantId}/ensure` — Idempotent assistant creation (user-scoped)
- **Send Message** — `POST /api/assistants/{assistantId}` — Send user message to SAMI (returns streaming response)
- **Get Chat State** — `GET /api/assistants/{assistantId}?timestampUTC={ts}` — Retrieve full chat history
- **Azure OpenAI Integration** — Powered by Azure OpenAI `gpt-4-turbo`
- **Prompt Template Service** — Dynamic prompt generation with user context injection
- **Chat Storage** — Azure Table Storage for persistent chat state
- **Coach Assistant Query** — `GetAssistantStateForCoach` — Coach portal can query athlete's chat history

### **🔧 Devices & Configuration**

- **Add Device** — `POST /api/devices` — Register wearable device (smartwatch, head unit)
- **Delete Device** — `DELETE /api/devices/{deviceId}` — Remove device registration
- **Get Configuration** — `GET /api/config` — Fetch app configuration (API endpoints, feature flags)
- **Diagnostics/Health** — `GET /health`, `GET /hello` — Service health checks

---

## **PART 3: STREEKA COACH PORTAL (.NET BLAZOR WEB APP)**

### **🏅 Coach Dashboard & Overview**

- **Coach Overview Page** (`/coach`) — High-level dashboard showing athlete status summary
  - Total athletes on track (green status)
  - Athletes needing attention (amber/red status)
  - Missed sessions count
  - Quick-access athlete list with color-coded status
  - Period filter (Day/Week/Month view)
  - Attention signal strip (pulsing indicator if any red athletes)

- **Athlete List View** (`/coach/athletes`) — Expanded coach-facing athlete management
  - Filterable table by status (All, Green, Amber, Red)
  - Per-athlete: name, status indicator, missed sessions, RPE, SAMI engagement count
  - Quick drill-down links to detail view
  - Period filter controls

- **Athlete Detail Page** (`/coach/athletes/{athleteId}`) — Coach view of individual athlete
  - Athlete name, status chip, header card
  - **Recent Adherence Panel** — Scheduled vs. completed sessions; missed session explanations
  - **Athlete Feedback Panel** — Latest RPE, mood, athlete notes
  - **SAMI Activity Panel** — Recent AI coach interactions and plan adjustments
  - **Coach Action Context** — Placeholder for future messaging CTA

- **Coach Admin Page** (`/coach/admin`) — Admin functions (in-progress)
  - Coach invite management
  - System diagnostics
  - Role/permission management

### **🔐 Authentication & Authorization**

- **Login Page** (`/login`) — Microsoft Entra ID OAuth redirect
- **Access Denied Page** (`/access-denied`) — Unauthorized access notification
- **Role-Based Access Control** — Coach users see only assigned athletes
- **Athlete-Coach Linking** — `CoachAthlete` model defines relationships

### **📊 Coach Portal Services**

- **CoachPortalQueryService** — Fetches coach-scoped read models
  - `GetCoachOverviewAsync()` — Summary cards and athlete list
  - `GetCoachAthletesAsync()` — Filtered athlete rows with status, adherence, feedback
  - `GetCoachAthleteDetailAsync()` — Full athlete drill-in view data
  - Timezone-aware calculations per athlete

- **AthleteStatusService** — Computes status (Green/Amber/Red) from adherence, feedback, SAMI activity
  - Logic: Green = on track; Amber = partial compliance; Red = off plan

- **SamiChatService** — Queries SAMI chat state for athlete interactions
  - Fetch interaction count and summaries by date range

- **SamiSummaryService** — Generates human-readable SAMI activity summaries
  - E.g., "Asked about recovery after illness — plan adjusted"

- **CoachInviteService** — Manages coach onboarding and athlete roster assignment

### **🎨 UI Components (MudBlazor-based)**

- **CoachOverviewVm** — Data transfer object for overview page
- **CoachAthleteRowVm** — Row data for athlete list
- **CoachAthleteDetailVm** — Full detail view model
- **Status Chips** — Visual indicators (Green, Amber, Red)
- **Period Toggle** — Day/Week/Month selector
- **Summary List Items** — Reusable list component for adherence/feedback/SAMI data
- **Shared Layout** — Header, navigation, footer

### **✨ Key Features**

- **Fast Scanning** — Coach can review athlete status in under 10 seconds
- **Status-First Design** — Red/Amber flags surface immediately
- **Stale-While-Revalidate Caching** — Coach queries use local cache with background refresh
- **Timezone Awareness** — All dates computed per athlete's timezone
- **Real-Time Feedback** — Pull-to-refresh to see latest athlete data
- **Drill-Down Workflow** — Overview → List → Detail navigation

---

## **PART 4: SHARED/CORE INFRASTRUCTURE**

### **Data Models**

- **User** — App user profile (name, email, timezone, Entra linking)
- **Activity** — Recorded workout (Garmin, Wahoo, manual)
- **WeeklyPlan** / **OverallPlan** — AI-generated training schedules
- **AthleteGoal** — Training objectives (general or specific)
- **WorkoutFeedback** — Post-activity RPE, mood, notes
- **Streak** — Consistency tracker (days active, weekly workouts completed)
- **Device** — Wearable device registration
- **TrainingZone** — Power and HR zones (FTP-derived)
- **PersonalityProfile** — AI-computed coach personality label
- **CoachAthlete** — Many-to-many relationship between coaches and athletes
- **FitnessTrend** — CTL, ATL, TSS time series
- **WeeklyPlanDay** / **WeeklyPlanWorkout** — Granular workout structure
- **ActivityBestEffort** — Detected power efforts (1min, 5min, 20min, 1hr)
- **ActivityLap** — Lap-level aggregated metrics
- **ActivitySample** — Detailed time-series data (power, HR, cadence)

### **Integrations**

- **Azure OpenAI** — Plan generation, SAMI chat, personality profiling
- **Garmin Connect OAuth** — Activity sync, plan push, device management
- **Wahoo Cloud OAuth** — Activity sync, plan integration
- **Firebase** — Remote config, cloud messaging, crashlytics
- **RevenueCat** — Subscription management and in-app purchases
- **Microsoft Entra ID** — Authentication and identity
- **Azure SQL Database** — Persistent data store
- **Azure Blob Storage** — File storage (images, exports)
- **Azure Queue Storage** — Async job queueing (plan generation, activity processing)
- **Azure Table Storage** — Chat state persistence
- **Firebase Remote Config** — Feature flags and environment configuration
- **Mixpanel** — Analytics event tracking
- **Application Insights** — APM and diagnostics

### **Cross-Cutting Services**

- **FunctionsService** — HTTP client wrapper for API calls
- **RemoteConfigService** — Feature flag and config retrieval
- **AuthService** — Token acquisition and lifecycle
- **SafeSecureStorage** — Encrypted credential storage
- **ActivityFeedbackService** — Process and summarize feedback
- **AnalyticsService** — Event tracking
- **CrashlyticsService** — Error reporting
- **PlanService** — Plan caching and fetching orchestration

---

This exhaustive list captures all 60+ features across the Flutter app, Azure Functions backend, and Blazor coach portal, organized by functional domain with clear descriptions of each capability.