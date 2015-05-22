# Summary

Write user stories in Markdown, list the implementation tasks for each (with estimation range),
publish the interactive estimation document.

# Usage

Clone this repository into a directory of a new estimation project

    $ git clone https://github.com/ikr/estimates-template.git ./estimates-foobar
    $ cd ./estimates-foobar
    $ rm -rf ./.git

Describe your estimation project in the `./package.json` properties. Then, install the npm
dependencies

    $ npm install

Rename `./story/one` and `./story/two` into something relevant to your problem domain, and register
the new names in the `./content.js` file.

Then, by analogy, add more story directories.

When done, build the interactive estimation document

$ npm run build

Now it can be Web-published, with the `./build/index.html` as the entry point. Here's a sample Nginx
configuration snippet

    location /estimates-foobar/ {
        alias /var/www/example.com/estimates-foobar/build/;
    }

defining the `http://example.com/estimates-foobar/` route.