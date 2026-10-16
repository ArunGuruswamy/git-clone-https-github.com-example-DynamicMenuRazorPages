# v3.1.1 validation report

Actual MSTest execution: **157 passed, 0 failed, 0 skipped**, using the real NuGet adapter on Linux. Release compilation passed with SonarAnalyzer.CSharp and warnings as errors. Corrected async-inclusive coverage: **95.89% line, 89.79% branch**.

New regression checks confirm all four supplied PR 55783 diagnostic IDs block changed source and are explicitly requested in the local configuration. A real disposable C# build also reproduced **CS0169, CS8618, S1144 and S3242**, and the local gate reported all four as failures. See pr55783-regression-fails.txt. The synthetic fixture uses a simple element type; the actual GraphQL-generated element interface is unchanged in the real repository because that repository's current source was not available here.

A corrected synthetic fixture removes the unused dependency, uses initialized meaningful state, changes the collection parameter to IReadOnlyCollection, and tests its behavior. The corrected fixture passed: 3 tests, 100% new-code coverage and 0 local analyzer issues. See pr55783-regression-fixed.txt for the actual outcome. These are agent regression fixtures, not changes to the live Akzo application.

CS8618 can only be produced when the target's nullable analysis is enabled. The generated diagnostic configuration requests warning severity; it does not silently enable nullable warnings across legacy projects. Original historical comment status does not prove whether the issue persists or is fixed on the latest PR iteration.

Inherited v3.1.0 capabilities were validated with the same underlying tests: source-bound verification/review, real Git commits and preservation/rejection cases, exact Sonar task-to-analysis lookup via controlled HTTP responses, scanner 10.4.1 installation, real local analyzer smoke tests and package installation. The v3.1.1 package installation is checked separately in package-install.txt and package-assets.txt.

**Not executed:** live Sonar server scan, Windows WPF desktop dialog, Windows setup wizard and live Visual Studio/Copilot independent-review invocation. These still require the user's Windows/Sonar pilot. No access to or changes in live PR 55783 were made.

Coverage is not proof of full requirements correctness. CompilerGeneratedAttribute remains removed from the inherited coverage exclusion so async method bodies are measured. Historical sample files are not this release's validation.
