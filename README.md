# nudge


Nudge is an multi-linguistic application, offering custom user deferrals, which strongly encourages macOS updates. Written in Swift 5.5 and SwiftUI 5.2, Nudge will only work on macOS Big Sur 11 and later.

## Nudge Functionality Overview
Nudge consists of the following three components:

1. Nudge.app installed to /Applications/Utilities/Nudge.app
2. A LaunchAgent installed to /Library/LaunchAgents (co.c3.nudge.plist)
3. A Preference file, either in JSON or mobileconfig format

Rather than trying to install updates via the macOS built-in softwareupdate binary, Nudge prompts users to install updates via Apple approved/tested methods: System Preferences > Software Update and major application upgrades via the standalone macOS installer (Ex: Install macOS Monterey.app).


## JSON Support
Nudge has support for both remote JSON and local JSON.

Nudge will look for local JSON located at /Library/Preferences/com.github.macadmins.Nudge.json.

Using the -json-url argument
Remote JSON
To use a remote JSON file, simply pass the -json-url argument.

Note: Spaces must be converted to %20, just as a standard URL. (This is required both for remote and local assets.)

The following example uses our remote JSON included in this GitHub repository.

```bash
/Applications/Utilities/Nudge.app/Contents/MacOS/Nudge \
-json-url \
"https://raw.githubusercontent.com/C3-Creative-Code-and-Content-GmbH/nudge/main/nudge.json"
```
