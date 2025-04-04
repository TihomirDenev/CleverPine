# How to Tag a Release 🏷️

This guide provides step-by-step instructions for tagging a new release in your repository.

## Steps

### 1. Create a New Branch for the Release 🌿

- This command switches to a new branch dedicated to preparing the release.

```bash
git checkout -b release/0.24.0
```

### 2. Update the Version 🔢

- Manually change the version number in **_package.json_** and **_package-lock.json_** to the new version (e.g., 0.24.0).

### 3. Stage Changes 📦

- This command adds all changed files to the staging area, preparing them for the next commit.

```bash
git add .
```

### 4. Commit the Changes 💾

- This step records the changes you've made to the repository.

```bash
git commit -m “increase version”
```

### 5. Create the Tag 🏷️

- This command tags the latest commit with the new version number.

```bash
git tag 0.24.0
```

### 6. List All Tags 📑

- This command lists all tags in your repository, allowing you to verify the newly created tag.

```bash
git tag -l
```

### 7. Push Changes to the Remote Repository 📤

- Push the changes of the new release branch to the remote repository.

```bash
git push
```

### 8. Push Tags to the Remote Repository 🚀

- This final step pushes all local tags to the remote repository.

```bash
git push —tags
```
