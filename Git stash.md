# Git stash

    Saves your local modifications away and reverts the working directory to
    match the HEAD commit

## `git stash`

- NOTE: stash does not save the untracked files
- Stash the changes in the stash stack
- Last saved stash is at the top of the stack
- Stack starts from 0

`git stash -m | --message`

- Adds a message to the stash

`git stash --include-untracked`

- Includes untracked changes

## `git stash list <log-options>`

- Lists everything in the stage stack

## `git stash drop [stash]`

- Deletes the last stash

## `git stash show`

- Shows a list of files that has changed

`git stash show -p [stash]`

- Shows a patch of the changes

## `git stash clear`

- Removes the entire stash stack

## `git stash create [message]`

- Creates a new stash
