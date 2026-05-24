---
title: Variable Reference
description: All available variables for commands, messages and templates.
---

# Variable Reference

Variables are written in curly braces: `{variable}` or `{variable:parameter}`.
You can use them in commands, welcome messages, automod warnings, live announcements and more.

[:flag_de: Deutsche Version](variablen.md)

---

## Command Variables (Twitch & YouTube)

### Basic (Free)

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{user}` | Your display name | `Thymply_` |
| `{channel}` | Channel name | `die_prototypen` |
| `{touser}` | Mentioned user or yourself | `!hug @Night` -> `Night` |
| `{query}` | Everything after the command | `!wiki Python` -> `Python` |
| `{userlevel}` | Your role in chat | `moderator`, `subscriber`, `everyone` |
| `{count}` | Call counter (persistent) | `42` (counts up forever) |
| `{count_stream}` | Call counter (per stream) | `7` (resets on stream start) |

**Examples:**

```
!hug -> {user} hugs {touser}! ({count} hugs total)
!rank -> {user}, you are {userlevel} in this chat.
```

### Time (Free)

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{time}` | Current time (CET) | `14:30` |
| `{time:Zone}` | Time in timezone | `{time:America/New_York}` -> `8:30` |
| `{countdown:Date}` | Time until a date | `3 days, 5 hours, 20 minutes` |
| `{countup:Date}` | Time since a date | `2 years, 3 months, 1 day` |
| `{date}` | Current date (DD.MM.YYYY) | `24.05.2026` |
| `{date:FORMAT}` | Date in specific format | `{date:long}` → `24. May 2026` |

**Supported timezones:** `CET`, `EST`, `PST`, `GMT`, `JST` or IANA format like `Europe/Berlin`, `America/New_York`.

**{date} formats:**

| Format | Example | Description |
|--------|---------|-------------|
| `{date}` | `24.05.2026` | Default (DD.MM.YYYY) |
| `{date:short}` | `24.05.26` | Short (DD.MM.YY) |
| `{date:iso}` | `2026-05-24` | ISO 8601 |
| `{date:long}` | `24. May 2026` | Long written out |
| `{date:weekday}` | `Saturday` | Day of the week |
| `{date:month}` | `May 2026` | Month and year |
| `{date:us}` | `May 24 2026` | US format |
| `{date:us_long}` | `May 24, 2026` | US format long |

```
!date -> Today is {date:weekday}, {date:long}.
!countdown -> {countdown:Dec 25 2026 00:00} until Christmas!
```

### Random (Free)

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{random.X-Y}` | Random number between X and Y | `{random.1-100}` → `42` |
| `{random:a\|b\|c}` | Random element from list (pipe-separated) | `{random:yes\|no\|maybe}` → `no` |

```
!8ball -> {random:yes|no|maybe|ask later|absolutely not}
!roll -> {user} rolls a {random.1-6}!
!choose -> {random:Rock|Paper|Scissors}
```

### Stream (Free)

| Variable | Description | Example Output | Platform |
|----------|------------|----------------|----------|
| `{uptime}` | Stream duration | `2h 35m` | Twitch + YouTube |
| `{title}` | Current stream title | `Chill stream with community` | Twitch + YouTube |
| `{game}` | Current category/game | `Just Chatting` | Twitch + YouTube |
| `{followage}` | How long you follow the channel | `1 year, 3 months` | Twitch only |
| `{watchtime}` | Your watch time this session | `45m` | Twitch + YouTube |

!!! warning "Twitch only"
    `{followage}` only works on Twitch. On YouTube it shows `[Twitch only]`.

### External (Pro/Premium) :material-crown:{ .pro-badge }

These variables are only available for **Pro** and **Premium** users. Free users see `[Pro required]`.

| Variable | Description | API | Cache |
|----------|------------|-----|-------|
| `{weather:Location}` | Current weather | Open-Meteo | 10 min |
| `{twitch:User}` | Twitch profile info | Twitch API | -- |
| `{steam:User}` | Steam profile info | Steam Web API | -- |
| `{urlfetch:URL}` | Call external API (text) | HTTP GET | -- |
| `{urlfetch_json:URL:path}` | Call external API (JSON field) | HTTP GET + JSON | -- |

#### {urlfetch:URL}

Calls an external URL and returns the response as text.

- HTTPS URLs only
- Maximum 400 characters response
- Timeout: 3 seconds
- Rate limit: 1 call per 5 seconds per command

#### {urlfetch_json:URL:path}

Like `{urlfetch}`, but parses the JSON response and returns a specific field.

The path uses dot notation with array support:

- `joke.text` -> `{"joke": {"text": "..."}}`
- `data.results[0].name` -> `{"data": {"results": [{"name": "..."}]}}`

---

## Discord Welcome & Farewell

| Variable | Description | Example Output | Pings? |
|----------|------------|----------------|:------:|
| `{user}` | @Mention of the user | `@Thymply_` | **Yes** |
| `{username}` | Name without mention | `Thymply_` | No |
| `{server}` | Server name | `My Discord Server` | No |
| `{membercount}` | Current member count | `1337` | No |

---

## Discord AutoMod Warnings

| Variable | Description | Example Output | Pings? |
|----------|------------|----------------|:------:|
| `{user}` | @Mention of the offender | `@Thymply_` | **Yes** |
| `{username}` | Name without mention | `Thymply_` | No |

Available in: Spam warning, link filter warning, bad word filter warning.

---

## Discord Temp Voice Channel Names

!!! info "No @Mention"
    In the Temp Voice context, `{user}` does **not** create an @Mention. All variables are inserted as plain text, since Discord does not allow mentions in channel names.

| Variable | Description | Example |
|----------|------------|---------|
| `{user}` | Display name (server nickname or global name) | `Thymply_` |
| `{username}` | Unique Discord handle (always lowercase) | `thymply_` |
| `{game}` | Current game of the user (fallback: `Chillen`) | `Minecraft` |

**Example templates:**

| Template | Result |
|----------|--------|
| `Channel of {user}` | `Channel of Thymply_` |
| `{username}'s room` | `thymply_'s room` |
| `{user} plays {game}` | `Thymply_ plays Minecraft` |

---

## Discord Live Announcements

### Twitch Stream

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{user}` | Streamer display name | `Thymply_` |
| `{channel}` | Twitch channel name | `thymply_` |
| `{title}` | Stream title | `Chill stream with community` |
| `{game}` | Game/category | `Just Chatting` |
| `{url}` | Stream link | `https://twitch.tv/thymply_` |
| `{viewers}` | Viewer count | `142` |
| `{mention}` | @Mention of the Discord user | `@Thymply_` |
| `{vod}` | Link to last VOD (if available) | `https://twitch.tv/videos/...` |

### YouTube Stream

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{user}` | Channel name | `einfruechtchen` |
| `{channel}` | Channel name | `einfruechtchen` |
| `{title}` | Stream title | `Minecraft Survival` |
| `{url}` | Stream link | `https://youtube.com/watch?v=...` |
| `{viewers}` | Viewer count | `85` |

### Combined Announcement (Twitch + YouTube simultaneously)

| Variable | Description |
|----------|------------|
| `{streamer}` | Streamer name |
| `{twitch_name}` | Twitch channel name |
| `{youtube_name}` | YouTube channel name |
| `{twitch_url}` | Twitch stream URL |
| `{youtube_url}` | YouTube stream URL |
| `{twitch_game}` | Twitch category |
| `{title}` | Stream title |
| `{viewers}` | Viewer count |

---

## Discord Tickets

| Variable | Description | Example Output | Pings? |
|----------|------------|----------------|:------:|
| `{user}` | @Mention of the ticket creator | `@Thymply_` | **Yes** |

Available in the ticket welcome message.

---

## Discord Duplicate Detection

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{mention}` | @Mention of the user | `@Thymply_` |
| `{game}` | Game name | `Minecraft` |
| `{original}` | Who suggested it first | `Night` |
| `{count}` | How often suggested | `3` |
| `{link}` | Link to original suggestion | `https://discord.com/channels/...` |

---

## Discord Counter Messages

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{count}` | Current counter value | `42` |
| `{name}` | Counter name | `Deaths` |
| `{game}` | Associated game | `Elden Ring` |
| `{user}` | Triggering user | `Thymply_` |
| `{amount}` | Change amount | `1` |

---

## Twitch Ad Break Announcement

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{duration}` | Ad duration in seconds | `90` |
| `{minutes}` | Ad duration in minutes (rounded) | `1.5` |
| `{type}` | Type of ad break | `manual` or `automatic` |

**Pre-warnings** have additional variables:

| Variable | Description | Example Output |
|----------|------------|----------------|
| `{seconds}` | Seconds until ad break | `30` |
| `{minutes}` | Minutes until ad break | `0.5` |

---

## Platform Overview

### `{user}` by Context

| Context | Value | Pings? |
|---------|-------|:------:|
| **Twitch Command** | Display name (`Thymply_`) | No |
| **YouTube Command** | Author name | No |
| **Discord Welcome** | @Mention (`@Thymply_`) | **Yes** |
| **Discord AutoMod** | @Mention (`@Thymply_`) | **Yes** |
| **Discord Temp Voice** | Display name (`Thymply_`) | No |
| **Discord Tickets** | @Mention (`@Thymply_`) | **Yes** |
| **Discord Counter** | Triggering user | No |

### YouTube Compatibility

All free-tier command variables also work on YouTube -- except `{followage}` (returns `[Twitch only]`). Pro/Premium variables like `{weather}`, `{urlfetch}` and `{steam}` work cross-platform.
