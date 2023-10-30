# auto-stash
Script for enabling you to move between branches without thinking about stashing and remembering to unstash what you were working on last on each branch. Also includes a script for listing recent branches and choosing which to move to.


# Setup
- Clone or save this repo somewhere
- Add the following lines to your ~/.bash_profile, ~/.zprofile, or whatever you are using for your terminal configs:

    ```bash
    AUTO_STASH_PATH="/PATH_TO_REPO/auto-stash"
    alias recentBranches="python $AUTO_STASH_PATH/git-recent-branches"
    alias sw="python $AUTO_STASH_PATH/git-sw"
    alias rr="recentBranches" # lazy
    ```

- Replace `/PATH_TO_REPO` with the actual path to this repo.
- Source your changes (`source ~/.zprofile`) or open a new terminal.

## Usage:
- Use 'sw BRANCH_NAME' to make git automatically:
    - 1. Stash your current changes and save it with a code to pick it up later
    - 2. 'git switch BRANCH_NAME'
    - 3. Check out the optional changes that were auto-stashed last time you were on this branch
- Use recentBranches without any other flag to see which branches you used last
    - And use a flag with the chosen number from the list to use the 'sw' script on this branch, autostashing and checking it out. 
    - E.g. 'rr 1' with this setup will check out the branch you last.


Credit to https://gist.github.com/mgaitan for original versions