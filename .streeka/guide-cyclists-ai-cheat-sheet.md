# The Cyclist's AI Training Cheat Sheet
## What to ask Claude when it has your Strava data

From Sam Sutherland, founder of Streeka

---

AI tools can now connect directly to Strava.

Claude can do it through Strava's MCP connector. More tools will follow.

This is genuinely useful.

Once connected, Claude can look at your training data directly instead of relying on you to describe it. It can look at your rides, compare patterns, check power, heart rate, pace, GPS, segments, and activity history.

But here's the catch.

Most cyclists will still get average answers, because they'll ask average questions.

They'll ask things like:

> "How's my training going?"

Or:

> "What should I do next?"

And they'll get something that sounds reasonable, but often misses the real coaching problem.

Good training questions need context, constraints, and a decision to make.

This guide gives you better prompts.

Use them to get more useful answers from Claude when it has your Strava data, and to understand where the connection stops being enough.

---

## The simple rule

Don't ask AI to "look at your training."

Ask it to compare something specific, diagnose a pattern, or help make a decision.

Bad prompt:

> "Analyse my cycling."

Better prompt:

> "Look at my last 6 weeks of rides. Am I actually keeping my easy days easy, or am I riding too hard between harder sessions? Use heart rate, power, and ride duration to explain your answer."

That second version gives the AI something concrete to investigate.

The difference isn't magic. It's just asking a better question.

---

# 1. Easy day audit

Most cyclists don't plateau because they never ride hard.

They plateau because they ride moderately hard all the time. Too hard to recover. Not hard enough to create a strong training signal. The classic endurance grey zone.

Use this prompt:

> "Look at my rides from the last 6 weeks. Which sessions look like they were meant to be easy but probably weren't? Use duration, heart rate, power, and ride title if available. Give me a short list of rides where I may have turned an easy day into a medium-hard day."

Follow-up:

> "What pattern do you see? Is this happening after hard sessions, before hard sessions, on group rides, or when I ride solo?"

Why this works:

You're not asking for motivation. You're asking for a pattern. That's where AI becomes useful.

---

# 2. Hard session quality check

A lot of cyclists think they're training hard because the ride felt unpleasant.

That's not the same as executing a useful hard session.

Use this prompt:

> "Find my hardest structured rides from the last 4 to 8 weeks. For each one, tell me whether the hard work looks well executed or messy. Look at power consistency, heart rate response, recovery between efforts, and whether I faded late in the ride."

Follow-up:

> "Which type of hard work do I seem to execute best: short VO2-style efforts, threshold work, longer tempo, or climbs?"

Why this works:

It moves past "that was hard" and starts looking at whether the session actually did its job.

---

# 3. Heart rate vs power drift

This is one of the most useful things to ask about after endurance rides.

If your power stays the same but heart rate climbs, that can suggest fatigue, heat, dehydration, poor fuelling, or simply that the ride was harder than you thought.

Use this prompt:

> "Look at my longest endurance rides from the last 6 weeks. Do you see heart rate drifting upward relative to power as the ride goes on? Compare the first half and second half of each ride. Explain what that might suggest, but don't overstate it."

Follow-up:

> "Which ride shows the biggest mismatch between power and heart rate, and what should I check first: fuelling, pacing, heat, fatigue, or recovery?"

Why this works:

You're asking for a signal, not a vague feeling.

---

# 4. Group ride damage report

Group rides are brilliant.

They're also where training plans often go to die.

Use this prompt:

> "Look at my recent group rides or bunch rides. How hard are they compared with my other rides? Do they look like endurance rides, threshold sessions, repeated surges, or races I'm pretending are social?"

Follow-up:

> "If I keep this group ride in my week, what kind of session should I avoid placing too close to it?"

Why this works:

The AI can help you understand what the ride actually costs, not just what it was supposed to be.

---

# 5. Training consistency check

Consistency isn't just "did I ride?"

It's whether your week contains enough useful work, enough recovery, and enough repeatable structure to create adaptation.

Use this prompt:

> "Look at my last 8 weeks. How consistent has my training actually been? Don't just count rides. Look at weekly volume, hard sessions, long rides, recovery days, and missed weeks. Give me the main pattern."

Follow-up:

> "What's the biggest limiter in my recent training: not enough volume, too much intensity, inconsistent long rides, poor recovery, or lack of progression?"

Why this works:

You're forcing the answer to identify a constraint. Training improves when you find the bottleneck.

---

# 6. Fitness trend reality check

This is where you need to be careful.

Claude can describe trends from your Strava data. That can be useful. But it's not the same as having a complete training model that knows your plan, your intent, your feedback, and what you were supposed to do.

Use this prompt:

> "Based on my recent training history, what signs suggest I'm improving, maintaining, or going backwards? Use evidence from power, heart rate, pace, ride duration, climb performance, and consistency. Separate strong evidence from weak evidence."

Follow-up:

> "What would you need to know before making a confident recommendation about my next training block?"

Why this works:

That follow-up is the important part.

A good answer should admit what it doesn't know.

---

# 7. Missed training recovery prompt

This is the real-world one.

Because most training advice assumes your week goes perfectly. Most people's weeks don't.

Use this prompt:

> "I missed training this week. Look at what I actually did compared with my recent normal training pattern. What's the sensible way to resume without cramming everything in?"

Follow-up:

> "What should I absolutely not try to make up?"

Why this works:

The danger after a missed week isn't always undertraining. Often, it's panic-training.

---

# 8. Event readiness prompt

This works best when you give the AI the event context.

Don't just ask:

> "Am I ready?"

Ask:

> "I'm training for [event name/type] on [date]. It's [distance], with [climbing], and my goal is [goal]. Based on my recent Strava data, what parts of my training look well prepared, and what parts look underprepared?"

Follow-up:

> "What are the top 3 risks between now and the event?"

Why this works:

Readiness isn't generic fitness. It's fitness matched to a specific demand.

A flat 100 km bunch ride, a hilly gran fondo, a criterium, and a 300 km day aren't the same problem.

---

# 9. "What should I do this week?" prompt

This is the question everyone wants to ask.

It's also the question where a Strava connection can start to struggle, because your activity data is only part of the answer.

Use this prompt:

> "Based on my recent Strava data, suggest a sensible training week. Before you answer, list the assumptions you're making about my goal, available time, fatigue, and current training phase."

Follow-up:

> "Now rewrite the week assuming I only have 4 hours available and need to keep Saturday fresh."

Why this works:

You're making the AI show its working assumptions.

That matters because the best training week isn't the best-looking week on paper. It's the week you can actually execute.

---

# 10. The prompt that reveals the limit

Use this one when you want to understand what the AI can and can't know from Strava alone.

> "Based only on my Strava data, what can you confidently tell me about my training? What can you only guess? What important coaching context is missing?"

This is one of the best questions you can ask.

Because Strava data can show what happened.

It doesn't always show why it happened.

It may not know that you were sick, sleeping badly, travelling, stressed, time-poor, under-fuelled, or trying to squeeze intervals between work calls.

That missing context is often where the coaching problem lives.

---

# The useful distinction

Claude with Strava is excellent for asking:

> "What happened in my training?"

And sometimes:

> "What patterns can you see?"

That's valuable.

But coaching isn't just analysis.

Coaching is the loop:

1. What are you trying to achieve?
2. What was planned?
3. What actually happened?
4. How did it feel?
5. What does that change?
6. What should happen next?

That's where Streeka is different.

Streeka isn't just a window into your Strava history. It's built around the training loop.

SAMI, Streeka's AI coach, knows your goal, your current plan, your FTP, your zones, your recent training, your missed sessions, your feedback, and what you're trying to build towards.

It doesn't just analyse the rides after the fact.

It helps adjust the plan.

That's the bit most cyclists actually need, because real life keeps interfering with training. Work gets busy. Legs feel dead. Kids get sick. Weather turns bad. A group ride turns into a race even though everyone said it was going to be steady.

The plan needs to adapt.

---

# What to ask Streeka instead

These work because Streeka already has the training context.

> "What should I do this week given my last 3 sessions?"

> "I've only got 45 minutes tomorrow. What's the most useful session?"

> "I missed 4 sessions this month. How do we recover the block?"

> "My legs are heavy and I have a key ride Saturday. What should I do Wednesday?"

> "Am I doing enough hard work, or is my training too comfortable?"

> "What does my fitness trend say about this block?"

> "I want to build toward [event]. Where should I start?"

> "I did the session but felt awful. Should we change the rest of the week?"

That's the difference.

Strava plus Claude helps you inspect the evidence.

Streeka helps turn the evidence into the next decision.

---

# The takeaway

Use Claude with Strava. It's genuinely useful.

Ask better questions and you'll get better answers.

But don't confuse analysis with coaching.

A good training system doesn't just tell you what happened.

It helps you decide what to do next.

That's what Streeka is built for.

---

## Try Streeka free

The free trial is two weeks.

No credit card. No form. Download the app and ask SAMI what to do next.

[Start your free trial →]
(App Store / Play Store link)

---

Streeka — AI training for cyclists and runners. iOS + Android. streeka.com
