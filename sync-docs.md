# Mapbox Sync Tool Docs
Sync styles and assets between Mapbox Studio and GitHub

### 1. Getting started
To get started syncing styles, click the **Log In** button under the **Sync to GitHub** section of the Mapbox Studio menu. You will be redirected to GitHub's login page. (After logging in you will redirect back to Mapbox Studio!)

<img src="/img/sync-log-in.jpg" width="250px"/>

### 2. Link your style to a GitHub repo
Your menu will now show your GitHub username and a new option to link a repository to your current style. Click on **Link repository**. This will prompt a modal to open, listing your GitHub repos. Select an existing repo, or select **Create New Repo**.

<img src="/img/link-repo.jpg" width="250px"/>

### 3. Push changes to GitHub
As you work on your style, any time your files in Mapbox Studio have new changes that have not yet been committed to the linked repo, the **Push** button will be active. Click on it to push changes to GitHub. You will be prompted for a commit message. (These messages are a good way to keep track of changes you have made since your last commit.)

<img src="/img/sync-push.jpg" width="250px"/>

### 4. Pull styles from GitHub
If you make changes to your style in your GitHub repo (for instance, by merging a pull request), the **Pull** button will be active. Click on it to pull changes from GitHub into Mapbox Studio. (Pulling from GitHub will replace your style's json file.)

<img src="/img/sync-pull.jpg" width="250px"/>
