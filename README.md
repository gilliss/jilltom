# Wedding Website

A wedding website based on Ram Patra's `wedding-website` project.
https://github.com/rampatra/wedding-website
http://wedding.rampatra.com/

# Steps
1. Downloaded `wedding-website` repo
2. Removed `.github` file
3. Edited `README.md` file
4. Edited `CNAME` file
5. Edited index.html
6. Changed .png images in browserconfig.xml and manifest.json
7. Changed .jpg hero image in styles.scss
  * It seems styles.scss must be compiled
  * $ cd jilltom/
  * $ npm install
  * $ gulp
    * 'command not found: gulp'
    * https://stackoverflow.com/questions/22224831/after-installation-of-gulp-no-command-gulp-found
  * $ npm install --global gulp-cli # needed sudo
  * $ gulp
    * 'Node Sass does not yet support your current environment'
    * https://stackoverflow.com/questions/37324519/node-sass-does-not-yet-support-your-current-environment-linux-64-bit-with-false
    * https://stackoverflow.com/questions/60087434/macos-catalina-fse-node-cannot-be-opened-because-the-developer-cannot-be-ver
  * $ npm rebuild node-sass
8. Push an existing repository from the command line to GitHub
  * Create new empty repo on GitHub
  * $ git remote add origin https://github.com/gilliss/jilltom.git
  * $ git branch -M main
  * $ git push -u origin main
9. Setup GitHub pages
  * Go to repo's Settings >> Pages
  * Set source to main branch's "/ (root)" directory
10. Get custom domain name
  * https://github.com/sjmeijer/mootmeijer has notes on this
  * https://domains.google/

# Notes
* You can generate the Uber deeplink here
  * https://developer.uber.com/products/ride-requests
* Google Maps directions deeplink instructions here
  * https://developers.google.com/maps/documentation/urls/get-started#directions-action
