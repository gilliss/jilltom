# Wedding Website

A wedding website based on Ram Patra's `wedding-website` project.
https://github.com/rampatra/wedding-website
http://wedding.rampatra.com/

# Setting up
1. Cloned `wedding-website` repo
2. Removed `.github` file
3. Edited `README.md` file
4. Edited `CNAME` file to be blank
5. Edited `index.html` with wedding info
  * https://developers.google.com/search/docs/advanced/crawling/block-indexing
6. Changed .png images in `browserconfig.xml` and `manifest.json`
7. Changed .jpg hero image in `styles.scss`
  * It seems `styles.scss` must be compiled
  ```
  $ cd jilltom/
  $ npm install
  $ gulp
    * 'command not found: gulp'
    * https://stackoverflow.com/questions/22224831/after-installation-of-gulp-no-command-gulp-found
  $ npm install --global gulp-cli # needed sudo
  $ gulp
    * 'Node Sass does not yet support your current environment'
    * https://stackoverflow.com/questions/37324519/node-sass-does-not-yet-support-your-current-environment-linux-64-bit-with-false
    * https://stackoverflow.com/questions/60087434/macos-catalina-fse-node-cannot-be-opened-because-the-developer-cannot-be-ver
  $ npm rebuild node-sass
  $ gulp
  ```
8. Pushed existing repository from the command line to GitHub
  * Create new empty repo on GitHub and then:
  ```
  $ git remote add origin https://github.com/gilliss/jilltom.git
  $ git branch -M main
  $ git push -u origin main
  ```
9. Setup GitHub pages
  * Go to repo's Settings >> Pages
  * Set source to main branch's `/ (root)` directory
  * https://pages.github.com/
10. Get custom domain name
  * https://github.com/sjmeijer/mootmeijer has notes on this
  * https://domains.google/
  * https://support.google.com/domains/answer/4522141?hl=en forwarding a Google domain
  * At first, I used domain forwarding, but then switched to specifying custom resource records according to GitHub's "custom domain name" instructions
    * https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
    * https://stackoverflow.com/questions/54059217/how-to-fix-domain-does-not-resolve-to-the-github-pages-server-error-in-github
    * https://support.google.com/domains/answer/10751068
    1. Created A record with apex domain (jilltom.com) as "Host name" and GitHub Pages IP addresses as "Data"
      * points "Host name" to "Data"
    2. Created AAAA record with apex domain (jilltom.com) as "Host name" and GitHub Pages IP addresses as "Data"
    3. Created CNAME record with www subdomain (www.jilltom.com) as "Host name" and the default domain (gilliss.github.io) as "Data"
      * See links above for @ and www shorthand in "Host name" field
    4. Under the GitHub repo's Settings >> Code and automation" >> Pages >> Custom domain, entered apex domain (jilltom.com) as the custom domain. Also checked the box to "Enforce HTTPS".
    5. Wait a bit for things to update and check with `dig`:
    ```
    $ dig jilltom.com +noall +answer -t A
    $ dig jilltom.com +noall +answer -t AAAA
    $ dig www.jilltom.com +nostats +nocomments +nocmd
    ```
    6. Created a TXT record to verify my custom domain name for GitHub Pages
      * https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
      ```
      $ dig _github-pages-challenge-gilliss.jilltom.com +nostats +nocomments +nocmd TXT
      ```

# Other notes
* You can generate an Uber deeplink here
  * https://developer.uber.com/products/ride-requests
* Google Maps directions deeplink instructions here
  * https://developers.google.com/maps/documentation/urls/get-started#directions-action
