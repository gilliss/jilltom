# Wedding Website

A wedding website based on Ram Patra's `wedding-website` project.
https://github.com/rampatra/wedding-website
http://wedding.rampatra.com/

# Getting Started
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
  * $ npm rebuild node-sass

# Notes
* You can generate the Uber deeplink here
  * https://developer.uber.com/products/ride-requests
