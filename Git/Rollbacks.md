### List of good commands that I use to rollback


* Git revert --no-commit -m 1 `<oldest-hash>..HEAD`

    This will revert all commits including merges from oldest-hash to current HEAD. Won't rewrite history and won't need others to rebase their branches with production.
    In case of any conflicts, just accept current (which will be production).
