# The North Face Code Challenge

> A code challenge.

To run locally:

- Clone repo locally
- `npm install`
- `npm run dev`

You shoudl then be able to view the site locally at `http://localhost:8080/`

## Notes

Couple things to be noted. First is that I stubbed out the JSON object with locally hosted assets that I have resized. Also I have chosen Vue.js for this particular code challenge because I like to use my time on these types of projects to learn something new.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

## Requirements

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

Featured Collection Page

You’ve been tasked with creating a new landing page to showcase TNF collections.  Below is a link to a JS object that’s been generated from an API response for TNF’s “Featured” pages. Use your FE development and design skills to layout a page as you see fit. Feel free to reference www.thenorthface.com for general design layouts if necessary but also feel free to use creative license.

Use the object in this [link](https://bitbucket.org/bioradical/collections-page-project/src/3e0b073714e51318e824a5d5a5a410ad91f36f7d/main.js?at=master&fileviewer=file-view-default) and create an appropriate responsive page

Please read the following carefully and let us know if you have any questions.

The Request:
-The most recent collection should be highlighted and be visually distinctive from the others.
-Each of the collections should be represented on the page.
-Reusability via templating should be considered. (If we were to request a different payload via the API, the page should be generally reproducible)
-There should be a section on the page for representation of The North Face Endurance Challenge and the Explore Fund Grant, as well as links to their respective pages. (as seen at the bottom of this page https://www.thenorthface.com/get-outdoors.html)

Constraints/Considerations
-You don’t necessarily need to use all of content provided in the object provided but every collection should be represented.
-You can use any of the content from the pages represented
-Use Helvetica with an Arial fallback for all type.
-Presume you can edit the values from the Article Search API call
(ie, you can pull down the images, reformat and then reference them locally in your build or edit/change the copy values if necessary/desired  )
-Implement for modern viewports and browsers.
-Feel free to reference www.thenorthface.com for general design guidelines if necessary
-Don’t include the navigation header or footer as currently represented on the TNF website.
-Use open source development resources as you see fit.
-Hand-off your build so that its readily viewable.

Helpful Links:
We use Adobe’s Scene7 for visual asset hosting, below is a reference for helpful commands (mostl the wid & qlt commands may be of use but not necessary)
https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/http_ref/c_command_reference.html

Lastly, don’t overthink the design, simple and clean with maybe a simple animated embellishment. The goal here is to see how you put things together in your builds. Thanks!
