# My Project
A starting point for using Polymer, Firebase, Geofire, and username/provider logins.

Try it at https://app-starter-8f1a5.firebaseapp.com

## Key features
* Fully operational user-to-user messaging system that includes cloud messaging.
* Integrated permissions system based on user roles.
* List and Map view of "posts". There are two types of posts in the demo.
* Sort posts by their distance to you or another location you specify.
* Use Firebase with usernames instead of cryptic IDs.
* Site-wide theming
* Lighthouse score: 95/100

## Usage

### Initial setup
The purpose of this repo is to be used as a starting point for a new app.
A typical way to accomplish that is

1. Clone this repo into your own `app-starter` directory.

  ```
  git clone https://github.com/jifalops/app-starter.git app-starter
  ```

2. Setup the git remotes to be able to pull from this project and pull/push to your project.

  ```
  cd app-starter
  git remote rename origin app-starter
  git remote set-url --push app-starter no-pushing    # Set push url to dead end
  git remote add origin [YOUR-REPO-URL]
  ```

3. Replace some strings.
  * Replace the necessary information inside `src/app-firebase.html` to use your own Firebase info and replace the existing messaging sender ID in `firebase-messaging-sw.js`. Also set your default deploy location in `.firebaserc`.
  * Search the entire project and change `My Project` to `My Project` and `app-starter` to `app-starter` using your preferred editor or some other method. Also update the description of your project, which occurs in `index.html`, `bower.json`, `package.json`, `manifest.json`, and `README.md`.

4. Commit and push your changes.

  ```
  git add --all
  git commit -m 'Initial changes'
  git push -u origin master
  ```

5. Install dependencies.

    ```
    bower install --save
    npm install polymer-cli@next
    ```

6. Test locally, requires deploying rules first.

    ```
    firebase use dev
    ./internal/make-rules.sh
    firebase deploy --only database
    polymer serve
    ```

7. Deploy when ready.

    ```
    # Optional -- setup cloud functions to handle push notifications.
    firebase init functions

    polymer build
    firebase deploy
    ```

### Pulling in new changes
To update your existing project to use the newest version of app-starter,
merge in new changes or rebase your project on top of app-starter.

```
# If others are working from origin/master.
git merge app-starter master
git push origin master
```

```
# Only do this if nobody else is using origin/master
git pull --rebase app-starter master
git push -f origin master
```

## Contributing

1. Fork it on Github.
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## License

[Apache](https://opensource.org/licenses/Apache)
