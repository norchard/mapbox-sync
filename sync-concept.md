# Mapbox Sync Tool

## Research
Current workflow to push to GitHub:
1. Download style and assets
2. Move style into git repo
3. Add remote GitHub repo
4. Push changes to GitHub

Current workflow to pull from GitHub:
1. Pull style from Github into local repo
2. Use "replace style" menu option to replace style json file (*is it possible to replace assets?*)

#### Conclusions and objectives
- Moving files around breaks up workflow and is tedious
- Designers should be able to sync styles without leaving Mapbox Studio or having to know complex git concepts

## Concept
*Assuming access to Mapbox Studio application internals*

### Workflow:
#### 1. User logs in to GitHub account
  - [Use OAuth Web Application Flow](https://developer.github.com/apps/building-integrations/setting-up-and-registering-oauth-apps/about-authorization-options-for-oauth-apps/):
    - Users are redirected to request their GitHub identity
    - Users are redirected back to Mapbox Studio by GitHub with access token
    - Write token to database so user remains logged in
    - Mapbox Studio Sync Tool will access GitHub API with the user's access token
#### 2. User selects target GitHub repo for current style
  - [Use GitHub API to list user repos](https://developer.github.com/v3/repos/#list-user-repositories)
  - [Use GitHub API to create a new repo](https://developer.github.com/v3/repos/#create)
#### 3. User can **push** commits to GitHub with the click of a button
  - [Use GitHub API to create new commit](https://developer.github.com/v3/git/commits/#create-a-commit)
#### 4. User can **pull** styles from GitHub with the click of a button
  - [Use GitHub API to download files](https://developer.github.com/v3/git/trees/#get-a-tree-recursively)


### User Interface
Integrated into MapBox Studio style menu, for easy discoverability and minimal workflow disruption

<img src="/img/sync-push.jpg" width="250px"/>


#### Additional thoughts:
- Should add error handling in case GitHub API is unresponsive or other bugs
- Should add branch selection after repo selection
- Another option would be to create an *opt-in* tool for GitHub tracking and automatically push changes every time a style is "published" (auto-generate commit messages based on style changes)
  - To minimize API calls, maybe commits should be made in batches at a set interval, rather than every time the designer pushes changes?
