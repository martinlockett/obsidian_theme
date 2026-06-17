Create a new release of the Obsidian theme by tagging the repo and pushing, which triggers the GitHub Actions release workflow.

## Steps

1. Read `manifest.json` to get the current version number.

2. Determine the new version:
   - If `$ARGUMENTS` is provided, use that as the new version (strip any leading `v`).
   - If `$ARGUMENTS` is empty, increment the patch segment (the rightmost number) of the current version by 1. For example, `1.0.3` → `1.0.4`.

3. Update `manifest.json` by setting `"version"` to the new version string.

4. Stage and commit the change: `git add manifest.json` then commit with message `Update version number`.

5. Create a git tag for the new version: `git tag <version>` (no leading `v`).

6. Push the commit and tag: `git push && git push --tags`.

7. Confirm to the user that the release has been triggered and state the new version number.
