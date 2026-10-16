# Akzo SDD Agent releases

## v3.1.1

C# SDD agent for Visual Studio / GitHub Copilot, with automatic SonarScanner setup, source-bound verification/review, and a final Windows local-commit dialog. Push, PR creation and merge remain manual.

- [Download the complete v3.1.1 package](releases/Akzo-SDD-Agent-v3.1.1.zip)
- [Download the interactive installation guide](releases/Akzo-SDD-Agent-v3.1.1-Guide.html) — download the raw HTML and open it locally in your browser. Enter your extracted package path, repository path and project type to generate copyable PowerShell installation and verification commands. GitHub's HTML file viewer does not run the guide.
- [SHA-256 checksum](releases/Akzo-SDD-Agent-v3.1.1.zip.sha256)
- [Engine test report](releases/Akzo-SDD-v3.1.1-Test-Report.md)

Extract the entire ZIP before running setup. No credentials belong in the guide or repository. The guide generates commands locally and cannot verify your folders or execute the installer.

Validation: 157 actual MSTest tests passed; real-build regression reproduced and rejected CS0169, CS8618, S1144 and S3242. The corrected synthetic fixture passed. The interactive guide was tested in Chromium, including command generation, copying, quoting, validation and responsive layout. Windows/Visual Studio interaction and a live scan against your Sonar project still need a pilot. Automatic independent reviewer invocation depends on the Copilot host's supported tools.

## Earlier artifact

- [Akzo SDD Development Builder v2.5.2](releases/Akzo-SDD-Development-Builder-v2.5.2.zip)
