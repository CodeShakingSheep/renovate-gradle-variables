# renovate-gradle-variables

This is a minimum reproduction repository to demonstrate the creation of multiple PRs with same changes in `build.gradle` when using variables in Gradle build script. See the corresponding issue [here](https://github.com/renovatebot/renovate/discussions/26437). To reproduce just run renovate on this repository.

## Current behavior

Two PRs are being created both containing the same change (bumping `ext.kotlin_version` variable to the latest Kotlin version).

- Update dependency org.jetbrains.kotlin:kotlin-stdlib to v1.9.22
    - renovate-bot wants to merge 1 commits from renovate/kotlin-monorepo into master
- Update plugin org.jetbrains.kotlin.jvm to v1.9.22
    - renovate-bot wants to merge 1 commits from renovate/kotlin_version into master

Both PRs contain the exact same change bumping ext.kotlin_version from `1.9.21` to `1.9.22`.

## Expected bahvior

Only one common PR should be created bumping `ext.kotlin_version` variable to the latest Kotlin version.
