How to create a Helm repo from GitHub repo
------------------------------------------

```
mkdir my-helm-chart
cd my-helm-chart
helm create my-chart
helm package my-chart
helm repo index .
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/your-repo.git
git push -u origin master

# Serve your Helm chart repository: Your Helm chart repository is now hosted on GitHub, but you need to serve the index.yaml file from a web server. You can use GitHub Pages to do this:
## Go to your GitHub repository settings.
## Scroll down to the GitHub Pages section.
## Select the branch you want to serve your Helm chart from (usually master or main).
## Click Save.

## How to find the URL Repo
# -------------------------
## 1. Go to your GitHub repository in your web browser.
## 2. Click on the “Settings” tab at the top of the repository.
## 3. Scroll down to the “GitHub Pages” section. Here, you’ll see a message like “Your site is published at https://<username>.github.io/<repository>/”. This is the URL of your GitHub Pages.

helm repo add my-repo https://yourusername.github.io/your-repo/
helm repo update

```
