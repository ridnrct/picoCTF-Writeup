# Commitment Issues picoCTF Write-Up

### 1. **HEAD: Pointer Git that Points to the Latest Commit**

In Git, **HEAD** is a pointer that points to the latest commit that is currently active on the branch being used.

### 2. **HEAD Points to `refs/heads/master` Containing Hash `42942c9c605b30100f5d859ef6e172027447c0db`**

In this repository, **HEAD** points to the `master` branch, which means the main active branch in the repository. This is seen in the `.git/HEAD` file, which points to `refs/heads/master`. The latest commit on this branch has the hash `42942c9c605b30100f5d859ef6e172027447c0db`.

### 3. **`git show` Command to View Detailed Information about a Commit**

The `git show` command is a very useful tool to examine the details of a specific commit. By using `git show`, you can get more information about the commit, including:
- **File Changes**: Shows the files that were changed in the commit.
- **Author**: Who made the changes.
- **Commit Date**: When the commit was made.
- **Commit Message**: A description of the commit explaining the changes made.

This command helps to verify the changes applied to the repository in more detail.

### 4. **Example Usage of `git show`**

To view the details of the commit with hash `42942c9c605b30100f5d859ef6e172027447c0db`, you can run the following command:
```bash
git show 42942c9c605b30100f5d859ef6e172027447c0db
```

## Flag
The program output prints the following flag:
```
picoCTF{s@n1t1z3_c785c319}
```
