
# zeus-hosting

Mock web hosting company website built with Foundation 6 and Sass.

This project was bootstrapped with Foundation's [ZURB Template](https://foundation.zurb.com/sites/docs/starter-projects.html).

Here's how I published this project to GitHub Pages:
1. Added a `homepage` property in package.json and committed the change.
2. Added a `docs` directory in the root directory.
3. In my GitHub repository's settings, I enabled GitHub Pages publishing and set the source to the master branch /docs folder.
3. In package.json, I changed the `"scripts"` key `"build"` from `"gulp build --production"` to `"gulp build --production && rm -rf docs && mv dist docs"`. `&&`, the logical AND operator, strings commands together, executing successive commands if previous ones succeed. So once the production build is complete (which creates a `dist` folder), `rm -rf docs` is executed, which deletes the existing `docs` directory and all of its contents, then `mv dist docs` is executed, which renames `dist` as `docs`. (Note: `"gulp build --production && rm -rf docs && mv dist docs"` resulted in the error `mv: cannot move 'dist' to 'docs/dist': Directory not empty`, which is why I'm removing `docs` first.)
4. Ran `npm run build`.