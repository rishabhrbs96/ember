# Ember language audit: final recommendations

This audit recommends copy changes only. It does not change the application.

## Language decisions

- Use **device** everywhere when describing where Ember saves or keeps data. It is simpler and more natural for the intended audience.
- Use American English throughout.
- Use curly apostrophes and quotation marks in visible copy.
- Use **complete** and **completed** for tasks and days. Avoid mixing these terms with **done**.
- Capitalize **Ember** and **Fuel** whenever they name product features.
- Keep visible copy plain, warm, brief, and in sentence case.

## Highest-priority changes

### 1. Make the first-run choice explicit

**Current title**

> Keep your list on this device?

**Keep as written.** It is clear, approachable, and uses the preferred storage term.

**Recommended body**

> Ember saves your tasks, streak, and theme on this device. Nothing is sent anywhere. There is no account, no cookie, and no analytics.
>
> Without saving, your list is cleared when you close Ember. You can export or erase saved data under Settings.

**Current actions**

> Not now  
> Save on this device

**Recommended actions**

> Continue without saving  
> Save on this device

“Continue without saving” makes the result of the secondary action clear. “Save on this device” should remain unchanged.

### 2. Remove the contradiction in Settings

The current introduction says all data is stored while the same screen can report that saving is off.

**Recommended**

> Ember never sends your data anywhere. When saving is on, it stays on this device. Days older than two years are removed automatically.

**Current fact label**

> Saving to this device

**Recommended fact label**

> Saving on this device

Use the same preposition as the first-run action.

### 3. Explain the empty first-day state accurately

When there are no tasks, “Complete today’s list” asks the person to complete a list that does not yet exist.

**Current**

> No streak yet. Complete today’s list to begin one.

**Recommended behavior**

- With no tasks: `No streak yet. Add a task to begin.`
- With one or more tasks: `No streak yet. Complete today’s list to begin one.`

## Header and Today

### Previous-best streak

**Current**

> No current streak. Your best is {N} days.

**Recommended**

> No streak right now. Your best is {N} days.

“Right now” sounds warmer and less administrative than “current.”

### Unfinished-streak slogan

**Current**

> Keep it alight.

**Recommended**

> Keep the flame alive.

The rewrite is more familiar while retaining Ember’s fire language.

### Empty-day status

**Current**

> Nothing planned.

**Recommended**

> No tasks yet.

This names the actual object managed by the application.

### Theme accessibility labels

Keep the visible actions **Dim** and **Bright**.

**Current accessible labels**

> Dim the theme  
> Brighten the theme

**Recommended accessible labels**

> Switch to Dim  
> Switch to Bright

These labels preserve the product vocabulary while making the action explicit without relying on the visual context.

### New-task accessibility label

The visible placeholder changes with the selected date, but the accessible name remains “New task.” Make the accessible name change as well:

- `New task for today`
- `New task for tomorrow`
- `New task for {date}`

### Date and count copy

Keep the following strings unchanged:

- `{Weekday}, {D} {Month}`
- `All completed.`
- `{N} remaining.`
- `{N} scheduled for tomorrow.`
- `{N} scheduled ahead.`
- `Add to`
- `Today`
- `Tomorrow`
- `Another date`

They are concise and understandable in context.

## Fuel

### Introduction

**Current**

> Fuel holds the tasks you do every day. Each one is added to every new day’s list automatically.

**Recommended**

> Fuel is your list of daily tasks. Each is added to every new day automatically.

The rewrite defines Fuel directly and removes unnecessary words.

### Empty state

**Current**

> No daily tasks yet. For example: Stretch, or Read ten pages.

**Recommended**

> No daily tasks yet. Add something like Stretch or Read ten pages.

This removes the awkward comma and turns the example into a useful prompt.

### Fuel controls

Keep these strings unchanged:

- `Add a daily task`
- `New Fuel item`
- `Fuel items`
- `Remove from Fuel: {task}`

## History

### Calendar key

**Current**

> completed  
> partly completed  
> not completed

**Recommended**

> All completed  
> Partly completed  
> Not completed

The three labels become parallel and describe the whole day rather than an unspecified object.

### Monthly summary

**Current**

> {completed} of {listed} listed days completed in full.

**Recommended**

> {completed} of {listed} days with tasks fully completed.

“Days with tasks” is more immediately understandable than “listed days.”

### Empty state

**Current**

> No past days yet. Today will appear here tomorrow.

**Recommended**

> No history yet. Today appears here tomorrow.

The rewrite is shorter and connects directly to the name of the view.

### Day-page accessibility labels

The current row labels contain only the task text. Add the completion state:

- `Completed: {task}`
- `Not completed: {task}`

### History controls

Keep these strings unchanged:

- `Previous month`
- `Next month`
- `Back to the month`
- `Completed`
- `Not completed`
- `{completed} of {total} completed.`

## Settings, saving, and data

### Stop-saving dialog

**Recommended**

> Your saved copy stays on this device. New changes last only until you close Ember. To remove the saved copy, choose Erase all data.

This is shorter, uses the preferred storage language, and explains the difference between existing and new data.

Keep the title and actions unchanged:

- `Stop saving?`
- `Cancel`
- `Stop saving`

### Saving-off banner

**Recommended**

> Saving is off. This list will be cleared when you close Ember.

“Cleared” is more neutral and precise than “lost.”

Keep the action:

> Turn saving on

### Storage-blocked message

**Recommended**

> Ember cannot save on this device. This list will be cleared when you close Ember. Private mode may be the cause.

### Saving feedback

**Current**

> Saving resumed.

**Recommended**

> Saving on this device.

The rewrite confirms the resulting state and matches the Settings label.

### Export feedback

**Current**

> Exported. The file contains every day, every Fuel item, and the streak.

**Recommended**

> Exported. The file includes your tasks, Fuel items, streak, and settings.

This more accurately describes the exported data.

### Import feedback

**Current patterns**

> Replaced. {N} days and {M} Fuel items from the file.  
> Merged. {N} days and {M} Fuel items from the file.

**Recommended patterns**

> Replaced your data with {N} days and {M} Fuel items.  
> Merged {N} days and {M} Fuel items from the file.

### Invalid import entries

**Current**

> {N} unreadable entries were skipped.

**Recommended**

> {N} invalid entries were skipped.

Use the singular form `1 invalid entry was skipped.`

“Invalid” is more accurate because the file was readable but some entries failed validation.

### Erasing data

Keep the following copy unchanged:

- `Erase all data?`
- `Every task, Fuel item, past day, and the streak will be removed from this device. This cannot be undone.`
- `Erase all data`
- `Erased.`

The body should use **device** in place of the current storage term.

## Import-version dialog

### Title

**Current**

> Two versions of this list

**Recommended**

> Which version should Ember keep?

The rewrite turns the title into the decision the person needs to make.

### Body

**Current**

> This list has changed since it was last saved. Choose which version to keep.
>
> The saved copy discards the changes made here. Merge keeps both. This session replaces the saved copy.

**Recommended**

> This list has changed since it was last saved.
>
> Saved copy discards changes from this session. Merge combines both versions. This session replaces the saved copy on this device.

### Actions

Keep the existing actions:

- `Cancel`
- `Saved copy`
- `Merge`
- `This session`

## Installation

### Development-only installation message

**Current**

> Installation requires Ember to be served over HTTPS rather than opened as a file.

**Recommended**

> To install Ember, open it from a secure web address.

This keeps technical protocol language out of the interface.

### Other installation copy

Keep the remaining installation text unchanged. It is direct and explains the offline benefit without overselling it.

## Page and installation descriptions

### Page description

**Recommended**

> Ember. Keep the fire within. A to-do list that stays on your device and helps you keep a daily streak.

### Installation description

**Current**

> Keep the fire within. A to-do list that stays on your device, with a streak to keep.

**Recommended**

> Keep the fire within. A to-do list that stays on your device and helps you keep a daily streak.

Using the same final sentence in both locations keeps the product description consistent.

## Recommended final slogan ladder

- No streak and no previous best: `Light it up.`
- No streak with a previous best: `Light it again.`
- Active streak, today incomplete, under three days: `Still warm.`
- Active streak, today incomplete, three days or more: `Keep the flame alive.`
- Today completed, one or two days: `First light.`
- Today completed, three to six days: `Keep it burning.`
- Today completed, seven to twenty-nine days: `Burning bright.`
- Today completed, thirty days or more: `Unbroken.`

Each rung is distinct, brief, and consistent with Ember’s restrained fire metaphor.

## Summary

The strongest existing copy should remain: the product name, tagline, navigation, date controls, core action labels, and most of the streak ladder. The recommended changes concentrate on four areas:

1. Use **device** consistently for saving and storage.
2. Explain the consequence of continuing without saving before the person chooses it.
3. Remove contradictions between general privacy copy and the current saving state.
4. Make status and accessibility language more explicit without making the visible interface heavier.
