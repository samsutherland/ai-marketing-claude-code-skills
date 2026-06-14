Here's everything the Strava MCP exposes based on what I loaded:
5 tools:
list_activities — paginated activity list (max 100), sorted by date only, with optional date range filter. Each activity includes id, name, sport type, start time, distance, elapsed/moving time, elevation, avg/max speed, cadence, calories, relative effort, kudos, achievement + PR counts. Optional polyline and tags.
get_activity_performance — single activity deep-dive by ID: HR flags, avg/max HR, avg watts, avg cadence, calories, perceived exertion, PR achievements, segment efforts, best efforts, laps.
get_activity_streams — time-series data for a single activity. Available streams: time, location, heart_rate, watts, cadence, distance, altitude, velocity_smooth, grade_smooth, moving, temp. Configurable resolution.
get_gear — bikes and shoes. Bikes: weight, frame type, total distance, retired status. Shoes: brand, model, total distance. Filterable by gear type.
get_club_info — clubs you're a member of: name, sport type, member count, plus upcoming events with date/time, address, and recurrence rules. Paginated.

Notable omissions (things Strava's own API supports but the MCP doesn't expose):

Athlete profile / zones (there's a get_athlete_profile tool mentioned in the schema description but it wasn't in the loaded tools — possibly gated behind eligibility)
Segment leaderboards
Routes
Followers / following
Kudos / comments
Writing back to Strava (creating/updating activities)
Filtering by sport type natively
Ordering by anything other than date

It's a read-only, activity-centric subset. Solid for analysis, nothing for social or write operations.