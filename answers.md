# Frontend Guidelines Questionnaire, Answered for Whiteboard
A one-page questionnaire to help your team establish effective frontend guidelines, so that you can write consistent & cohesive code together.

## HTML
### HTML Principles
- **What are some general principles your team should follow when writing HTML?**
  - Start by writing a complete document that makes sense without style. You should be able to identify the content and sections by reading this document.
  - Order of operations, typically: HTML, SCSS, then JS
    - This is only for front-end marketing pages
    - For pages with highly interactive elements, it still makes sense to do this order, but it's possible
      to take the HTML and sometimes the CSS and port it into React.js
  - 


### HTML Tools
- **Are you using an HTML preprocessor** *(such as [HAML](http://haml.info/), [Jade](http://jade-lang.com/), etc)*?
  - We use ERB and HAML in our Rails applications
  - In Wordpress, we optionally use Twig with a custom version of the Timber base theme
  - Codepen demos can use any of the provided preprocessors
- **Are you using a templating engine** *(such as [Mustache](https://mustache.github.io/), [Handlebars](http://handlebarsjs.com/), etc)*?
  - For JavaScript templating, we use Handlebars and and the built-in templating provided by React.js
- **Does your backend architecture influence the frontend markup in any way** (for example, WordPress will add `wp-paginate` to a class in your markup)? If so, can you highlight these conventions? 

### HTML Style
- **Spaces or Tabs?**
  - Spaces
- **What does HTML commenting look like?** 
  - All HTML comments should exist in this format: <!-- Here is my comment. -->
    - If the comment is multiline, the Opening and closing comment tags should be on their own lines:
      ```
      <!--
        Here is my multiline comment.
        It has many lines.
      -->

---------------

## CSS 

### CSS Principles
- **What are some general principles your team should follow when writing CSS?** *(For example, modularity, avoiding long selector strings, etc. See [these](http://cssguidelin.es/) [resources](http://www.yellowshoe.com.au/standards/#css) [for](http://manuals.gravitydept.com/code/css) [inspiration](http://codeguide.co/#css))*
  - CSS should be easily read by any party approaching the application.
  - CSS should be separated by the "content pattern" and "visual pattern", with preference towards the visual pattern first.
  - Atomic classes are acceptable for often-used atomic rules. Example: clearfix, padding top, column classes
  - Atomic classes should not be made for *every* rule; use discretion, and impose limits for this based on visual patterns.


### CSS Methodology
- **Is your team using a CSS methodology** *(such as [SMACSS](https://smacss.com/), [BEM](https://en.bem.info/method/), or [OOCSS](http://oocss.org/)*? If yes, where is the documentation for that methodology?
- **Are you deviating from the methodology in any way?** If so, can you highlight these conventions?

### CSS Tools
- **Is the team using a preprocessor** *(such as [Sass](http://sass-lang.com/) or [Less](http://lesscss.org/))*?
- **What are the guidelines for using that preprocessor** *(check out [Sass Guidelines](http://sass-guidelin.es/) for inspiration)*?
- **Are you using a CSS base** *(such as [Normalize](https://necolas.github.io/normalize.css/) or a [reset](http://meyerweb.com/eric/tools/css/reset/))*?
- **Are you using any CSS postprocessors** *(such as Prefixfree or [Autoprefixer](https://github.com/postcss/autoprefixer))*?
- **Are there specific CSS techniques you're utilizing** *(such as [critical CSS](https://www.smashingmagazine.com/2015/08/understanding-critical-css/))*?

### CSS Frameworks
- **Is the team using a framework** *(such as [Bootstrap](http://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/))*? If yes, where is the documentation for that framework?
- **Are you deviating from the framework in any way?** If so, can you highlight these conventions?

### CSS Style
- **Spaces or Tabs?**
- **Spacing around rules?**
- **[Grouping](https://smacss.com/book/formatting#grouping) properties?**
- **What does CSS commenting look like?** 

---------------

## JavaScript

### JavaScript Principles
- **What are some general principles your team should follow when writing JavaScript?** *(See [these](https://github.com/airbnb/javascript) [resources](https://github.com/rwaldron/idiomatic.js) for [inspiration](https://github.com/styleguide/javascript))*


### JavaScript tools
- **Are you using a JavaScript framework** *(such as [jQuery](http://jquery.com/), [Ember](http://emberjs.com/), [Angular](https://angularjs.org/), etc)*?
- **Where is the documentation for those frameworks?**
- **Are you using any polyfills or shims** *(such as [any of these](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills))*?
- **What third-party scripts are dependencies for your project** *(such as scripts for form validation, graphs, animation, etc)*?

### JavaScript Style 
*(See [these](https://github.com/airbnb/javascript) [resources](https://github.com/rwaldron/idiomatic.js) for [inspiration](https://github.com/styleguide/javascript))*
- **Spaces or Tabs?**
- **What does JS commenting look like?** 
- [What patterns are you following](https://addyosmani.com/resources/essentialjsdesignpatterns/book/)?

---------------

## Tooling
- **Are you using a task runner** *(such as [Grunt](http://gruntjs.com/) or [Gulp](http://gulpjs.com/))*?
- **Are you using a dependency manager** *(such as [Bower](http://bower.io/) or [Composer](https://getcomposer.org/))*
- **Are you using any scaffolding tools** *(such as [Yeoman](http://yeoman.io/))*
- **Are you using any tools to reinforce frontend style** *(such as [Editor Config](http://editorconfig.org/) or [linters](https://github.com/CSSLint/csslint))*?
- **Are any other specific pieces of software that are needed to work on this project?**

---------------

## Version control
- **What version control system are you using for your frontend code** *(such as [Git](https://git-scm.com/) or [Subversion](https://subversion.apache.org/))*?
- **Where is your version-controlled code hosted** *(such  as [Github](https://github.com/) or [Bitbucket](https://bitbucket.org/))* ?
- **Do you use a version control workflow** *(such as [gitflow](http://nvie.com/posts/a-successful-git-branching-model/), [centralized](https://www.atlassian.com/git/tutorials/comparing-workflows/centralized-workflow), [feature-branch](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow), etc)*?
- **Who's responsible for managing and governing the version controlled code?**?
- **Where are issues tracked**?

-----------

## Support and Optimization
It's important to recognize the difference between ["support" and "optimization"](http://bradfrost.com/blog/mobile/support-vs-optimization/). You should do your best to support as many environments as possible while simultaneously optimizing for the environments that make the most sense for your business and users. 

- **What browsers are you *optimizing* for?** 
- **What devices are you *optimizing* for?** 
- **Are you using a [graded browser support](https://github.com/yui/yui3/wiki/Graded-Browser-Support) system?**
- **Are there specific components that require [more specific grading](https://www.filamentgroup.com/lab/grade-the-components.html)?**

-----------

## Documentation
- **Are you using a [pattern library tool](http://styleguides.io/tools.html) to document your front-end architecture**?
- **Where does your documentation live**? What are the links to the documentation?
- **Who's responsible for maintaining and governing the documentation**?
- **What happens when the guidelines are updated**?

-----------

*Feel free to modify or extend (such as adding specific sections for performance, accessibility, etc) this document for your own organization's needs. For questions, comments, additions, and corrections, please open an issue on Github and/or reach out to [@brad_frost](https://twitter.com/brad_frost) on Twitter.*
