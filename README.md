# Curfew

A macOS app that opens and closes other apps at times you choose.

It's a **setup tool, not a background app**. Open it when you want to change
something, then quit. The schedules keep running because they're handed to
macOS itself (launchd), not kept alive by Curfew. Nothing of ours runs when the
window is closed.

## What it does

**Apps** -- add an app and set the times you want it opened and closed, and the
days that applies to. It can open only, close only, or both. Closing either
asks the app to quit politely, like ⌘Q, or forces it if it refuses. Closing can
also take the app out of the Dock, for something you'd rather not have on show.

**Skip Days** -- dates when apps are left alone. They live in named calendars --
a school one, a work one -- and each app picks which it follows, so one app can
pause for school while another pauses for work. Import a `.ics`, or add dates
by hand.

## Permissions

Automation, optionally -- it's what lets Curfew quit an app politely instead of
force-killing it. Without it nothing breaks; Curfew still shuts apps down
cleanly, just not by the polite route. Apps set to "Force quit" never need it.

## Installing

Download the zip from the [**Releases page**](../../releases/latest), unzip it,
and drag **Curfew.app** into your Applications folder.

macOS will then refuse to open it, most likely claiming the app **"is damaged
and can't be opened."** It isn't damaged. That is what macOS says about any app
not signed with a paid Apple developer certificate. To clear it, run this once
in Terminal:

```
xattr -dr com.apple.quarantine /Applications/Curfew.app
```

That removes the "downloaded from the internet" flag. It's a standard macOS
command and worth looking up rather than taking my word for it. After that the
app opens normally for good.

**Apple silicon only** (M1/M2/M3/M4). It will not run on an Intel Mac.

## Updates

Curfew does not update itself. Watch this repo to hear when a new version lands.

## Source

The source is in a private repo. This one holds the builds.

## Bugs

Open an [issue](../../issues). This has run mostly on my own Mac, so real
reports are useful.
