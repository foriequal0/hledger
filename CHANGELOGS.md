# Changelogs

Always maintain changelogs in master branch (not in release branches).

**Frequently**, especially after merging changes, and before cherry picking into release branch:

- dry run: `./Shake changelogs -n`
- add new changes: `./Shake changelogs`
- edit
  - drop things
  - move things
  - Add headings: Features, Improved, Fixes
  - rewrite things
  - format ([#ISSUE](https://github.com/simonmichael/hledger/issues/), AUTHOR) on its own line
- commit: `./Shake changelogs -c`

**After cherry-picking** changes to a release branch:
- in the master branch changelogs, move the corresponding changelog items under a pending release heading,
  creating that when necessary:
    ```
    # LATESTHASH

    ...CHANGES ONLY IN MASTER...

    # NEXTVER unreleased

    ...CHANGES CHERRYPICKED INTO RELEASE BRANCH...

    # LASTVER YYYY-MM-DD
    ```

**At release:**

- do final update/edits; check organisation, wording, formatting, issue links
- replace "unreleased" with the release date
- copy the new sections from master changelogs to release branch changelogs
