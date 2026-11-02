# GitHub CLI in Zed

Install GitHub CLI and sign in:

```sh
sudo pacman -S github-cli
gh auth login
```

Choose **GitHub.com**, **HTTPS**, and **Login with a web browser**, then follow the code-and-browser prompts.

Configure Git to use your GitHub CLI credentials:

```sh
gh auth setup-git
gh auth status
```

In the repository, confirm the remote and try your Git operation in Zed:

```sh
git remote -v
git push
```

If needed, set the remote to HTTPS:

```sh
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```
