# git-gitkeep-hook

Problem: you want to version control a directory tree with empty directories

Solution: use the `pre-commit` hook to add `.gitkeep` files to every directory within the tree

## Scripts

This repository contains two scripts, found in the `scripts` subdirectory.

The `pre-commit` script will add `.gitkeep` files to every directory within the paths specified in the `directories.lst` file. The `directories.lst` file should be kept at the root of the repository.

The `post-commit` script will remove `.gitkeep` files from the directories within the paths specified in the `directories.lst` file. It performs the opposite operation for the `pre-commit` script.

A downside to using the `post-commit` script is that all versioned `.gitignore` files will be marked as deleted by `git status`. The `post-commit` script may be omitted in certain use cases.

## Usage

Copy the `pre-commit` script into the `./.git/hooks` directory of your repository.