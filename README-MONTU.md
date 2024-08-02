# Forked Snowplow JavaScript Tracker

Forked from: https://github.com/snowplow/snowplow-javascript-tracker

## Getting Started
1. Install nvm.
    ```
    brew install nvm
    ```
1. Use project version.
    ```
    nvm use
    ```
1. Install rush globally.
    ```
    npm install -g @microsoft/rush
    ```
1. Rush update.
    ```
    rush update
    ```
1. Rush build.
    ```
    rush build
    ```
1. Rush test.
    ```
    rush test
    ```

### Troubleshooting
You may need to remove volta from your path. It seems to install the latest node and rush doesn't like it.

## Publishing
1. Setup a [PAT](https://github.com/settings/tokens) with write packages. Copy your token.
1. Configure SSO.
1. Save the PAT in your password manager for later.
1. Run build.
    ```
    rush build
    ```
1. Commit your changes.
    ```
    git commit --no-verify
    ```
    I can't work out how to disable the git hooks.
1. Run version.
    ```
    rush version --bump --target-branch master --ignore-git-hooks
    ```
1. Build again.
    ```
    rush build
    ```
1. Run rush publish
    ```
    NPM_AUTH_TOKEN=123456 sh publish.sh
    ```
    Replace 123456 with your PAT.

Rush is designed for a CI environment and doesn't support npm login.

