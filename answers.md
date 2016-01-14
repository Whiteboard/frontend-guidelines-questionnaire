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
  - Use the most appropriate and semantic tag that you can for a given scenario
  - Millions of developers suffer from `<div>`-phobia. Don't join them.


### HTML Tools
- **Are you using an HTML preprocessor** *(such as [HAML](http://haml.info/), [Jade](http://jade-lang.com/), etc)*?
  - We use ERB and HAML in our Rails applications
  - In Wordpress, we optionally use Twig with a custom version of the Timber base theme
  - Codepen demos can use any of the provided preprocessors
- **Are you using a templating engine** *(such as [Mustache](https://mustache.github.io/), [Handlebars](http://handlebarsjs.com/), etc)*?
  - For JavaScript templating, we use Handlebars and and the built-in templating provided by React.js
- **Does your backend architecture influence the frontend markup in any way** (for example, WordPress will add `wp-paginate` to a class in your markup)? If so, can you highlight these conventions? 
  - We do use WordPress, and in many instances WordPress does in fact add classes to the markup. However, we try to avoid using WordPress classes in our stylesheets, so this typically doesn't affect us.
    - The obvious caveat is that it may be easier to accidentally collide with WordPress classes and style multiple things. Be specific with your naming structure and aware of this nuance.

### HTML Style
- **Spaces or Tabs?**
  - Spaces
- **What does HTML commenting look like?** 
  - All HTML comments should exist in this format: <!-- Here is my comment. -->
    - If the comment is multiline, the Opening and closing comment tags should be on their own lines:
      ```html
        <!--
          Here is my multiline comment.
          It has many lines.
        -->
      ```

---------------

## CSS 

### CSS Principles
- **What are some general principles your team should follow when writing CSS?** *(For example, modularity, avoiding long selector strings, etc. See [these](http://cssguidelin.es/) [resources](http://www.yellowshoe.com.au/standards/#css) [for](http://manuals.gravitydept.com/code/css) [inspiration](http://codeguide.co/#css))*
  - CSS should be easily read by any party approaching the application.
  - CSS should be separated by the "content pattern" and "visual pattern", with preference towards the visual pattern first.
  - Atomic classes are acceptable for often-used atomic rules. Example: clearfix, padding top, column classes
  - Atomic classes should not be made for *every* rule; use discretion, and impose limits for this based on visual patterns.
    - For example, if possible, avoid classes that modify individual aspects of type styles (color, size, weight), and instead create classes for complete type styles.
    - This is a pattern that is broken by major frameworks like Bootstrap, so if you do end up using these classes, do so knowing that they might make your designed outcome inconsistent. This is bad.


### CSS Methodology
- **Is your team using a CSS methodology** *(such as [SMACSS](https://smacss.com/), [BEM](https://en.bem.info/method/), or [OOCSS](http://oocss.org/)*? If yes, where is the documentation for that methodology?
- **Are you deviating from the methodology in any way?** If so, can you highlight these conventions?
  - Yes. We are using BEM, mixed with some of the concepts from SMACSS for state classes and mixin classes.
  - A simple example can be found in our column classes, which look like this:
  - `col-md-4`, `vp-xs-bottom-4`, `vm-xl-top-9`
  - When in doubt, follow BEM.
  - Consider using AMCSS when defining BEM modules

### CSS Tools
- **Is the team using a preprocessor** *(such as [Sass](http://sass-lang.com/) or [Less](http://lesscss.org/))*?
  - Yes. We exclusively use the SCSS syntax of Sass.
- **What are the guidelines for using that preprocessor** *(check out [Sass Guidelines](http://sass-guidelin.es/) for inspiration)*?
  - Avoid heavy nesting.
  - Follow order rules.
  - Avoid `extends` statements unless you have specifically defined a silent class, which helps avoid unnecessarily complex nested class selectors.
  - Take a look at [Sass Guidelines](http://sass-guidelin.es/) for some general thoughts on Sass.
  - Follow the official [CSS Style Guide](https://github.com/Whiteboard/kb/wiki/Whiteboard-Style-Guide:-CSS)
- **Are you using a CSS base** *(such as [Normalize](https://necolas.github.io/normalize.css/) or a [reset](http://meyerweb.com/eric/tools/css/reset/))*?
  - We are currently using Normalize, though this isn't necessarily the only option that accomplishes the goal.
- **Are you using any CSS postprocessors** *(such as Prefixfree or [Autoprefixer](https://github.com/postcss/autoprefixer))*?
  - We do use Autoprefixer via Gulp, and minifying in the same process. This is specific to our WordPress sites.
- **Are there specific CSS techniques you're utilizing** *(such as [critical CSS](https://www.smashingmagazine.com/2015/08/understanding-critical-css/))*?
  - We are not using any other specific techniques, though we have experimented with echoing the contents of a CSS file into the page to test the effect on load speeds. In many cases, this has proven to be worthwhile, and it is now the default for the homepage of Launchframe-driven sites.
  - No single strategy will be perfect for every site; when in doubt, test 3 options.

### CSS Frameworks
- **Is the team using a framework** *(such as [Bootstrap](http://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/))*? If yes, where is the documentation for that framework?
  - We are loosely using [Bootstrap](http://getbootstrap.com/).
- **Are you deviating from the framework in any way?** If so, can you highlight these conventions?
  - The framework is brought in via SCSS, so deviation is fully available and encouraged. Not every part of Bootstrap is necessary; cut as many pieces as possible for the sake of performance.

### CSS Style
- **Spaces or Tabs?**
  - Spaces; enable your editor to convert tabs to 4 spaces.
- **Spacing around rules?**
  - Covered in the Style Guide.
- **[Grouping](https://smacss.com/book/formatting#grouping) properties?**
  - Covered in the Style Guide.
- **What does CSS commenting look like?** 
  - Any valid CSS comments are acceptable, except single-line comments on the same line as active code.

---------------

## JavaScript

### JavaScript Principles
- **What are some general principles your team should follow when writing JavaScript?** *(See [these](https://github.com/airbnb/javascript) [resources](https://github.com/rwaldron/idiomatic.js) for [inspiration](https://github.com/styleguide/javascript))*
  - When in a loop, set variables to avoid unnecessary function calls.
  - TBD


### JavaScript tools
- **Are you using a JavaScript framework** *(such as [jQuery](http://jquery.com/), [Ember](http://emberjs.com/), [Angular](https://angularjs.org/), etc)*?
  - Whiteboard uses jQuery and React
- **Where is the documentation for those frameworks?**
  - Google. :)
- **Are you using any polyfills or shims** *(such as [any of these](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills))*?
  - We do use Modernizr. We do not use polyfills unless necessary. We do use Babel to transpile es6 syntax.
- **What third-party scripts are dependencies for your project** *(such as scripts for form validation, graphs, animation, etc)*?
  - No third-party scripts are universal. We often depend on jQuery, Slick.js, and React, but some site that Whiteboard launches have no JavaScript.

### JavaScript Style *TBD*
*(See [these](https://github.com/airbnb/javascript) [resources](https://github.com/rwaldron/idiomatic.js) for [inspiration](https://github.com/styleguide/javascript))*
- **Spaces or Tabs?**
- **What does JS commenting look like?** 
- [What patterns are you following](https://addyosmani.com/resources/essentialjsdesignpatterns/book/)?

---------------

## Tooling
- **Are you using a task runner** *(such as [Grunt](http://gruntjs.com/) or [Gulp](http://gulpjs.com/))*?
  - Yes (Gulp)
- **Are you using a dependency manager** *(such as [Bower](http://bower.io/) or [Composer](https://getcomposer.org/))*
  - Yes (Bower, Ruby Gems, Composer, NPM)
- **Are you using any scaffolding tools** *(such as [Yeoman](http://yeoman.io/))*
  - Not in the main line of front-end work, though Rails's built-in generator is used heavily for Rails projects.
- **Are you using any tools to reinforce frontend style** *(such as [Editor Config](http://editorconfig.org/) or [linters](https://github.com/CSSLint/csslint))*?
  - [SCSS-Lint](https://github.com/brigade/scss-lint) is used to validate SCSS syntax.
- **Are any other specific pieces of software that are needed to work on this project?**
  - It is a good idea to install Apache at the system level. If you are a Ruby developer (and perhaps even if you are not), install RVM.
  - If you prefer, installing rbenv is fine, but note that this may cause some differences in environments.

---------------

## Version control
- **What version control system are you using for your frontend code** *(such as [Git](https://git-scm.com/) or [Subversion](https://subversion.apache.org/))*?
  - Exclusively Git.
- **Where is your version-controlled code hosted** *(such  as [Github](https://github.com/) or [Bitbucket](https://bitbucket.org/))* ?
  - GitHub.
- **Do you use a version control workflow** *(such as [gitflow](http://nvie.com/posts/a-successful-git-branching-model/), [centralized](https://www.atlassian.com/git/tutorials/comparing-workflows/centralized-workflow), [feature-branch](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow), etc)*?
  - We currently have a relatively loose set of rules, and most work is done directly on Master.
  - Ideally, we subscribe to a very simple feature branch model proposed by GitHub.
- **Who's responsible for managing and governing the version controlled code?**?
  - Everyone owns the code.
- **Where are issues tracked**?
  - Email and TeamGridApp; Slack is used heavily internally, but TeamGrid is where most tracking occurs.

-----------

## Support and Optimization
It's important to recognize the difference between ["support" and "optimization"](http://bradfrost.com/blog/mobile/support-vs-optimization/). You should do your best to support as many environments as possible while simultaneously optimizing for the environments that make the most sense for your business and users. 

- **What browsers are you *optimizing* for?** 
  - Current versions of all major browsers, minus 2 versions.
- **What devices are you *optimizing* for?** 
  - Latest and previous versions of iPhones
  - Capable laptops from 12" to 15"
  - Project-dependent for other optimizations.
- **Are you using a [graded browser support](https://github.com/yui/yui3/wiki/Graded-Browser-Support) system?**
  - Not explicitly
- **Are there specific components that require [more specific grading](https://www.filamentgroup.com/lab/grade-the-components.html)?**
  - N/A

-----------

## Documentation
- **Are you using a [pattern library tool](http://styleguides.io/tools.html) to document your front-end architecture**?
  - Not explicitly/universally
- **Where does your documentation live**? What are the links to the documentation?
  - This document is a large part of the documentation.
  - Other documentation should be found in git history, and the individual git repositories for the given project.
  - Further documentation should be stored in Markdown files in the project.
    - In rare instances, documentation may be stored on Dropbox, in Google Drive, or in Quip. This is not ideal.
- **Who's responsible for maintaining and governing the documentation**?
  - Whoever is working on that project and that feature.
- **What happens when the guidelines are updated**?
  - They are changed in the git repository directly on GitHub, in the Whiteboard Knowledgebase.
