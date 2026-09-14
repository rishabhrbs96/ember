# Ember design direction

Direction transcribed from the owner's brief. Specific values (palette, type, motion timings) were chosen by the agent and are marked so; change them freely.

## Brief (owner's words, paraphrased)

Ultra-minimal todo list. Bare minimum UI. Browser only, local storage only. Something that builds a streak and makes the app worth coming back to. Very clean, seamless animation.

## Design read

Reading this as: a single-screen personal utility for one person, in a warm ultra-minimal style, dial ENERGY 1 / RHYTHM 1 / MOTION 2.

- ENERGY 1: the list is the product. Nothing competes with the input box and the tasks.
- RHYTHM 1: one screen, one column, no sections. Uniformity is the point.
- MOTION 2: motion on state change (add, finish, remove, reorder, streak lights). Reduced-motion preference disables all of it.
- One owner-requested exception: the lit flame flickers gently on a loop. The owner asked for fire animation as the app's identity, so this is recorded as a deliberate override of the no-endless-loops rule. It is the only looping motion on the page and it marks a real state (the streak is alive).

## Identity motif (owner direction, agent execution)

Fire. The name sits small at the top like a native app title. Below it the hearth: a large flame, the one focal point on every screen, with two layers, an outer tongue and a paler inner one, each flickering at its own pace while the streak is alive, an outline when it is out. Its glow grows with how much of today is finished. Beside it, one line addressed to the person that changes with the streak ("Light it up." through "Nothing puts you out."), then the streak numeral. The same flame is the favicon. A small outline flame marks tasks that came from Fuel. History shows each day as a small ember, lit or not. Finishing a task throws three sparks off the mark. Lit and cold always differ in shape as well as colour.

The orange is used for: the lit flame and its glow, a finished task's mark, lit and part-done day embers in History, the active view's icon on the phone bar, keyboard focus, and the one destructive button in a dialog. Nowhere else.

## Vocabulary

- Fuel: the recurring list that goes on every day. Chosen over "master list" and "kindling" because everyone knows what fuel does to a fire.
- Out / warm / burning: the flame states. Out means no streak. Warm means the streak is alive but today's list is not finished. Burning means today is done.
- Done: a day counts when every task on it is finished. Finishing one thing is not enough to keep a fire going.
- Dim / Bright: the theme switch labels. They name the action, not the mode.

## Palette (agent chosen)

Warm paper, not white. Warm ink, not black. One accent.

| Role | Light | Dark |
|------|-------|------|
| Paper | #faf7f2 | #141210 |
| Ink | #1d1a17 | #efe9e2 |
| Muted text | #6e665e | #a39b92 |
| Rule line | #e6e0d8 | #2a2622 |
| Ember (accent) | #bf4a1a | #ff7a3d |
| Cold ember | hollow ring in Muted text colour | hollow ring in Muted text colour |

Why warm: an ember belongs on paper, not on a screen-blue white. Why one accent: the streak is the only thing that needs to be noticed.

Theme follows the operating system until the person picks Dim or Bright. The choice is remembered.

## Typography (owner's pick)

Ranade Light for display, Satoshi Light for everything else. Both from the Indian Type Foundry through Fontshare, both self-hosted, one weight each. Ranade is a sharp, airy modern serif drawn for Latin and Devanagari together; it carries the wordmark (uppercase, tracked wide), the slogan, the streak numeral, the date line, month and day titles, dialog titles, and Settings group titles. Satoshi is a warm geometric sans; at its light weight it carries tasks, hints, buttons, and navigation. Nothing on the page is bold; hierarchy comes from the two faces, size, case, and spacing. Navigation and small labels are spaced uppercase, an owner-directed luxury cue.

No visitor ever contacts a font service. Fallbacks are Didot or Bodoni then Georgia for display, Avenir Next or Helvetica Neue then the system sans for text.

## Spacing

One column, max 30rem wide, generous top margin. Rows are separated by hairlines, not cards. Whitespace does the grouping.

## Motion (agent chosen)

See Motion budget below. The flame's glow is a static blurred disc behind the SVG, so the flicker only moves transforms.

## Views

One screen, four views: Today, Fuel, History, Settings. Today is default because the app's whole job is today.

On wide screens the views are a segmented control under the hearth; the active segment is tinted with the rule colour and its icon turns ember, so the state reads at a glance without a block of ink outweighing the flame. On phones (under 700px) the same control becomes a fixed bar at the bottom of the screen, where thumbs are, each view an icon over a label, the active icon in ember. On watches the labels hide and the icons stay. The four icons are drawn for this app: a checked circle, the flame, three dots for the strip of days, two sliders.

## Sizes

Type scales with the device through the root font size: 87.5% under 290px (watches), 93.75% under 400px (phones), 106.25% above 900px, 118.75% above 1600px. The column widens from 30rem to 34rem on wide screens. Nav labels hide on watches and the icons stay. Nothing else changes shape, because the layout is one column everywhere.

## Motion budget

Motion only where it shows cause and effect. Every animation is transform, opacity, or background-size, so it stays cheap.

- Add: the row slides in from the input.
- Finish: the mark fills, three sparks leave it (500ms), the row glides to the bottom. When the last task tips today into done, the flame flares and starts to burn. Adding or unfinishing a task after that settles it back to warm.
- Remove: the row slides out.
- Focus the input: the ember underline draws in from the left.
- Open History: 35 embers fill in over 210ms, left to right, like days passing.
- The flame flickers while lit and its glow tracks today's completion.
- The slogan fades in when it changes.

No fades on view switches, no ambient movement anywhere else. All of it is off under prefers-reduced-motion.

## Data and consent

A first-run dialog explains that everything stays in the browser and asks before anything is written. Settings shows what is stored and offers export, import, stop, and erase. The first-run dialog stays by owner decision.

While nothing is being saved, a standing banner at the top of every view says so, with a Start saving link in it. It has an ember border because losing a list is the one real risk in the app. The same banner carries the storage-blocked message.

Stop saving leaves the saved copy as it was at that moment and stops writing; it does not delete anything, and says so. Start saving compares this session's list with the saved copy. If they differ, a dialog asks which to keep: the saved copy (discarding the session's changes), a merge of both, or this session (replacing the copy). This session is the ember button because it overwrites.

## Install offer

Once, after the first-run question, where installing is possible, a dialog offers to put Ember on the home screen: an Install button where the browser provides one, the Share then Add to Home Screen steps on iPhone. Whatever the answer, it is not asked again; the Install row in Settings remains.

## Dialogs

Every dialog looks like a dialog: a bordered panel with a shadow over a darkened, blurred page, a title phrased as the question, one paragraph, then the actions on their own row with the cancel on the left and the primary on the right. The browser's own confirm() is never used. A destructive primary is ember; every other primary is ink.

## Later days

Under the box, a row of chips: Add to Today, Tomorrow, Another day. You choose the day first, then type and press Enter, so the intent is visible before the task goes anywhere. The placeholder follows the choice ("What will you do tomorrow?"). Another day opens the device's own date picker and the chip then shows the chosen date. After each add the row resets to Today. Cmd or Ctrl with Enter still means tomorrow. Under the date line, a count of what is waiting opens into a plain list with a remove button per task.

## Fuel, explained

Fuel is the list of things you do every day. Anything on it is added to every new day's list automatically, so you never type "Stretch" twice. The Fuel view says this in one sentence at the top, and its empty state suggests two examples.

## Voice

Professional and calm, in the register of a well-run private service. Complete sentences, plain words, no slang, no exclamation, contractions only where the sentence would sound stiff without one. Each notice states what is true and what the person can do: "Saving is off. This list will be lost when the tab is closed." Buttons name the action they perform. Work is "completed", never "done"; data is "removed" or "cleared", never "gone". Storage is always "this device". Spelling is American. Apostrophes and quotation marks are curly.

## Tagline

"Keep the fire within." It sits beside the wordmark in the body face, hidden on phones narrower than 400px where the row has no room, and repeats in the manifest and README. It is about the person, not the app: the fire is theirs, the app only helps keep it.

## Import

Settings offers Import from JSON next to Export. The file is checked field by field: dates must be real dates, tasks must have text, anything malformed is dropped and the count is shown. Then a three-way dialog: Cancel, Merge, Replace. Merge unions days and tasks by text, Fuel by text, and keeps the higher best streak. Replace keeps only the consent and theme. Replace is the ember button because it discards data.

## Install

Ember installs as an app through the web app manifest and a service worker. The Install row in Settings says the right thing for the browser it is in: a button where the browser offers one, the Share then Add to Home Screen steps on iPhone, a menu hint elsewhere, and "Installed" once it is. The icon is the flame in paper on an ember square.

## History

A calendar, one month at a time, because a month is how people already think about the past. Earlier and Later controls either side of the month name; every day is a numbered cell whose fill is its state: filled ember when everything was done, an ember ring when some was, a muted ring when none was, plain when nothing was listed, faint when the day is still ahead. Today wears an outline. A key under the grid says what the fills mean. Tapping a day opens its page, grouped into done and not done, with a link back to the month. The grid is one Tab stop; arrows walk the days, PageUp and PageDown change month.

## Settings

Titled groups: Theme, Install, Your data. Each title is in the display face, in ink, and each group is separated by a hairline, so the titles cannot be mistaken for the muted body text under them. On wide screens the title sits in a left column beside its group; on phones it sits above.

## Today

A date line at the top, in words, with the day's count beside it ("Saturday, 13 September. 3 left."). The streak is stated once, in the hearth, so no two lines can disagree about it. There is no Clear done: the row cross is the one way to remove, and a day's record is never rewritten after the fact.

## Keyboard

Finishing a task by keyboard keeps focus on that task after the list re-renders. Removing one moves focus to the next row, or the previous, or the input. A tab left open past midnight rolls the day by timer.

## Streak on day one

A day that was fully done stays lit for streak purposes even if a task is added afterwards: the flame goes warm, not out, and the count holds. Without this, day one, the day that decides whether a person comes back, would show "No streak yet" the moment they added one more thing.
