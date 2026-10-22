<img src="icon.png" width="128" height="128" alt="Curfew icon">

# Curfew

A macOS app that opens and closes other apps at times you choose.

Curfew is a setup tool. Open it to change a schedule, then quit. macOS runs the
schedules through launchd, so Curfew does not stay open in the background.

## What it does

**Apps:** Add an app and set the times you want it opened and closed, and the
days that applies to. It can open only, close only, or both. Closing either
asks the app to quit politely, like ⌘Q, or forces it if it refuses. Closing can
also take the app out of the Dock, for something you'd rather not have on show.

**Skip Days:** Dates when apps are left alone. They live in named calendars,
such as school or work, and each app picks which it follows. One app can
pause for school while another pauses for work. Import a `.ics`, or add dates
by hand.

## Permissions

Automation lets Curfew ask an app to quit normally instead of force-quitting
it. Curfew still works without this permission, and apps set to Force Quit do
not need it.

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

Curfew checks this repository for updates when it opens. It asks before
downloading or installing anything.

## Source

The source is in a private repo. This one holds the builds.

## Bugs

Open an [issue](../../issues). This has run mostly on my own Mac, so real
reports are useful.
