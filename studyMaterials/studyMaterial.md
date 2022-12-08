# Handbook  

# Table of Contents
1. [GIT](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git)
2. [HTML](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#html)
3. [CSS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css)
4. [JavaScript](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#javascript)
5. [OOP](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#oop)
6. [HTTP](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http)
7. [SEO](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#seo)
8. [Security](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#security)
9. [Bibliography](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#bibliography)  

# GIT  

<details>
    <summary>
    Table of contents
    </summary>

1. [What's GIT?](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#whats-git)
2. [What's version control?](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#whats-version-control)
3. [Most common commands](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#most-common-commands)
4. [GIT branch](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-branch)
5. [GIT tags](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-tags)
6. [GIT commits](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-commits)
7. [Stash command](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#stash-command)
8. [Hooks](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#hooks)
9. [GIT branching strategies](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-branching-strategies)
10. [GIT workflow](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-workflow)
11. [GIT merge](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-workflow)
12. [GIT rebase](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-rebase)
13. [GIT squash + merge](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git-squash--merge)

</details>

## What's GIT?
Open-source, distributed version control system.  
## What's version control?
A system that records changes to a file or set of files over time so that you can recall specific versions later.  
## Most common commands
### To create a repository
- `git init` turn an existing repository into a git repository  
- `git clone` download a repository that exists on a remote server  
### Synchronizing
- `git fetch` downloads all history from the remote tracking branches
- `git merge` combines remote tracking branch into current local branch
- `git push` uploads all local branch commits to remote servers
- `git pull` updates local current branch with all the new commits from the corresponding remote branch. It's a combination of `git fetch` and `git merge`
### Branching
- `git branch [ branch name ]` creates new branch
- `git checkout [ branch name ]` switches to the specified branch and updates working directory
- `git merge [ branch ]` combines specified branch history into the current branch
- `git branch -d [ branch name ]`  deletes the specified branch
### Make changes
- `git log` lists version history for the current branch
- `git log --follow [ title ]` lists version history for a file, including renames
- `git diff [ first branch ] [ second branch ]` shows content differences between the two branches
- `git show [ commit ]` outputs metadata and content changes of the specified commit
- `git add [ file ]` snapshots thr file in preparation for versioning
- `git commit -m "[ descriptive message ]"` records file snapshots permanently in version history  
### Redo commits
- `git reset [ commit ]` undoes all commits after [commit], preserving changes locally
- `git reset --hard [ commit ]`  discards all history and changes back to the specified commit  
## GIT branch
A pointer to changes made in a repository.
When a commit is made, Git stores a commit object* that contains a pointer to the snapshot of the content that has been staged.  A branch in Git is simply a lightweight movable pointer to one of these commits. As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, the master branch pointer moves forward automatically.  
## GIT tags
A label used to indicate a specific point in a repository as being important.  
*Note: Checking out tags puts the repository in a “detached HEAD” state, in which if you make changes, then commit those changes, the tag won’t change and the new commit  won’t belong to any branch and will ONLY be readable by the commit hash.*  
### Types of tags
- Lightweight: pointer to a specific commit, like a branch
- Annotated: objects that contain the tagger name, email, and date; they also have a tagging message
### Creating tags
- Lightweight: `git tag [ tag name ]-lw`
- Annotated: `git tag -a [ tag name ] -m [ message ]`
### Adding tags on past commits
- `git tag -a [ tag name ] [ complete or partial checksum of the commit ]`
### Pushing tags to remote
- Single tag: `git push origin [ tag name ]`
- Multiple tags: `git push origin ——tags`
### Deleting tags
- Local server: `git tag -d [ tag name ]-lw`
- Remote servers: `git push origin --delete [ tagname ]`  
## GIT commits
When you make a commit, Git stores a commit object that contains a pointer to the snapshot of the content you staged. This object also contains the author’s name and email address, the message that you typed, and pointers to the commit or commits that directly came before this commit (its parent or parents): zero parents for the initial commit, one parent for a normal commit, and multiple parents for a commit that results from a merge of two or more branches.  
## Stash command
It’s used when you want to record the current state of the working directory and the index without doing a commit, but want to go back to a clean working directory. Stashing takes the dirty state of your working directory — that is, your modified tracked files and staged changes — and saves it on a stack of unfinished changes that you can reapply at any time (even on a different branch).  
### Stash commands
### Create a stash
- `git stash`
### Create a stash including the untracked files
- `git stash -u`
- `git stash --include-untracked`
### Create a stash with the ``.ignored`` files
- `git stash -a`
### Apply latest stashed work
- `git stash apply`
### Get stash list
- `git stash list`
### Apply specific version of the stash list
- `git stash@{ [ number ] }`
### Create a branch from stash
- `git stash branch [ new branchname ]`
### Control which changes will be stashed
- `git stash --patch`  
## Hooks
Git hooks are scripts that get fired off when a certain action occurs, they are scoped to their given repository, hence, they are local and tehy’re stored in the `./git/hooks` directory. Git provides a template directory that allows the installation of hooks automatically with every git init or git clone.  
### Client-side hooks
Client-side hooks don’t get copied when a repository is cloned. They can be altered or uninstalled by the owner of a repository.  
#### Local hooks
The most useful and common local hooks are:
1. `pre-commit`
2. `prepare-commit-msg`
3. `commit-msg`
4. `post-commit`
5. `post-checkout`
6. `pre-rebase`  
Hooks 5 and 6 are useful to perform additional safety checks for git checkout and git rebase respectively. pre- hooks are used to alter the action that’s about to happen, whereas post- hooks are used for notifications.  
### Server-side hooks
They usually reside in central or remote repositories, and can be used as a way to enforce policies about commits when they’re attached to the ‘official’ repository. These hooks allow you to react to stages of the git push process.
#### Server-side hooks
* `pre-receive`
* `update`
* `post-receive`  
The pre-receive hook runs before references are updates, and can therefore be used to prevent merges, checking the user for authorization, and reject commits that don’t meet a company’s standard, whether that is the commit message or the changes that the commit is trying to push. The update hook also runs before any updates are made to the repository and is called for every ref that got pushed. Meanwhile, post-receive is called after a successful push operation, which is why this hook is commonly used to send notifications.  
## Git branching strategies
1. Use feature branches for all new features and bug fixes.
2. Merge feature branches into the main branch using pull requests.
3. Keep a high quality, up-to-date main branch.  
### Use feature branches for your work
Develop your features and fix bugs in feature branches based off your main branch. These branches are also known as topic branches.  
Feature branches isolate work in progress from the completed work in the main branch.  
### Name your feature branches by convention
Use a consistent naming convention for your feature branches to identify the work done in the branch. You can also include other information in the branch name, such as who created the branch.  
**Some suggestions for naming feature branches:**  
* users/username/description
* users/username/workitem
* bugfix/description
* feature/feature-name
* feature/feature-area/feature-name
* hotfix/description  
## GIT workflow  
### GIT feature branch workflow  
All feature development should take place in a dedicated branch instead of the main branch. This encapsulation makes it easy for multiple developers to work on a particular feature without disturbing the main codebase. It also means the main branch will never contain broken code and it makes it possible to make it pull requests. Developers create a new branch every time they start work on a new feature.  
### GITflow workflow  
Giflow is an alternative Git branching model that involves the use of feature branches and multiple primary branches. Giflow has numerous, longer-lived branches and larger commits. Under this model, developers create a feature branch and delay merging it to the main trunk branch until the feature is complete. In addition to feature branches, it uses individual branches for preparing, maintaining, and recording releases. **These long-lived feature branches require more collaboration to merge** and **have a higher risk of deviating from the trunk branch.** They can also **introduce conflicting updates.**  
## GIT merge  
* Non-destructive operation
* Existing branches are not changed
* Can pollute the master branch
* Existing branches are joined  
## GIT rebase  
* Context is lost, rewrites project history. (Never use it on public branches)
* Rewrites history on top of a branch
* Provides linear history
* May have to force push changes  
## GIT squash + merge  
Allows a developer to squash an extensive amount of commits into a single commit before merging it with the master branch. Helps maintain a cleaner commit history.  

***[Go back to the main table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to GIT table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git)***

# HTML  

<details>
    <summary>
    Table of contents
    </summary>

1. [What's HTML?](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#whats-html)
2. [XHTML](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#xhtml)
3. [Meta tags](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#meta-tags)
4. [Input types](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#input-types)
5. [`data-*` attributes](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#data--attributes)
6. [Semantic HTML](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#semantic-html)
7. [Accessibility (A11y)](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#accessibility-a11y)
</details>

## What's HTML?
HTML (HyperText Markup Language) is the most basic building block of the Web. It defines the meaning and structure of web content. HTML is used to specify whether your web content should be recognized as a paragraph, list, heading, link, image, multimedia player, form, or one of many other available elements or even a new element that you define.  
## XHTML 
XHTML stands for EXtensible HyperText Markup Language. It is a cross between HTML and XML language. XHTML is almost identical to HTML but it is stricter than HTML. XHTML is HTML defined as an XML application. It is supported by all major browsers.  
### HTML VS XHTML  
Key differences between HTML and XHTML:
* `<!DOCTYPE>` is mandatory in XHTML
* HTML is newer than XHTML
* The xmlns attribute in `<html>` is mandatory
* `<html>`, `<head>`, `<title>`, and `<body>` are mandatory
* Elements must always be properly nested
* Empty elements must always be closed
* Elements must always be in lowercase
* Attribute names must always be in lowercase
* Attribute values must always be quoted
* Attribute minimization is forbidden  
## Meta tags
Meta tags are specific snippets of text and image content that provide a summary for a webpage. Often meta tag data shows up whenever someone shares a link on social media, in messaging, or in chat softwares. In addition meta tags can contain information to help search engines and other technical services scan your site to figure out what it’s all about and whether or not it’s authentic.  
`<meta>` tags always go inside the `<head>` element, and are typically used to specify character set, page description, keywords, author of the document, and viewport settings.
### OG tags
Open Graph protocol enables any web page to become a rich object in a social graph. It requires some basic metadata to transform a webpage into a rich object:
* og:title - The title of your object as it should appear within the graph, e.g., "The Rock".
* og:type - The type of your object, e.g., "video.movie". Depending on the type you specify, other properties may also be required.
* og:image - An image URL which should represent your object within the graph.
* og:url - The canonical URL of your object that will be used as its permanent ID in the graph, e.g., "https://www.imdb.com/title/tt0117500/".  
Other optional meta data:
* og:audio - A URL to an audio file to accompany this object.
* og:description - A one to two sentence description of your object.
* og:determiner - The word that appears before this object's title in a sentence. An enum of (a, an, the, "", auto). If auto is chosen, the consumer of your data should chose between "a" or "an". Default is "" (blank).
* og:locale - The locale these tags are marked up in. Of the format language_TERRITORY. Default is en_US.
* og:locale:alternate - An array of other locales this page is available in.
* og:site_name - If your object is part of a larger web site, the name which should be displayed for the overall site. e.g., "IMDb".
* og:video - A URL to a video file that complements this object.  
## Input types
* button 
* checkbox 
* color 
* date 
* datetime-local 
* email 
* file 
* hidden 
* month 
* number 
* password 
* radio 
* range 
* reset 
* search 
* submit 
* tel 
* text ***default*** 
* time 
* url  
## `data-*` attributes  
Allow the storage of extra, custom information on standard, semantic HTML elements without other hacks such as non-standard attributes, or extra properties on DOM. The stored (custom) data can then be used in the page's JavaScript to create a more engaging user experience (without any Ajax calls or server-side database queries).  

Any attribute on any element whose attribute name starts with data- is a data attribute, and will be completely ignored by the user agent. For example: 
```
<article
    id="electric-cars"
    data-columns="3"
    data-index-number="12314"
    data-parent="cars">
    …
</article>
```
## Semantic HTML
### What is semantic HTML?
Elements that clearly answer the question "what purpose or role does that HTML element have?" to both the developer and the browser.  
HTML should be coded to represent the data that will be populated and not based on its default presentation styling.  
### Benefits of writing semantic markup  
* Search engines will consider its contents as important keywords to influence the page's search rankings.  
* Screen readers can use it as a signpost to help visually impaired users navigate a page (aids in accessibility)
* Finding blocks of meaningful code is significantly easier than searching through endless divs with or without semantic or namespaced classes (readability)
* Suggests to the developer the type of data that will be populated (readability)
* Semantic naming mirrors proper custom element/component naming  
When approaching which markup to use, ask yourself, "What element(s) best describe/represent the data that I'm going to populate?"  
### Semantic elements
These are some of the roughly 100 semantic elements available:
* `<article>`
* `<aside>`
* `<details>`
* `<figcaption>`
* `<figure>`
* `<footer>`
* `<header>`
* `<main>`
* `<mark>`
* `<nav>`
* `<section>`
* `<summary>`
* `<time>`  
## Accessibility (A11y)  
Accessibility is the practice of making your websites usable by as many people as possible, by developing content to be accessible, no matter an individual's physical and cognitive abilities and how they access the web.  
Websites have to comply with the Web Content Accessibility Guidelines.  
### Benefits
* Semantic HTML, which improves accessibility, also improves SEO, making your site more findable.
* Caring about accessibility demonstrates good ethics and morals, which improves your public image.
* Other good practices that improve accessibility also make your site more usable by other groups, such as mobile phone users or those on low network speed. 
* It’s required by the law in some places.  
### Main types of disabilities to consider
* Visual impairments
    * Screen magnifiers
    * Screen readers
    * Captioning images
* Hearing impairments
    * Captioning audio and video elements
    * Providing transcripts
    * Text simplification
* Mobility impairments
    * Controls must be accessible by keyboard
    * Make clickable elements big
* Cognitive impairments
    * Delivering content in more than one way, such as by text-to-speech or by video.
    * Easily understood content, such as text written using plain-language standards.
    * Focusing attention on important content.
    * Minimizing distractions, such as unnecessary content or advertisements.
    * Consistent webpage layout and navigation.
    * Familiar elements, such as underlined links blue when not visited and purple when visited.
    * Dividing processes into logical, essential steps with progress indicators.
    * Website authentication as easy as possible without compromising security.
    * Making forms easy to complete, such as with clear error messages and simple error recovery.  

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to HTML table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#html)***

# CSS  

<details>
    <summary>
    Table of contents
    </summary>

1. [What is CSS?](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#what-is-css)
2. [Importing external stylesheets](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#importing-external-stylesheets)
3. [CSS rulesets](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css-rulesets)
4. [CSS syntax](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css-syntax)
5. [The Box Model](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#the-box-model)
6. [Specificity](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#specificity)
7. [The `!important` keyword](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#the-important-keyword)
8. [Positioning](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#positioning)
9. [Relative and absolute units](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#relative-and-absolute-units)
10. [Layout](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#layout)
11. [Flexbox](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#flexbox)
12. [Grid](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#grid)
13. [Media Queries](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#media-queries)
14. [OOCSS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#ocss-object-oriented-css)
15. [BEM](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#bem-block-element-modifier)
16. [SMACSS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#smacss-scalable-and-modular-architecture-for-css)
17. [CSS preprocessors](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css-preprocessors)
18. [Bootstrap](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#bootstrap)
19. [Materialize CSS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#materialize-css)
</details>

## What is CSS?
Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML. It describes how elements should be rendered on screen, on paper, in speech, or on other media. CSS is what you use to selectively style HTML elements.  
## Importing external stylesheets
```
<head>
    <link href=”<url || path>” rel="stylesheet" />
    …
</head>
```  
## CSS rulesets
They are what create a CSS stylesheet and are comprised by:
* Selector: The element(s) to style.
    * Type selectors ( div )
    * Class selectors ( .className )
    * Id selectors ( not recommended )
    * Attribute selectors ( [attr=value] )
    * Pseudo-classes and pseudo-elements ( :hover, ::first-line )
    * Combinators 
    * Grouping selectors ( , )
* Declaration: It specifies which of the element's properties you want to style. 
* Properties: These are ways in which you can style an HTML element. 
* Property value  
## CSS syntax
* Apart from the selector, each ruleset must be wrapped in curly braces. ({})
* Within each declaration, you must use a colon (:) to separate the property from its value or values.
* Within each ruleset, you must use a semicolon (;) to separate each declaration from the next one.  
## The Box Model
When laying out a document, the browser's rendering engine represents each element as a rectangular box according to the standard CSS basic box model. CSS determines the size, position, and properties (color, background, border size, etc.) of these boxes. The box model describes how these elements work together to create a box as displayed by CSS.  
Every box is composed of four parts (or areas), defined by their respective edges: the **content** edge, **padding** edge, **border** edge, and **margin** edge.
### Block boxes
* The box will break onto a new line.
* The width and height properties are respected.
* Padding, margin and border will cause other elements to be pushed away from the box.
* The box will extend in the inline direction to fill the space available in its container. In most cases, the box will become as wide as its container, filling up 100% of the space available.  
### Inline boxes
* The box will not break onto a new line.
* The width and height properties will not apply.
* Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
* Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.
## Specificity
The specificity algorithm calculates the weight of a CSS selector to determine which rule from competing CSS declarations gets applied to an element.  
### How is it calculated?
The weight is determined by the number of selectors of each weight category in the selector matching the element (or pseudo-element). If there are two or more declarations providing different property values for the same element, the declaration value in the style block having the matching selector with the greatest algorithmic weight gets applied.  
The algorithm is a three column value of three categories or weights:  
`ID - CLASS - TYPE`  
The three columns are created by counting the number of selector components for each selector weight category in the selectors that match the element. Once the specificity values of the relevant selectors are determined, the number of selector components in each column are compared, from left to right.  
### Selector weight category
* ID column: Includes only ID selectors, such as `#example`. For each ID in a matching selector, add 1-0-0 to the weight value.
* CLASS column
    * Includes class selectors, such as `.myClass`, 
    * attribute selectors like `[type="radio"]` and `[lang|="fr"]`, 
    * and pseudo-classes, such as `:hover`, `:nth-of-type(3n)`, and `:required`. 
    * For each class, attribute selector, or pseudo-class in a matching selector, add 0-1-0 to the weight value.
* TYPE column:
    * Includes type selectors, such as `p`, `h1`, and `td`, 
    * and pseudo-elements like `::before`, `::placeholder`, and all other selectors with double-colon notation. 
    * For each type or pseudo-element in a matching selector, add 0-0-1 to the weight value.
* No value: The universal selector (`*`) and the pseudo-class `:where()` and its parameters aren't counted when calculating the weight so their value is 0-0-0, but they do match elements. These selectors do not impact the specificity weight value.
* Combinators, such as `+`, `>`, `~`, `" "` (space), and `||`, may make a selector more specific in what is selected but they don't add any value to the specificity weight.
* The negation pseudo-class, `:not()`, itself has no weight. Neither do the `:is()` or the `:has()` pseudo-classes. The parameters in these selectors, however, do. The values of both come from the parameter in the list of parameters that has the highest specificity. 
## The `!important` keyword
CSS declarations marked as important override any other declarations within the same cascade layer and origin. When conflicting declarations from the same origin and cascade layer with the `!important` flag are applied to the same element, the declaration with a greater specificity is applied.  
## Positioning
Sets how an element is positioned in a document. 
### Values
* static: every element has a static position by default, so the element will stick to the normal page flow. So if there is a left, right, top, bottom, z-index set then there will be no effect on that element.
* relative: an element’s original position remains in the flow of the document, just like the static value. But now left, right, top, bottom, z-index will work. The positional properties “nudge” the element from the original position in that direction.
* absolute: the element is removed from the flow of the document and other elements will behave as if it’s not even there whilst all the other positional properties will work on it.
* fixed: the element is removed from the flow of the document like absolutely positioned elements. In fact they behave almost the same, only fixed positioned elements are always relative to the document, not any particular parent, and are unaffected by scrolling.
* sticky: the element is treated like a relative value until the scroll location of the viewport reaches a specified threshold, at which point the element takes a fixed position where it is told to stick.
* inherit: the position value doesn’t cascade, so this can be used to specifically force it to, and inherit the positioning value from its parent.  
## Relative and absolute units
### Relative (responsive)
Unlike PX, relative units like %, EM, and REM are better suited to responsive design and also help meet accessibility standards. Relative units scale better on different devices because they can scale up and down according to another element’s size.
* EM: Relative to the parent element (1em = 16 px)
* REM: Relative to the root element (HTML tag)
* %: Relative to the parent element
* VW: Relative to the viewport’s width
* VH: Relative to the viewport’s height
### Absolute
Choose PX however, if you need to ensure that an element never resizes at any breakpoint and remains the same regardless of whether a user has chosen a different default size. PX units ensure consistent results even if that’s not ideal.
* Px: Using PX can be problematic for responsive sites, but they are useful for maintaining consistent sizing for some elements. If you have elements that should not be resized, then using PX is a good choice.  
## Layout
### Fixed/ static (px)
In a fixed (static) layout, elements are sized using pixels. The elements will be the same size on all screens, it’s a measurement that is independent and uneffected by the size of the device we are viewing from. If we create an element that is wider or taller than the device size we will see horizontal scrollbars, and the user will have to scroll to see the rest of the content that is out of view.  
### Elastic (em)
As a user scales the text up and down using their zoom settings it will also scale the elements set as ems. this way your text will always be in proportion to the container it is within. There are also some disadvantages such as, if a user scales elements that occupy the same space overlap is possible unless the developer invests a lot of time testing font sizes across many different device sizes and make s adjustments accordingly.  
### Fluid/ liquid (%)
Fluid layouts size elements using (%) percents. This allows for a layout that will stretch and expeand or contract to the size of the user's device. This allows developers to make use of the entirety of space on the screen. Also your users will never see horizontal scrollbars if it is implemented correctly.  
### Hybrid
Hybrid layouts use a combination of all of the size values mentioned above.  
## Flexbox
The Flexbox Layout module aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic.  
The main idea behind the flex layout is to give the container the ability to alter its items’ width/height (and order) to best fill the available space (mostly to accommodate to all kind of display devices and screen sizes). **A flex container expands items to fill available free space or shrinks them to prevent overflow.**  
Flexbox layout is most appropriate to the components of an application, and small-scale layouts.  
### Flexbox teminology
* **main axis** – The main axis of a flex container is the primary axis along which flex items are laid out. Beware, it is not necessarily horizontal; it depends on the flex-direction property (see below).
* **main-start | main-end** – The flex items are placed within the container starting from main-start and going to main-end.
* **main size** – A flex item’s width or height, whichever is in the main dimension, is the item’s main size. The flex item’s main size property is either the ‘width’ or ‘height’ property, whichever is in the main dimension.
* **cross axis** – The axis perpendicular to the main axis is called the cross axis. Its direction depends on the main axis direction.
* **cross-start | cross-end** – Flex lines are filled with items and placed into the container starting on the cross-start side of the flex container and going toward the cross-end side.
* **cross size** – The width or height of a flex item, whichever is in the cross dimension, is the item’s cross size. The cross size property is whichever of ‘width’ or ‘height’ that is in the cross dimension.
### Flex container properties (parents)
* Display
* Flex-direction
    * Row, row-reverse, column, column-reverse
* Flex-wrap
    * Nowrap, wrap, wrap-reverse
* Flex-flow
    * shorthand for the flex-direction and flex-wrap properties
* Justify-content (when there is extra space in the main-axis)
    * flex-start, flex-end, center, space-between, space-around, space-evenly, start, end, left, right
        * The safest values are flex-start, flex-end, and center
    * Safe, unsafe
        * Using safe ensures that however you do this type of positioning, you can’t push an element such that it renders off-screen (e.g. off the top) in such a way the content can’t be scrolled too (called “data loss”).
* Align-items
    * stretch, flex-start, flex-end, center, baseline, first baseline, last baseline, start, end, self-start, self-end
    * Safe, unsafe
        * Using safe helps prevent aligning elements such that the content becomes inaccessible.
* Align-content (when there is extra space in the cross-axis)
    * flex-start, flex-end, center, space-between, space-around, space-evenly, stretch, start, end, baseline, first baseline, last baseline
    * Safe, unsafe
        * Using safe helps prevent aligning elements such that the content becomes inaccessible.
* gap, row-gap, column-gap
### Flex items properties (children)
* Order
* Flex-grow
* Flex-shrink
* Flex-basis
* Flex
* Align-self
    * auto, flex-start, flex-end, center, baseline, stretch  
## Grid
The Grid layout is intended for larger scale layouts. Similarly to flexbox, the source order of the grid items doesn’t matter. Your CSS can place them in any order, which makes it super easy to rearrange your grid with media queries. Imagine defining the layout of your entire page, and then completely rearranging it to accommodate a different screen width all with only a couple lines of CSS.  
### Grid terminology
* Grid container - The element on which display: grid is applied. It’s the direct parent of all the grid items.
* Grid item - The children (i.e. direct descendants) of the grid container. 
* Grid line - The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. 
* Grid track - The space between two adjacent grid lines. You can think of them as the columns or rows of the grid.
* Grid area - The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells.
* Grid cell - The space between two adjacent row and two adjacent column grid lines. It’s a single “unit” of the grid.
### Grid containers properties (parent)
* Display
    * Grid, inline-grid
* Grid-template-columns, grid-template-rows
    * Track-size, line-name
* Grid-template-areas
    * Grid-area-name, “.”, none
* Grid-template (A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration)
    * None, grid-template-rows, grid-template-columns
* Column-gap, row-gap, grid-column-gap, grid-row-gap
    * Line-size
* Gap, grid-gap (shorthand for row-gap and column-gap)
    * Grid-row-gap, grid-column-gap
* Justify-items
    * Start, end, center, stretch
* Align-items
    * Start, end, center, stretch, baseline
* Place-items
    * Align-items, justify-items
* Justify-content
    * Start, end, center, stretch, space-around, space-between, space-evenly
* Align-content
    * Start, end, center, stretch, space-around, space-between, space-evenly
* Place-content
    * Align-content, justify-content
* Grid-auto-columns, grid-auto-rows
    * Track-size
* Grid-auto-flow
    * Row, column, dense
* Grid (shorthand for grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow)
    * None, grid-template, grid-template-rows, `[ auto-flow && dense? ] <grid-auto-columns>?`, `[ auto-flow && dense? ] <grid-auto-rows>? || <grid-template-columns>`  
### Grid items properties (children)
* Grid-column-start, grid-column-end, grid-row-start, grid-row-end
    * Line, `span <number>`, `span <name>`, auto 
* Grid-column, grid-row (Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively)
    * Start-line, end-line
* Grid-area
    * Name, row-start, column-start, row-end, column-end
* Justify-self
    * Start, end, center, stretch
* Align-self
    * Start, end, center, stretch
* Place-self
    * Auto,  align-self, justify-self
### Special units
* Fr units (portion of the remaining space)
* Sizing Keywords
* min-content: the minimum size of the content
* max-content: the maximum size of the content
* auto: this keyword is a lot like fr units, except that they “lose” the fight in sizing against fr 
* fit-content: use the space available, but never less than min-content and never more than max-content
* Fr
### Special functions
* minmax() sets a minimum and maximum value for what the length is able to be
* min() function
* max() function
### repeat() function and keywords
* Syntax: repeat( `<number of times>`, `<size>` )
* Keywords
    * auto-fill: Fit as many possible columns as possible on a row, even if they are empty.
    * auto-fit: Fit whatever columns there are into the space. Prefer expanding columns to fill space rather than empty columns.
```
grid-template-columns: 
  repeat(auto-fit, minmax(250px, 1fr));
```
## Media Queries
They are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen) or specific characteristics and parameters (such as screen resolution or browser viewport width).  
Media queries are used for the following:
* To conditionally apply styles with the CSS `@media` and `@import` at-rules.
* To target specific media for the `<style>`, `<link>`, `<source>`, and other HTML elements with the media= attribute.
* To test and monitor media states using the `Window.matchMedia()` and `MediaQueryList.addListener()` JavaScript methods.
### Syntax
`@ <media-type> <media-features> { <css rules> }`  
#### Media types
They define the category of device for which the media query applies: all, print, screen. The type is optional (assumed to be all) except when using the not or only logical operators. 
##### Media features
They describe a specific characteristic of the user agent, output device, or environment:
* any-hover
* any-pointer
* aspect-ratio
* color
* color-gamut
* color-index
* display-mode
* dynamic-range
* forced-colors
* grid
* height
* hover
* inverted-colors
* monochrome
* orientation
* overflow-block
* overflow-inline	
* pointer
* prefers-color-scheme
* prefers-contrast
* prefers-reduced-motion
* resolution
* scripting
* update
* video-dynamic-range
* width (min- and max-)
##### Logical operators
They can be used to compose a complex media query: `not`, `and`, and `only`. You can also combine multiple media queries into a single rule by separating them with commas.
##### Examples
``` 
@media print {
  /* ... */
}
@media screen, print {
  /* ... */
}
@media (hover: hover) {
  /* ... */
}
@media (max-width: 1250px) {
  /* ... */
}
@media (width <= 1250px) {
  /* ... */
}

@media (color) {
  /* ... */
}
@media (min-width: 30em) and (orientation: landscape) {
  /* ... */
}
@media (min-height: 680px), screen and (orientation: portrait) {
  /* ... */
}
@media not all and (monochrome) {
  /* ... */
}
@media not screen and (color), print and (color) {
  /* ... */
}
```  
## OCSS (Object Oriented CSS)
It’s a CSS writing methodology that aims to make CSS modular and object-based. The “object” in OOCSS refers to an HTML element or anything associated with it (like CSS classes or JavaScript methods).  
A CSS object may consist of four things:
* HTML node(s) of the DOM
* CSS declarations about the style of those nodes
* Components like background images
* JavaScript behaviors, listeners, or methods associated with an object
### Principles of OOCSS
1. Separate structure from appearance: A big part of OOCSS is writing code that separates page structure (width, height, margins, padding) from appearance (fonts, colors, animations). This allows custom skinning to be applied onto multiple page elements without affecting the structure.
2. Separate content from its container: In simpler terms, this only means that you should avoid using child selectors whenever it’s possible. When customizing any unique page elements like anchor links, headers, blockquotes, or unordered lists, you should give them unique classes rather than descendant selectors.
### Guidelines
* Work with classes instead of IDs for styling.
* Try to abstain from multi-level descendant class specificity unless needed.
* Define unique styles with repeatable classes (eg floats, clearfix, unique font stacks).
* Extend elements with targeted classes rather than parent classes.
* Organize your stylesheet into sections, consider adding a table of contents.
## BEM (Block, Element, Modifier)
It’s a popular naming convention for classes in HTML and CSS. e.g.:  
```
<a class="btn btn--big btn--orange" href="https://css-tricks.com">
  <span class="btn__price">$9.99</span>
  <span class="btn__text">Subscribe</span>
</a>
```
### Block
It’s a top-level abstraction of a new component, it should be thought of as a parent.  
In the example, it’s `btn`.
### Element
The child item or element can be placed inside a block and it’s denoted by two underscores following the name of the block.  
In the example, it’s `btn__price` and `btn__text`.
### Modifier
They can manipulate the block so that we can theme or style that particular component without inflicting changes on a completely unrelated module.  
In the example, it’s `btn--orange` and `btn--big`.
## SMACSS (Scalable and Modular Architecture for CSS)
It’s a style guide, an attempt to document a consistent approach to site development when using CSS. It follows five categories:  
1. Base: these are the default values. They are padding, margin, border, font and other properties; these values are used on the entire website and all elements.
2. Layout: divides a page into sections with elements like header, footer, main page, etc. Layouts hold one or more modules together. Often developers show layout elements by prefixing the class with l-, e.g. l-header, l-footer.
3. Module: modules are the reusable, modular parts of our design like navbar, sidebar and some elements that are repeated in the site.
4. State: states are ways to describe how our modules or layouts will look when they are in a particular state (e.g. active, inactive, expanded, hidden). These are prefixed with is-, e.g. is-active, is-inactive, is-expanded, is-hidden.
5. Theme: Theme rules are similar to state rules in that they describe how modules or layouts might look. It is more applicable for larger sites with shared elements that look different throughout.  

The idea of this architecture is to not mix code of several categories on a single file because it can be complicated to find a single line of code to change.  
The main purpose of this categorization is to codify patterns —things that repeat themselves within our design. Repetition results in less code, easier maintenance, and greater consistency in the user experience.  
## CSS preprocessors
A CSS preprocessor is a program that lets you generate CSS from the preprocessor's own unique syntax.  
There are many CSS preprocessors to choose from, however most CSS preprocessors will add some features that don't exist in pure CSS, such as mixin, nesting selector, inheritance selector, and so on. These features make the CSS structure more readable and easier to maintain.  
To use a CSS preprocessor, you must install a CSS compiler on your web server; Or use the CSS preprocessor to compile on the development environment, and then upload compiled CSS file to the web server.
### Advantages
* Variables
* Functions
* Nesting
* Mixins (similar to functions)
* Extends (similar to extending classes in JS)
* Loops
### SASS
Sass stands for Syntactically Awesome Stylesheet, it is an extension to CSS and a pre-processor, it’s compatible with all versions of CSS and it reduces repetition of CSS, therefore saving time.  
A browser does not understand Sass code. Therefore, you will need a Sass pre-processor to convert Sass code into standard CSS, this process is called transpiling.  
## Bootstrap
Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It contains HTML, CSS and JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components. Once added to a project, Bootstrap provides basic style definitions for all HTML elements.  
The most prominent components of Bootstrap are its layout components, as they affect an entire web page. The basic layout component is called "Container", as every other element in the page is placed in it. Developers can choose between a fixed-width container and a fluid-width container.
### Grid System
The grid system in Bootstrap is one of the primary elements. They create layouts of pages by using multiple columns and rows in which the content can be inserted. If the device screen on which the page is being viewed, gets bigger, the grid will scale up to 12 columns. This fits the page on to the screen.  
There are pre-defined classes by which designers can make their own layouts. The grid system can also collapse to fit smaller screens. This flexibility allows designers to create more visually and technically comprehensive websites, with comparatively less effort as compared to a non-framework development foundation.
## Materialize CSS
It’s a design language whose goal is to develop a system of design that allows for a unified user experience across all their products on any platform. Also known as Material Design.  
It is used to construct attractive, consistent, and functional web pages and web apps while adhering to modern web design principles such as browser portability, device independence, and graceful degradation.  
### Features
* It is a standard CSS with minimal footprint.
* In-built Responsive Design
* It is free to use and requires jQuery JavaScript library to function properly.
* It is cross-browser, compatible, and can be used to create reusable web components.
* It contains enhanced and specialized features such as cards, tabs, navigation bars, toasts etc.
* It provides new versions of common user interface controls such as buttons, checkboxes, and text fields adapted to follow Material Design concepts.
* Materialize is by design very minimal and flat.  

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to CSS table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css)***

# JavaScript  

<details>
    <summary>
    Table of contents
    </summary>

1. [Basic syntax](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#basic-syntax)
2. [Closures](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#closures)
3. [DOM](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#dom)
4. [Strict](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#strict)
5. [Scope](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#scope)
6. [Hoisting](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#hoisting)
7. [Fetch API](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#fetch-api)
8. [AJAX (XHR)](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#ajax-xhr)
9. [Events](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#events)
10. [Promises](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#promises)
11. [Async / Await](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#async--await)
12. [Callbacks](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#callbacks)
13. [ES6+](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#es6)
</details>

## Basic syntax
It’s a scripting language that enables you to create dynamically updating content, control multimedia, etc. JavaScript is a lightweight and dynamic interpreted language, used to create client-side dynamic pages. It is an open-source and cross-platform language. It allows implicit type conversion.  
### Comments
* `// Single line comment`
* `/* Multiple lines comment */` 
### How to add it to a page?  
Both internal and external Javascript can go inside the ``<head>`` or the ``<body>`` tag. Although it's recommended to add it at the end of the `<body>` tag.  
#### Internal JavaScript  
```
<script>  
    // JavaScript code goes here  
</script>
```
#### External JavaScript
``<script src="index.js" type="text/javascript" defer > </script>``  
### Variable declaration
* const: to declare constant variables, block scoped
* let: to declare non-constant variables, block scoped
* var: also allows to declare non-constant variables but allows multiple declarations and it’s not scoped. Not recommended.  
#### Naming convention
* Functions and variables
    * isProperty for booleans
    * getSomething for returning functions
    * doSomething for non-returning functions
    * they are always camel-cased and start with a letter  
* Classes
    * They start with a capital letter
### JavaScript Operators
* Arithmetic: `+` `*` `-` `/` `%`  
* Assignment: `=` `+=` `*=` `-=` `/=` `%=`  
### JavaScript Data Types  
* Primitives: 
    * String 
    * Integer and BigInt
    * Boolean
    * `undefined` ( set by Javascript )
    * `null` ( set by the programmer )
    * Symbol  
* Non-primitives: 
    * Arrays
    * Objects
    * Sets and WeakSets
    * Maps and WeakMaps  
### Equality and comparisons  
* Strict equals ( `===` )
    * Compares values ***and*** type 
    * Only on primitive types
* Loose equals ( `==` )
    * Only on primitive types
* `Object.is() === true` if ***both*** elements to compare are one of the following:
    * `undefined`
    * `null`
    * `true`
    * `false`
    * strings of the same length with the same characters in the same order
    * the same object (meaning values reference the same object in memory)
    * BigInts with the same numeric value
    * symbols that reference the same symbol value
    * numbers and one of the following is true:
        * both are `+0`
        * both are `-0`
        * both are `NaN`
        * both are or non-zero, not `NaN`, and have the same value  
## Closures
A closure is a function that references variables in the outer scope from its inner scope. It references variables not declared inside itself.
They can emulate public and private methods or attributes.
```
let name = 'Ana';

function greeting() { 
    let message = 'Hi'
    console.log(message + '  '+ name)
}
```
## DOM
A web page is a document that can be either displayed in the browser window or as the HTML source. In both cases, it is the same document but the Document Object Model (DOM) representation allows it to be manipulated. It represents the document as nodes and objects; that way, programming languages can interact with the page.  
The DOM represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects.  
DOM methods allow programmatic access to the tree. With them, you can change the document's structure, style, or content. The DOM is not part of the JavaScript language nor is it a programming language, but is instead a Web API used to build websites. The core DOM defines the entities describing any document and the objects within it. This is expanded upon as needed by other APIs that add new features and capabilities to the DOM.  
### DOM vs HTML  
The html comes back from the server and gets parsed so that the browser can build the DOM, which JavaScript can manipulate.
###### DOM
1. Result from parsing the response from the server
2. Built by the browser, able to be manipulate with JS
###### HTML
1. Comes back from the server
2. Cannot be manipulated with JS
## Strict
JavaScript's strict mode is a way to opt in to a restricted variant of JavaScript, thereby implicitly opting-out of "sloppy mode". It is invoked by writing `"use strict";` at the top of a script and has siffernt semantics from normal JavaScript.
### Differences from normal JavaScript
* Eliminates some JavaScript silent errors by changing them to throw errors.
* Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
* Prohibits some syntax likely to be defined in future versions of ECMAScript.  
## Scope  
The scope is the current context of execution in which values and expressions are "visible" or can be referenced. If a variable or expression is not in the current scope, it will not be available for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.  
### Types of scopes
* Global scope
* Module scope
* Function scope
* Block scope (for `let` and `const`)
## Hoisting
JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code, thereby allowing functions to be safely used in code before they are declared.  
## Fetch API
The Fetch API provides an interface for fetching resources. Fetch provides a generic definition of Request and Response objects (and other things involved with network requests). This will allow them to be used wherever they are needed in the future, whether it's for service workers, Cache API, and other similar things that handle or modify requests and responses.  
The `fetch()` method. It is implemented in multiple interfaces, specifically Window and WorkerGlobalScope. This makes it available in pretty much any context you might want to fetch resources in.  
The `fetch()` method takes one mandatory argument, the path to the resource you want to fetch. It returns a Promise that resolves to the Response to that request — as soon as the server responds with headers — even if the server response is an HTTP error status. You can also optionally pass in an init options object as the second argument. Once a Response is retrieved, there are a number of methods available to define what the body content is and how it should be handled.  
## AJAX (XHR)
Ajax stands for Asynchronous Javascript and XML. Ajax is a programming technique that allows us to create dynamic, complex, and asynchronous web applications. Ajax allows us to send and receive data from the webserver asynchronously without interfering with the current state or behavior of the web page or application.  
XHR is the XMLHttpRequest Object which interacts with the server. Ajax technique in the nutshell leverages the XHR request to send and receive data from the webserver. This object is provided by the browser’s javascript environment. It transfers the data between the web browser and server.  
### XHR
XMLHttpRequest (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing. Despite its name, XMLHttpRequest can be used to retrieve any type of data, not just XML.  
## Events
Events are actions or occurrences that happen in the system you are programming, which the system tells you about so your code can react to them. For example, if the user clicks a button on a webpage or if a page finishes loading.  
### Bubbling
Event Bubbling happens when an element receives an event, and that event is transmitted or propagated to its parent and ancestor elements in the DOM tree until it gets to the root element. When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.  
`Element clicked on -> Parent -> ... -> Top level element`  
The most deeply nested element that caused the event is called a target element, accessible as event.target.  
Note the differences between event.target and event.currentTarget:  
* `event.target` – is the “target” element that initiated the event, it doesn’t change through the bubbling process.
* `event.currentTarget` – is the “current” element, the one that has a currently running handler on it.  
For instance, if we have a single handler `form.onclick`, then it can “catch” all clicks inside the form. No matter where the click happened, it bubbles up to `<form>` and runs the handler.  
In `form.onclick handler`, `this (=event.currentTarget)` is the `<form>` element, because the handler runs on it. `event.target` is the actual element inside the form that was clicked.  
#### Some non-bubbling events  
* HTML frame/object
    * load
    * unload
    * scroll (except that a scroll event on document must bubble to the window)
* HTML form
    * focus
    * Blur
* Mutation
    * DOMNodeRemovedFromDocument
    * DOMNodeInsertedIntoDocument
* Progress
    * loadstart
    * progress
    * error
    * abort
    * load
    * loadend
## Promises
The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.  
A Promise is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.  
![promise image](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/promises.png)
A Promise is in one of these states:  
* ***pending***: initial state, neither fulfilled nor rejected.
* ***fulfilled***: meaning that the operation was completed successfully.
* ***rejected***: meaning that the operation failed.  

The eventual state of a pending promise can either be fulfilled with a value or rejected with a reason (error). When either of these options occur, the associated handlers queued up by a promise's then method are called. If the promise has already been fulfilled or rejected when a corresponding handler is attached, the handler will be called, so there is no race condition between an asynchronous operation completing and its handlers being attached.  
## Async / Await
The async function declaration declares an async function where the await keyword is permitted within the function body. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains with the `.then()` method.  
### Async 
The word `“async”` before a function means that a function always returns a promise. `Async` functions can contain zero or more `await` expressions. `Await` expressions make promise-returning functions behave as though they're synchronous by suspending execution until the returned promise is fulfilled or rejected. The resolved value of the promise is treated as the return value of the `await` expression. Use of `async` and `await` enables the use of ordinary `try / catch` blocks around asynchronous code.  
Even though the return value of an `async` function behaves as if it's wrapped in a `Promise.resolve`, they are not equivalent. An `async` function will return a different reference, whereas `Promise.resolve` returns the same reference if the given value is a promise.  
The body of an `async` function can be thought of as being split by zero or more `await` expressions. Top-level code, up to and including the first `await` expression (if there is one), is run synchronously. In this way, an `async` function without an `await` expression will run synchronously. If there is an `await` expression inside the function body, however, the `async` function will always complete asynchronously.  
Code after each `await` expression can be thought of as existing in a `.then` callback. In this way a promise chain is progressively constructed with each reentrant step through the function. The return value forms the final link in the chain.  
### Await 
The `await` operator is used to wait for a Promise and get its fulfillment value. It can only be used inside an `async` function or at the top level of a module. 
The return value is the fulfillment value of the promise or thenable object, or, if the expression is not thenable, the expression's own value.  
`await` is usually used to unwrap promises by passing a `Promise` as the expression. Using `await` pauses the execution of its surrounding `async` function until the promise is settled (that is, fulfilled or rejected). When execution resumes, the value of the `await` expression becomes that of the fulfilled promise. If the promise is rejected, the `await` expression throws the rejected value.
Because `await` is only valid inside `async` functions and modules, which themselves are asynchronous and return promises, the `await` expression never blocks the main thread and only defers execution of code that actually depends on the result, i.e. anything after the `await` expression.  
## Callbacks
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
```
const callbackFun = ( name ) => `${name}@company.com`
const arrayOfUserEmails = usersData.map( callbackFun( userName ) )
```
The above example is a synchronous callback, as it is executed immediately. However, callbacks are often used to continue code execution after an asynchronous operation has completed — these are called asynchronous callbacks. A good example is the callback functions executed inside a `.then()` block chained onto the end of a promise after that promise fulfills or rejects. This structure is used in many modern web APIs, such as `fetch()`.  
## ES6+
ES6 is short for ECMAScript 6, and the plus sign (+) signals that we're also including features from even newer versions of ECMAScript. ECMAScript 6 (ES6 for short) is the sixth edition of the ECMA-262 standard and features major changes and improvements to the ECMAScript specification.  
ECMA means European Computer Manufacturer's Association. ECMAScript is a programming language standard and JavaScript is its implementation. ECMAScript specifies the core features that a language should provide and how those features should be implemented.
### Top Features Introduced since ES6 or ECMAScript 2015
1. `let` and `const` Keywords    
The keyword "let" enables the users to define variables and on the other hand, "const" enables the users to define constants. Variables were previously declared using "var" which had function scope and were hoisted to the top. It means that a variable can be used before declaration. But, the "let" variables and constants have block scope which is surrounded by curly-braces "{}" and cannot be used before declaration.   
2. Arrow Functions    
Arrow functions are defined using the fat arrow (=>) notation.   
It is evident that there is no "return" or "function" keyword in the arrow function declaration. We can also skip the parenthesis in the case when there is exactly one parameter, but will always need to use it when you have zero or more than one parameter.  
But, if there are multiple expressions in the function body, then we need to wrap it with curly braces ("{}"). We also need to use the "return" statement to return the required value.  
The behavior of `this` inside of an arrow function differs considerably from the regular function's `this` behavior. The arrow function doesn't define its own execution context. No matter how or where being executed, `this` value inside of an arrow function always equals this value from the outer function.  
```
const callbackFun = name => `${name}@company.com`
``` 
3. Multi-line Strings    
Users can create multi-line strings by using `` ` `` back-ticks.
```
const greeting = `This
                  is
                  a
                  multi-line
                  string
                  !`
```                  
4. Default Parameters   
```
const divide = ( a, b = 1 ) => ( b !== 0 ? a/b : 0 )
```  
5. Template Literals  
The syntax for using the string template is `${PARAMETER}` and is used inside of the back-ticked string.
```
const greeting = userName => `Welcome back, ${userName}`
```  
6. `Spread` Operator  
The `spread (...)` syntax allows an iterable, such as an array or string, to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected. In an object literal, the spread syntax enumerates the properties of an object and adds the key-value pairs to the object being created.
```
const dob = {
    year,
    month,
    day
}
const personObj = {
    name, 
    lastName,
    height,
    weight,
    sex
}
const addAge = (personObject, dob, currYear) => ( { ...personObject, age: currYear - dob.year  } )

// expected return value: an object with name, lastName, height, weight, sex and age properties.

const arrayOfAnimals = ['Monkey', 'Elephant', 'Giraffe', 'Lion']
const addAnimal = ( animalsArr, newAnimal ) => ( [ ... animalsArr, newAnimal ] )

// expected return value with 'Zebra' as the 'newAnimal' argument: ['Monkey', 'Elephant', 'Giraffe', 'Lion', 'Zebra']
```  
7. `Rest` Parameters    
The rest parameter syntax allows a function to accept an indefinite number of arguments as an array. A function definition's last (or only) parameter can be prefixed with `...`, which will cause all remaining (user supplied) parameters to be placed within an Array object. A function definition can only have one rest parameter, and the rest parameter must be the last parameter in the function definition. 
```
function getMoviesToWatch ( ...movies ) {
    movies.forEach( movie => searchInDatabase( movie ) )
}
function borrowBooks( username, ...books ) {
    books.forEach( book => addToBooksBorrowed( username, book.id ) )
}
```  
8. Destructuring Objects   
Object destructuring picks out values from objects and assigns it to variables. It is a more convenient method of accessing an object’s internal properties.
```
const dobObj = {
    day, 
    month,
    year
}
const bookObj = {
    title, 
    author, 
    summary, 
    edition,
    editorialHouse, 
    hasAudioVersion, 
    id
}
const {day, month, year} = dobObj
const {title, author, summary, edition} = bookObj
```
9. `Promises`  
10. `Classes`  
11. Modules  
JavaScript modules provide mechanisms for splitting JavaScript programs up into separate files, and `import` what's needed from each of them when needed. Use of native JavaScript modules is dependent on the `import` and `export` statements, which go at the top level of a module (not inside functions, blocks, etc). Modules are automatically interpreted in strict mode.  

***Export***  
There are two ways to `export` a `class`, `function`, or variable:
* Named export, of which there can be many in the same file
* Default export, that is only allowed once per module  
When exporting, the names can be redefined with the keyword `as`.
```
const greeting = name => <span>`Welcome back, ${name}`</span>
export greeting as getGreetingSpan
```  
A module can also "relay" values exported from other modules without the hassle of writing two separate import/export statements. This is often useful when creating a single module concentrating various exports from various modules. 
```
export { x } from "mod";
export { x as v } from "mod";
export * as ns from "mod";
```  

***Import***  
In order to use the import declaration in a source file, the file must be interpreted by the runtime as a module. In HTML, this is done by adding `type="module"` to the `<script>` tag.  
There are four forms of `import` declarations:  
* Named import: `import { export1, export2 as e2 } from "module-name"`
* Default import: `import defaultExport from "module-name"`
* Namespace import: `import * as namespaceImport from "module-name"`
* Side effect import: `import "module-name"`  

The `namespace` import inserts `namespaceImport` into the current scope, containing all the exports from the module located at `/modules/module-name.js`.
```
import * as myModule from "/modules/my-module.js";
```
Above, `myModule` represents a namespace object which contains all exports as properties. For example, if the module imported above includes an export `fun1()`, it would be called like `myModule.fun1()`.

The `side effects` import, runs the module's global code, but doesn't actually import any values.

12. `For ... of` Loop  
The for...of statement executes a loop that operates on a sequence of values sourced from an iterable object. Iterable objects include instances of built-ins such as `Array`, `String`, `TypedArray`, `Map`, `Set`, `NodeList` (and other DOM collections), as well as the `arguments` object (created by the rest parameter).  
```
const countriesArray = [`Canada`, `USA`, `Scotland`, `Spain`, `Ireland`, `Australia`]
for (const country of countriesArray) {
    // ...
}
```  
13. `Sets`  
`Set` objects are collections of values. A value in the `Set` may only occur once; it is unique in the `Set`'s collection. You can iterate through the elements of a `set` in insertion order. The insertion order corresponds to the order in which each element was inserted into the set by the `add()` method.  
`Set` class works in Javascript the way mathematical set notation works. There are no repeated elements. Only unique elements are preserved. A host functions are provided on this class like `add`, `has`, `clear`, etc. 



***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to JavaScript table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#javascript)***

# OOP

<details>
    <summary>
    Table of contents
    </summary>

1. [Concept](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#what-is-oop)
2. [SOLID](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#solid)
3. [Classes](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#classes)
4. [Instances](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#instances)
5. [Inheritance](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#inheritance)
6. [Polymorphism](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#polymorphism)
7. [Encapsulation](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#encapsulation)
8. [Prototype](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#prototype)

</details>

## What is OOP?
Object-oriented programming is about modeling a system as a collection of objects, where each object represents some particular aspect of the system. Objects contain both functions (or methods) and data (or attributes). An object provides a public interface to other code that wants to use it but maintains its own private, internal state.
## SOLID
* ***S***ingle-responsibility Principle
* ***O***pen-closed Principle
* ***L***iskov Substitution Principle
* ***I***nterface Segregation Principle
* ***D***ependency Inversion Principle  
### Single-responsibility Principle
A class should have only one reason to change, meaning that **a class should have only one job**. Only one potential change (database logic, logging logic, and so on.) in the software’s specification should be able to affect the specification of the class. 
### Open-closed Principle
Objects or entities should be open for extension but closed for modification. This means that **a class should be extendable without modifying the class itself**. We should be able to add new functionality without touching the existing code for the class. 
### Liskov Substitution Principle
Let **q(x)** be a property provable about objects of **x** of type **T**. Then **q(y)** should be provable for objects **y** of type **S** where **S is a subtype of T**. This means that **every subclass or derived class should be substitutable for their base or parent class**. 
This means that, given that class B is a subclass of class A, we should be able to pass an object of class B to any method that expects an object of class A and the method should not give any weird output in that case. 
### Interface Segregation Principle
A client should never be forced to implement an interface that it doesn’t use, or **clients shouldn’t be forced to depend on methods they do not use**. Many client-specific interfaces are better than one general-purpose interface. Clients should not be forced to implement a function they do no need. 
### Dependency Inversion Principle
Entities must depend on abstractions, not on concretions. It states that **the high-level module must not depend on the low-level module, but they should depend on abstractions**. We want our classes to be open to extension, so we have reorganized our dependencies to depend on interfaces instead of concrete classes. 
## Classes
They are abstract definitions representing the types of objects we want to have in our system. In JavaScript, classes are “syntactical sugar”, which means that they don’t exist that way in the actual language itself, but are a simpler and more reliable way to write functions, with a couple of added perks like throwing an error if the keyword new isn’t added to create an instance.
```
class Person {
  constructor ( name, lastName, id, salary ) {
    this.name = name
    this.lastName = lastName
    this.id = id 
    this.salary = salary
 }
    getRaise( raise ) { this.salary += raise }
}
```
The class **Person** has 4 data properties and 1 method.
## Instances
On its own, a class doesn't do anything: it's a kind of template for creating concrete objects of that type. Each concrete **Person** we create is called an instance of the **Person** class. The process of creating an instance is performed by a special function called a **constructor**. Programming languages often use the keyword new to signal that a constructor is being called. 
## Inheritance
It’s what happens when two classes derive from the same “superclass”, which means that they share some attributes and methods but can’t access each other’s specific attributes nor methods.
```
class Manager extends Person {
  constructor ( name, lastName, id, salary, employees, authBudget ) {
    this.name = name
    this.lastName = lastName
    this.id = id
    this.salary = salary
    this.employees = employees
    this.authBudget  = authBudget 
 }
    hire( newEmployee, employeeId ) { this.employees[employeeId] = newEmployee } }
    giveRaise( employeeId, raise ) { this.employees[employeeId].salary += raise }
}
``` 
The classes **Manager** and **Employee** are children of the superclass **Person**, from which they extend the **getRaise** method and 4 data attributes.
```
class Employee extends Person {
  constructor ( name, lastName, id, salary, bossId, tasks ) {
      this.name = name
      this.lastName = lastName
      this.id = id 
      this.salary = salary
      this.bossId = bossId
      this.tasks = tasks
 }
      addWork( newTask ) { this.tasks = [ ...this.tasks, newTask ]
}
```
The class **Employee** and **Manager** have similar attributes and methods but **Employee** can’t access the **hire** or **giveRaise** methods, it can, however, access the **getRaise** and **addWork** methods. 
## Polymorphism
When a **method** has the **same name** but a **different implementation in different classes**, is called polymorphism. When a method in a subclass replaces the superclass's implementation, we say that the subclass overrides the version in the superclass.
## Encapsulation
Keeping an object's internal state private, and generally making a clear division between its public interface and its private internal state, is called encapsulation. It enables the programmer to change the internal implementation of an object without having to find and update all the code that uses it.  
* The object's internal state is kept private: it can only be accessed by the object's own methods, not from other objects.
## Prototype
Prototypes are the mechanism by which JavaScript objects inherit features from one another. It’s used to provide additional property to all the objects created from a constructor function. 
### Prototype inheritance
When you try to access a property of an object: if the property can't be found in the object itself, the prototype is searched for the property. If the property still can't be found, then the prototype's prototype is searched, and so on until either the property is found, or the end of the chain is reached, in which case `undefined` is returned.  

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to OOP table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#oop)***

# HTTP

<details>
    <summary>
    Table of contents
    </summary>

1. [What is HTTP?](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#what-is-http)
2. [Basic aspects of HTTP](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#basic-aspects-of-http)
3. [HTTP 2.0](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http-20)
4. [HTTP 3.0](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http-30)
5. [HTTPS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#https)
6. [Connections and what can be controlled by HTTP](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#connections-and-what-can-be-controlled-by-HTTP)
7. [HTTP methods/ verbs](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http-methods-verbs)
8. [HTTP status codes](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http-status-codes)
9. [Session Management](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#session-management)
10. [CORS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#cors)
11. [JSONP](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#jsonp)
12. [JSON Web Token (JWT)](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#json-web-token-jwt)
13. [Single sign-on (SSO)](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#single-sign-on-sso)
14. [OAuth 2.0](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#oauth-20)
15. [JWT vs OAuth](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#jwt-vs-oauth)
16. [Cookies vs Local Storage vs Session Storage](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#cookies-vs-local-storage-vs-session-storage)

</details>

## What is HTTP?
Hypertext Transfer Protocol (HTTP) is an application-layer protocol for fetching resources such as HTML documents. HTTP follows a client-server model, with a client (usually a web browser) opening a connection to make a request, then waiting until it receives a response. HTTP is a stateless protocol, meaning that the server does not keep any data (state) between two requests.
Clients and servers communicate by exchanging individual messages. The messages sent by the client are sent to a server, and are called requests, the messages sent by the server to the client as an answer are called responses.  
### Client: the user-agent
The user-agent is any tool that initiates the request and acts on behalf of the user, typically the Web browser, but it may also be performed by programs used by engineers and Web developers to debug their applications.  
To display a Web page, the browser sends an original request to fetch the HTML document that represents the page. It then parses this file, making additional requests corresponding to execution scripts, CSS, and sub-resources contained within the page (usually images and videos). The Web browser then combines these resources to present the completed Web page. Scripts executed by the browser can fetch more resources in later phases and the browser updates the Web page and/ or its contents accordingly.
### The server
On the opposite side of the communication channel is the server, which serves the document as requested by the client. A server appears as only a single machine virtually; but it may actually be a collection of servers sharing the load, totally or partially generating the document on demand.  
## Basic aspects of HTTP
* **HTTP is simple**: HTTP messages can be read and understood by humans, providing easier testing for developers, and reduced complexity for newcomers. 
* **HTTP is extensible**: HTTP headers make this protocol easy to extend and experiment with. New functionality can even be introduced by a simple agreement between a client and a server about a new header's semantics.
* **HTTP is stateless, but not sessionless**: HTTP is stateless, that is to say that there is no link between two requests being successively carried out on the same connection. This immediately has the prospect of being problematic for users attempting to interact with certain pages coherently, for example, using e-commerce shopping baskets. But while the core of HTTP itself is stateless, HTTP cookies allow the use of stateful sessions. Using header extensibility, HTTP Cookies are added to the workflow, allowing session creation on each HTTP request to share the same context, or the same state.  
## HTTP 2.0
HTTP 2.0 does not modify the application semantics of HTTP in any way. All the core concepts, such as HTTP methods, status codes, URIs, and header fields, remain in place. Instead, HTTP 2.0 modifies how the data is formatted (framed) and transported between the client and server.  
### Goals of HTTP 2.0
* Enable request and response multiplexing (it allows the browser to fire off multiple requests at once on the same connection and receive the requests back in any order)
* Header compression
* Compatibility with the methods, status codes, URIs, and header fields defined by the HTTP 1.1 standard
* Optimized prioritization of requests, making sure that loading for optimal user experience is as fast as possible
* Support for server-side push (technique aimed at reducing latency by loading resources preemptively, even before the client knows they will be needed)
* Server-side backwards compatibility, making sure servers can still serve clients only supporting HTTP 1.1 without any changes
* Transforming to a binary protocol from the text-based HTTP 1.1
### Features
* Binary: Meaning commands use 1s and 0s and not text
* Multiplex: Permits multiple requests and responses to be sent at the same time
* Compression: Compresses headers that have been requested previously to make things more efficient
* Stream prioritization: This allows for the exchange of successive streams at one time
* Server push: The server can send additional information needed for a request before it is requested
* Increased security: HTTP/2 is supported through encrypted connections
### Differences between HTTP 1.0 vs HTTP 2.0
| | HTTP 1.0 | HTTP 2.0 |
|-|----------|----------|
| Compression | No default compression | Built-in compression |
| Performance | Doesn’t have the features to preemptively push resources to the client’s browser | Improving performance for the end-user by sending resources to the client before the browser asks for them |
| Security | Possibility to suffer response splitting attacks due to not using binary formats | By using binary formats in the response headers, these attacks aren’t possible |
| Delivery models | Delivers responses based on a single request | Uses multiplexing and server push to increase the delivery performance |
| Multiplexing | Longer time required to load resources needed for a website | Allows connections made to a web server from to be used to send multiple requests and receive multiple responses |
## HTTP 3.0
HTTP 3.0 will be the first major upgrade to the hypertext transfer protocol since HTTP/2, it runs on QUIC, a new transport protocol that’s designed for mobile-heavy Internet usage. Therefore, HTTP 3.0 relies on the User Datagram Protocol (UDP), not the Transmission Control Protocol (TCP). Switching to UDP will enable faster connections and faster user experience when browsing online.  
### Benefits of HTTP 3.0
* Developing a workaround for the sluggish performance when a smartphone switches from WiFi to cellular data 
* Decreasing the effects of packet loss — when one packet of information does not make it to its destination, it will no longer block all streams of information 
* Faster connection establishment
* Zero round-trip time (0-RTT): For servers they have already connected to, clients can skip the handshake requirement (the process of acknowledging and verifying each other to determine how they will communicate)
* More comprehensive encryption: QUIC’s new approach to handshakes will provide encryption by default and will help mitigate the risk of attacks
* QUIC understands that a site is made up of multiple files, and it won’t blight the entire connection just because one file hasn’t finished loading
### UDP vs TCP  
TCP is more reliable than UDP. UDP is faster for data sending than TCP. UDP makes error checking but no reporting but TCP makes checks for errors and reporting. TCP gives a guarantee that the order of data at receiving end is the same as on sending end while UDP has no such guarantee.  
## HTTPS
Hypertext transfer protocol secure (HTTPS) is the secure version of HTTP. HTTPS is encrypted in order to increase security of data transfer, it adds encryption, authentication, and integrity to the HTTP protocol. HTTPS is not a separate protocol from HTTP. It is simply using TLS/SSL encryption over the HTTP protocol, these certificates verify that a particular provider is who they say they are. The TSL/SSL protocol also encrypts data such as: 
* Request URL (which web page was requested by the client)
* Website content
* Query parameters
* Headers
* Cookies  
HTTPS secures communications by using what’s known as an asymmetric public key infrastructure. This type of security system uses two different keys to encrypt communications between two parties:  
* The private key - this key is controlled by the owner of a website. This key lives on a web server and is used to decrypt information encrypted by the public key.
* The public key - this key is available to everyone who wants to interact with the server in a way that’s secure. Information that’s encrypted by the public key can only be decrypted by the private key.
This means that HTTPS prevents websites from having their information broadcast in a way that’s easily viewed by anyone snooping on the network, and that if the packets were to be intercepted, they would make no sense to the attacker. It also eliminates the ability of unmoderated third parties to inject advertising into web content.  
### Benefits of HTTPS over HTTP
* Integrity and Authentication
* Privacy
* User Experience
* Compatibility: current browser changes are pushing HTTP ever closer to incompatibility
* SEO  
## Connections and what can be controlled by HTTP
HTTP relies on the TCP standard, which is connection-based. Before a client and server can exchange an HTTP request/response pair, they must establish a TCP connection.  
Common features controllable with HTTP:  
* **Caching**: The server can instruct proxies and clients about what to cache and for how long. The client can instruct intermediate cache proxies to ignore the stored document.
* **Relaxing** the origin constraint: To prevent snooping and other privacy invasions, Web browsers enforce strict separation between Web sites. Only pages from the same origin can access all the information of a Web page. Though such a constraint is a burden to the server, HTTP headers can relax this strict separation on the server side, allowing a document to become a patchwork of information sourced from different domains.
* **Authentication**: Some pages may be protected so that only specific users can access them, basic authentication may be provided by HTTP
* **Proxy and tunneling**: Servers or clients are often located on intranets and hide their true IP address from other computers. HTTP requests then go through proxies to cross this network barrier. 
* **Sessions**: Using HTTP cookies allows you to link requests with the state of the server. This creates sessions, despite basic HTTP being a state-less protocol. This is useful not only for e-commerce shopping baskets, but also for any site allowing user configuration of the output.
## HTTP methods/ verbs
| HTTP method | CRUD | Safe* | Idempotent** | Information |
--------------|------|-------|--------------|-------------|
| POST | Create | No | No | It’s used to **create** new resources. In particular, it's used to create subordinate resources. That is, subordinate to some other (e.g. parent) resource. In other words, when creating a new resource, POST to the parent and the service takes care of associating the new resource with the parent, assigning an ID, etc. On successful creation, it returns a Location header with a link to the newly-created resource with the 201 HTTP status. |
| GET | Read  | Yes | Yes | The HTTP GET method is used to **read** a representation of a resource. In the best case scenario, GET returns a representation in XML or JSON and an HTTP response code of 200. In an error case, it most often returns a 404 or 400. |
| PUT | Update: replace | No | In most cases | PUT is most-often utilized for **update** capabilities, PUT-ing to a known resource URI with the request body containing the newly-updated representation of the original resource. On successful update, return 200 (or 204 if not returning any content in the body) from a PUT. |
| PATCH | Update: modify | No | Could be, usually no | PATCH is used to **modify** resources. The PATCH request only needs to contain the changes to the resource, not the complete resource. The body contains a set of instructions describing how a resource currently residing on the server should be modified to produce a new version. Therefore the PATCH body shouldn't just be a modified part of the resource, but in some kind of patch language like JSON Patch or XML Patch. |
| DELETE | Delete  | - | Yes | DELETE is used to **delete** a resource identified by a URI. On successful deletion, return HTTP status 200 along with a response body, perhaps the representation of the deleted item (often demands too much bandwidth), or a wrapped response. Either that or return HTTP status 204 with no response body.  |  

\* can be called without the risk of data corruption or modification  
** making multiple identical requests ends up having the same result as a single request
## HTTP status codes
* 1__ Informational (`100`, `101`)
* 2__ Success (`200`, `201`, `202`, `203`, `204`, `205`, `206`)
* 3__ Redirection (`301`, `302`, `304`, `307`)
* 4__ Client error (`400`, `401`, `403`)
* 5__ Server error (`500`, `501`, `502`, `503`)  
***Note***: Client and Server Error codes have sub-codes ( e.g.: `4__.__` ) that provide a much more detailed explanation of what went wrong.
## Session Management
### What’s a session?
A web session is a sequence of network HTTP request and response transactions associated with the same user. Enforcing correct session management often boils down to the protection and security of the session keys.  
### What is session management used for?
**Facilitating secure interactions between a user and some service** or application. When a user has an ongoing session with a web application, they are submitting requests within their session and oftentimes are providing potentially sensitive information.  
They provide the **ability to establish variables** – such as access rights and localization settings – **which will apply to each and every interaction a user has with the web application for the duration of the session**.  
More importantly, **it is critical that the application has a means of protecting private data belonging to each unique user**, especially within authenticated sessions.  
### Session tokens
They serve to identify a user’s session within the HTTP traffic being exchanged between the application and all of its users. They are needed because **each request is processed independently, even if they are related to the same session**.  
This makes these tokens are vital as they’re passed back and forth between the user and the web application. **Each request and response made will have an associated session token which allows the application to remember distinct information about the client using it**.  
* **Note**: It should be noted that session cookies are not the only means of carrying out a session. It is also possible to include headers that contain session tokens.  
### Vulnerabilities introduced by a lack of session management
* **Session hijacking**: Adversaries can take measures to brute force, predict, and expose session tokens which ultimately can lead to session hijacking, where the malicious party can then impersonate the victim and perform actions from their account. 
* **Session fixation**: can also take place if the properties of a session token allows an attacker to fixate the token of the user once authenticated. It can then also be used to hijack the session. It may arise if the application fails to check for consistent user information throughout the session, reuses session tokens across all forms of access to the service, and sets cookies without proper validity periods.  
### Best practices
* **Set Secure/ HttpOnly Flags on your Cookies**: Refrain from sending sensitive traffic and tokens over an unencrypted channel (HTTP).
* **Generate New Session Cookies**: New session tokens should be generated at every stage of a session: as soon as a user visits the application, when they provide correct credentials, and when a user logs out of their account. A cookie should also expire if the account is inactive for a long period of time.
* **Configure Session Cookies Properly**: Session tokens should be long, unpredictable, and unique. The expiration on persistent cookies should be set for no longer than 30 minutes.  It’s recommended for the scope of domains that are able to access the session cookie to be limited and restrictive.  
## CORS
All data for a webiste should originate from the same server for security reasons. But if data like CSS or JavaScript is attempted to be downloaded from a different server, this access attempt is referred to as a *cross-origin request*. However, if the data exchange is known to both website operators and intended, then the procedure can be permitted. The requested server – i.e. the server from which content is to be downloaded – then allows access via *cross-origin resource sharing*.
However, CORS is not an open invitation for any cross-origin requests. Instead, *the second server permits exclusive access to the first via the HTTP header*, it exactly *describes which server may download the data* and make it finally available to the user.  
### Structure of a CORS header  
In line with the same-origin policy, the details of the origin of a server connection consist of three elements: *host, port, and protocol*. 
A cross-origin request is essentially a HTTP request. Certain methods generally don’t present any problems. GET and HEAD cannot change data and are therefore generally not perceived as a security risk. The situation is different with *PATCH*, *PUT* or *DELETE*: These make *harmful interference possible*. For this reason, cross-origin resource sharing must also be activated here. Accordingly, CORS isn’t only able to include information on the permitted origin, but also on which HTTP requests are allowed by the source.
### Advantages and Disadvantages of CORS
CORS serves to circumvent an inherently secure default setting – namely the same-origin policy (SOP). The SOP, in turn, is an effective way to prevent potentially dangerous connections. However, the internet is often based on these cross-origin requests, since many connections from one host to others are certainly desired in many cases.  
### CORS bypass
```
GET / HTTP/1.1 
Host: https://foo.example.com
(...)
Origin: https://other.example.com
```
Server response:  
```
HTTP/1.1 200 OK
(...)
Access-Control-Allow-Origin: https://other.example.com
Keep-Alive: timeout=2, max=100
Connection: Keep-Alive
Transfer-Encoding: chunked
Content-Type: application/xml
[...JsonData]
```
With preflight requests for method POST  to check if the method is safe:  
```
OPTIONS / HTTP/1.1 
Host: https://foo.example.com
(...) 
Origin: https://other.example.com
Access-Control-Request-Method: POST 
Access-Control-Request-Headers: X-CUSTOM, Content-Type
```
Response from the server, allowing POST, GET  
```
HTTP/1.1 204 No Content (...) 
Access-Control-Allow-Origin: https://other.example.com
Access-Control-Allow-Methods: POST, GET, OPTIONS 
Access-Control-Allow-Headers: X-CUSTOM, Content-Type 
Access-Control-Max-Age: 86400
```  
## JSONP
It’s a method that helps structured data be sent between different domains in JSON format. The acronym stands for *JSON* (JavaScript Object Notation) with *Padding*. To bypass the same-origin policy when requesting files from other domains, JSONP does not use the “XMLHttpRequest” object, as the usual JSON code does, but rather the element “script” including a function call. Unlike other files, scripts can also be transferred across domains without the SOP being violated.  
JSONP solves the same-origin policy problem using `<script>` elements. As many domains as you like can be specified in the `“src”` attribute of this element, and the SOP directive does not apply here. *Therefore, the attribute can also be used to distinguish URLs that belong to a foreign domain and return JSON code and other files*. In such a case, the script itself is exclusively used as a service provider, which sends the JSONP query to the respective web server without having its own effect. Like this:  
```
<script type="text/javascript">
    <codesnippet>
    src="http://not-origin-url.com/getjson?jsonp=exampleCallback">
</script>
```
If this JSONP script is embedded in the HTML code of a website and then run by any client, JSON data is accessed by the foreign domain `“not-origin-url.com”`. The query string `“?jsonp=exampleCallback”` tells the contacted server that it is a JSONP query. In addition, the information is supplied that it should send the requested data as a parameter of the JavaScript function `“exampleCallback”`.  
In order for the client to be able to subsequently process the data, the server packs this again as a parameter in a JavaScript function, which is already predefined in the web browser and is communicated to the server in the query string (or query part) of the URL. The server then generates the appropriate JavaScript code including the queried information as a parameter – in the case of this example, a name-value pair – and returns it to the client. The function call is then executed by the browser as if it were listed directly in the HTML code of the source page. The browser is thereby able to process the data retrieved from the third-party URL.
`exampleCallback( {"name":"test", "value":1} );`
## JSON Web Token
JSON web token is an open standard that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. Because of its relatively small size, a JWT can be sent through a URL, through a POST parameter, or inside an HTTP header, and it is transmitted quickly. A JWT contains all the required information about an entity to avoid querying a database more than once. 
### Benefits
* More compact
* More secure
* More common: JSON parsers are common in most programming languages because they map directly to objects
* Easier to process
### Use
* Authentication
* Authorization: Once a user is successfully logged in, an application may request to access routes, services, or resources (e.g., APIs) on behalf of that user. To do so, in every request, it must pass an Access Token, which may be in the form of a JWT. Single Sign-on (SSO) widely uses JWT because of the small overhead of the format, and its ability to easily be used across different domains.
* Information Exchange: JWTs are a good way of securely transmitting information between parties because they can be signed, which means you can be sure that the senders are who they say they are.
## Single sign-on (SSO)  
Single sign-on (SSO) is an authentication method that enables users to securely authenticate with multiple applications and websites by using just one set of credentials. This trust relationship is often based upon a certificate that is exchanged between the identity provider and the service provider. The token that is received by the Service Provider is validated according to the trust relationship that was set up between the Service Provider and the Identity Provider during the initial configuration.  
## OAuth 2.0
OAuth 2.0, which stands for “Open Authorization”, is a standard designed to allow a website or application to access resources hosted by other web apps on behalf of a user. It provides consented access and restricts actions of what the client app can perform on resources on behalf of the user, without ever sharing the user's credentials.   
OAuth 2.0 is an authorization protocol and NOT an authentication protocol. As such, it is designed primarily as a means of granting access to a set of resources, for example, remote APIs or user’s data. OAuth 2.0 uses Access Tokens.  
## JWT vs OAuth
| JWT | OAuth |
|-----|-------|
| Mainly used for APIs | Web, browser, APIs, other apps |
| Token format | Defining authorization protocols |
| Client-side storage | Client and server-side storage |
## Cookies vs Local Storage vs Session Storage  
| Criteria | Cookies | Local Storage | Session Storage |
|----------|---------|---------------|-----------------|
| Max size | 4 Kb | 5 Mb | 5Mb |
| Can auto-expire | Yes | No | Yes |
| Server-side access | Yes | No | No | 
| Data transferred on each HTTP request (sent with requests) | Yes | No | No | 
| Lifetime | Specified | Until deleted | Tab closed | 
| Accessible by | All windows | All windows | Tab only | 
| Cleared by | PHP, Js, Automatically | Js | Js, Automatically |  

All:
* User-editable
* User can block
* Only supports strings as data types
* High browser support
* Can be accessed on the client-side
* Non-secure data storage

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to HTTP table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#http)***

# SEO  
SEO (Search Engine Optimization) is the process of making a website more visible in search results. Search engines crawl the web, following links from page to page, and index the content found.  
Crawlers follow rules, if you follow those rules closely when doing SEO for a website, you give the site the best chances of showing up among the first results, increasing traffic and possibly revenue.  
SEO combines official search engine guidelines, empirical knowledge, and theoretical knowledge from science papers or patents. SEO methods fall into three broad categories:  
* Technical: Tag the content using semantic HTML. When exploring the website, crawlers should only find the content you want indexed.
* Copywriting: Write content using your visitors' vocabulary. Use text as well as images so that crawlers can understand the subject. 
* Popularity: You get most traffic when other established sites link to your site.
You must ensure that your crawlers/bots get the closest experience to that of your user’s, and that your site (and any fetches that need to be executed) loads within 5 seconds or less.  

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  

# Security 

<details>
    <summary>
    Table of contents
    </summary>

1. [Validation](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#validation)
2. [(MFA) Multi-Factor Authentication](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#mfa-multi-factor-authentication)
3. [OWASP and top 10 guidelines](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#owasp-and-top-10-guidelines)
4. [(DoS) Denial of Service](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#dos-denial-of-service)
5. [Brute Force Attacks](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#brute-force-attacks)
6. [(XSS) Cross-Site Scripting Attacks](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#xss-cross-site-scripting-attacks)

</details>

## Validation
Before submitting data to the server, it is important to ensure all required form controls are filled out, in the correct format. This is called client-side form validation, and helps ensure data submitted matches the requirements set forth in the various form controls.  
Client-side validation is an initial check and an important feature of good user experience; by catching invalid data on the client-side, the user can fix it straight away. If it gets to the server and is then rejected, a noticeable delay is caused by a round trip to the server and then back to the client-side to tell the user to fix their data.  
This is called form validation. When you enter data, the browser and/or the web server will check to see that the data is in the correct format and within the constraints set by the application. Validation done in the browser is called client-side validation, while validation done on the server is called server-side validation.  
Never trust data passed to your server from the client. Even if your form is validating correctly and preventing malformed input on the client-side, a malicious user can still alter the network request.  
There are 3 main reasons to validate data:
* We want to get the right data, in the right format. Our applications won't work properly if our users' data is stored in the wrong format, is incorrect, or is omitted altogether.
* We want to protect our users' data. Forcing our users to enter secure passwords makes it easier to protect their account information.
* We want to protect ourselves. There are many ways that malicious users can misuse unprotected forms to damage the application.  
## (MFA) Multi-Factor Authentication
Multi-factor Authentication (MFA) is an authentication method that requires the user to provide two or more verification factors to gain access to a resource such as an application, online account, or a VPN. MFA is a core component of a strong identity and access management (IAM) policy. Rather than just asking for a username and password, MFA requires one or more additional verification factors, which decreases the likelihood of a successful cyber attack.  
### MFA vs Two-Factor Authentication
MFA is often used interchangeably with two-factor authentication (2FA). 2FA is a subset of MFA since 2FA restricts the number of factors that are required to only two factors, while MFA can be two or more.  
### Benefits
It will enhance your organization's security by requiring your users to identify themselves by more than a username and password. While important, usernames and passwords are vulnerable to brute force attacks and can be stolen by third parties. Enforcing the use of an MFA factor like a thumbprint or physical hardware key means increased confidence that your organization will stay safe from cyber criminals.  
### Three Main Types of MFA Authentication Methods
* Things you know (**knowledge**), such as a password or PIN
    * Answers to personal security questions
    * Password
    * OTPs (Can be both Knowledge and Possession - You know the OTP and you have to have something in your Possession to get it like your phone)
* Things you have (**possession**), such as a badge or smartphone
    * OTPs generated by smartphone apps
    * OTPs sent via text or email
    * Access badges, USB devices, Smart Cards or fobs or security keys
    * Software tokens and certificates
* Things you are (**inherence**), such as a biometric like fingerprints or voice recognition
    * Fingerprints, facial recognition, voice, retina or iris scanning or other Biometrics
    * Behavioral analysis  
### Other types
* Location-based
* Adaptive Authentication or Risk-based Authentication
    * From where is the user when trying to access information?
    * When you are trying to access company information? During your normal hours or during "off hours"?
    * What kind of device is used? Is it the same one used yesterday?
    * Is the connection via private network or a public network?  
## OWASP and top 10 guidelines
The OWASP Top 10 is a standard awareness document for developers and web application security. It represents a broad consensus about the most critical security risks to web applications.  
### Top 10 security risks
| Security Risk | Vulnerabilities | Possible solutions |
|---------------|-----------------|--------------------|
| Broken Access Control | Access control enforces policy such that users cannot act outside of their intended permissions. Failures typically lead to unauthorized information disclosure, modification, or destruction of all data or performing a business function outside the user's limits. | Access control is only effective in trusted server-side code or server-less API, where the attacker cannot modify the access control check or metadata. |
| Cryptographic Failures | Failures related to cryptography which often leads to sensitive data exposure or system compromise. Some APIs rely on insecure data transmission methods, which attackers can exploit to gain access to usernames, passwords, and other sensitive information. | Data encryption, tokenization, proper key management, and disabling response caching can all help reduce the risk of sensitive data exposure. |
| Injection | Injection occurs when an attacker exploits insecure code to inject their own code into a program. Because the program is unable to determine code inserted in this way from its own code, attackers are able to use injection attacks to access secure areas and confidential information as though they are trusted users. Some of the more common injections are SQL, NoSQL, OS command, Object Relational Mapping (ORM), LDAP, and Expression Language (EL) or Object Graph Navigation Library (OGNL) injection. | Application security testing can reveal injection flaws and suggest remediation techniques such as stripping special characters from user input or writing parameterized SQL queries. |
| Insecure Design | It focuses on risks related to design flaws, it calls for more use of threat modeling, secure design patterns and principles, and reference architectures. One of the factors that contribute to insecure design is the lack of business risk profiling inherent in the software or system being developed, and thus the failure to determine what level of security design is required. | Establish and use a secure development lifecycle with AppSec professionals to help evaluate and design security and privacy-related controls. Establish and use a library of secure design patterns or paved road ready to use components. Use threat modeling for critical authentication, access control, business logic, and key flows. Integrate security language and controls into user stories. Integrate plausibility checks at each tier of your application (from frontend to backend). Write unit and integration tests to validate that all critical flows are resistant to the threat model. Compile use-cases and misuse-cases for each tier of your application. Segregate tier layers on the system and network layers depending on the exposure and protection needs. Segregate tenants robustly by design throughout all tiers. Limit resource consumption by user or service. |
| Security Misconfiguration | Just like misconfigured access controls, more general security configuration errors are huge risks that give attackers quick, easy access to sensitive data and site areas. | Dynamic testing can help discover misconfigured security in the application. Secure installation processes should be implemented like a minimal platform without any unnecessary features, components, documentation, and samples, a task to review and update the configurations appropriate to all security notes, updates, and patches as part of the patch management process and review cloud storage permissions. |
| Vulnerable and Outdated Components | o matter how secure your own code is, attackers can exploit APIs, dependencies and other third-party components if they are not themselves secure. Also, the app may be at risk if you do not scan for vulnerabilities regularly and subscribe to security bulletins related to the components you use, you do not know the versions of all components you use (both client-side and server-side). This includes components you directly use as well as nested dependencies. Or if the software is vulnerable, unsupported, or out of date. | There should be a patch management process in place to remove unused dependencies, unnecessary features, components, files, and documentation. Continuously inventory the versions of both client-side and server-side components. Use software composition analysis tools to automate the process. Only obtain components from official sources over secure links. |
| Identification and Authentication Failures | Confirmation of the user's identity, authentication, and session management is critical to protect against authentication-related attacks. An app may be at risk if: it permits automated attacks such as credential stuffing, where the attacker has a list of valid usernames and passwords, allows brute force and other automated attacks, permits default, weak, or well-known passwords, such as "Password1" or "admin/admin", uses plain text, encrypted, or weakly hashed passwords data stores, exposes session identifier in the URL, or reuses session identifier after successful login. | Where possible, implement multi-factor authentication to prevent automated credential stuffing, brute force, and stolen credential reuse attacks. Do not ship or deploy with any default credentials, particularly for admin users. Implement weak password checks, such as testing new or changed passwords against the top 10,000 worst passwords list. |
| Software and Data Integrity Failures | Software and data integrity failures relate to code and infrastructure that does not protect against integrity violations. An example of this is where an application relies upon plugins, libraries, or modules from untrusted sources, repositories, and content delivery networks (CDNs). An insecure CI/CD pipeline can introduce the potential for unauthorized access, malicious code, or system compromise. | Use digital signatures or similar mechanisms to verify the software or data is from the expected source and has not been altered. Ensure libraries and dependencies, such as npm or Maven, are consuming trusted repositories. If you have a higher risk profile, consider hosting an internal known-good repository that's vetted. Ensure that there is a review process for code and configuration changes to minimize the chance that malicious code or configuration could be introduced into your software pipeline. |
| Security Logging and Monitoring Failures | Without logging and monitoring, breaches cannot be detected. Insufficient logging, detection, monitoring, and active response occurs any time. Apps could be at risk if auditable events, such as logins, failed logins, and high-value transactions, are not logged, warnings and errors generate no, inadequate, or unclear log messages, logs of applications and APIs are not monitored for suspicious activity, or if logs are only stored locally. | Ensure all login, access control, and server-side input validation failures can be logged with sufficient user context to identify suspicious or malicious accounts and held for enough time to allow delayed forensic analysis. Ensure that logs are generated in a format that log management solutions can easily consume. Ensure log data is encoded correctly to prevent injections or attacks on the logging or monitoring systems. Ensure high-value transactions have an audit trail with integrity controls to prevent tampering or deletion, such as append-only database tables or similar. |
| Server-Side Request Forgery | SSRF flaws occur whenever a web application is fetching a remote resource without validating the user-supplied URL. It allows an attacker to coerce the application to send a crafted request to an unexpected destination, even when protected by a firewall, VPN, or another type of network access control list (ACL). | Sanitize and validate all client-supplied input data. Enforce the URL schema, port, and destination with a positive allow list. Do not send raw responses to clients. Disable HTTP redirections. Be aware of the URL consistency to avoid attacks such as DNS rebinding and “time of check, time of use” (TOCTOU) race conditions. Also, Don't deploy other security relevant services on front systems (e.g. OpenID). Control local traffic on these systems (e.g. localhost). For frontends with dedicated and manageable user groups use network encryption (e.g. VPNs) on independent systems to consider very high protection needs. |
## (DoS) Denial of Service 
**DoS events are often brought about by a service's underlying systems being overloaded**. They can be caused by legitimate overloading of the servers or they can be malicious attacks. The key difference between legitimate denial of service (eg, Black Friday browsing) and an attack is that an attack generally happens with no warning. Therefore, the service cannot plan to handle the increased load. Malicious attacks can take one of two general forms: Denial of Service (DoS) or Distributed Denial of Service (DDoS).
* A **Denial of Service** attack uses only a small number of attacking systems (possibly just one) to overload the target. Nowadays, a simple DoS attack is often simple to deflect as the attacker is easy to identify and block. One notable exception here may be industrial control systems, where equipment may have a low tolerance to bogus traffic, or may be connected via low bandwidth links that are easily saturated.
* In a **Distributed Denial of Service** attack, the attacker enlists the help of (many) thousands of Internet users to each generate a small number of requests which, added together, overload the target. These participants may either be willing accomplices (such as attacks initiated by loosely organized illegal "hacktivist" groups) or by unwitting victims whose machines have been infected with malware.  

When a website suffers a DoS attack, the apparent effect will depend on your perspective. For the average user, it appears that the site has simply stopped displaying content. For businesses, it could mean that the online systems they depend upon have ceased to respond. The symptoms of a DoS attack against industrial control systems may include the inability to retrieve sensor data, or control critical processes.  

DoS attacks can range in duration and may target more than one site or system at a time. An attack becomes a 'distributed denial of service', referred to as “DDoS”, when it comes from multiple computers (or vectors) instead of just one. This is the most common form of DoS attack on websites.  
## Brute Force Attacks
A brute force attack uses trial-and-error to guess login info, encryption keys, or find a hidden web page. Hackers work through all possible combinations hoping to guess correctly. These attacks are done by ‘brute force’ meaning they use excessive forceful attempts to try and ‘force’ their way into your private account(s).   
### Types of Brute Force Attacks
* **Simple Brute Force Attacks**: hackers attempt to logically guess your credentials — completely unassisted from software tools or other means. These can reveal extremely simple passwords and PINs. 
* **Dictionary Attacks**: a hacker chooses a target and runs possible passwords against that username.
* **Hybrid Brute Force Attacks**: these hackers blend outside means with their logical guesses to attempt a break-in. A hybrid attack usually mixes dictionary and brute force attacks. These attacks are used to figure out combo passwords that mix common words with random characters.
* **Reverse Brute Force Attacks**: a reverse brute force attack reverses the attack strategy by starting with a known password. Then hackers search millions of usernames until they find a match. Many of these criminals start with leaked passwords that are available online from existing data breaches.
* **Credential Stuffing**: if a hacker has a username-password combo that works for one website, they’ll try it in tons of others as well. Since users have been known to reuse login info across many websites, they are the exclusive targets of an attack like this.  
## (XSS) Cross-Site Scripting Attacks  
Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.  
An attacker can use XSS to send a malicious script to an unsuspecting user. The end user’s browser has no way to know that the script should not be trusted, and will execute the script. Because it thinks the script came from a trusted source, the malicious script can access any cookies, session tokens, or other sensitive information retained by the browser and used with that site. These scripts can even rewrite the content of the HTML page.  
### Prevention  
* Ensuring that all variables go through validation and are then escaped or sanitized is known as perfect injection resistance. Any variable that does not go through this process is a potential weakness. Frameworks make it easy to ensure variables are correctly validated and escaped or sanitized. However, frameworks aren't perfect and security gaps still exist in popular frameworks like React and Angular. Output Encoding and HTML Sanitization help address those gaps.
```
<div attr="$varUnsafe">
<div attr="*x" onblur="alert(1)*"> // Example Attack
```
* It’s critical to use quotation marks like `"` or `'` to surround your variables. Quoting makes it difficult to change the context a variable operates in, which helps prevent XSS. Quoting also significantly reduces the `characterset` that you need to encode, making your application more reliable and the encoding easier to implement. 
* If you're using JavaScript for writing to a HTML Attribute, look at the `.setAttribute` and `[attribute]` methods which will automatically HTML Attribute Encode. Those are Safe Sinks as long as the attribute name is hardcoded and innocuous, like `id` or `class`. Generally, attributes that accept JavaScript, such as onClick, are NOT safe to use with untrusted attribute values.
* For JSON, verify that the `Content-Type` header is `application/json` and not `text/html` to prevent XSS.
* The **only ‘safe’ location for placing variables in JavaScript is inside a “quoted data value”**. All other contexts are unsafe and you should not place variable data in them. 
* Encode all characters using the `\xHH` format. Encoding libraries often have a `EncodeForJavaScript` or similar to support this function. 
* Examples of “Quoted Data Values”: 
```
<script>alert('$varUnsafe')</script>
<script>x='$varUnsafe'</script>
<div onmouseover="'$varUnsafe'"</div>
```
* There will be situations where you use a URL in different contexts. The most common one would be adding it to an `href` or `src` attribute of an `<a>` tag. In these scenarios, you should do URL encoding, followed by HTML attribute encoding.
```
url = "https://site.com?data=" + urlencode(parameter)
<a href='attributeEncode(url)'>link</a>
```
If you're using JavaScript to construct a URL Query Value, look into using `window.encodeURIComponent(x)`. This is a *Safe Sink* and will automatically URL encode data in it.

***[Go back to the main table of contents](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#table-of-contents)***  
***[Go back to Security table of content](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#security)***

# Bibliography  
### GIT
* [Atlassian feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)  
* [Atlassian - Git branches](https://www.atlassian.com/git/tutorials/using-branches#:~:text=In%20Git%2C%20branches%20are%20a,branch%20to%20encapsulate%20your%20changes)
* [Atlassian - Git hooks](https://www.atlassian.com/git/tutorials/git-hooks)
* [Atlassian - GitFlow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow#:~:text=Gitflow%20is%20a%20legacy%20Git,software%20development%20and%20DevOps%20practices.)  
* [Atlassian - Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
* [GIT - Git branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [GIT - Git tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
* [GIT - Git stashing](https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)
* [GitHub - Git commands](https://training.github.com/downloads/github-git-cheat-sheet.pdf)
* [Microsoft - Git branching strategies](https://learn.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops)  
* [Squash, merge or rebase?](https://matt-rickard.com/squash-merge-or-rebase)  
* [When to use squash, merge, and rebase?](https://medium.com/@shubhpaliwal98/when-to-use-squash-merge-and-rebase-43da3571dcbe)  
### HTML
* [Java T Point - XHTML](https://www.javatpoint.com/what-is-xhtml)  
* [Meta tags - Meta tags](https://metatags.io/)  
* [MDN - Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
* [MDN - Data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
* [MDN - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)  
* [MDN - Input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) 
* [MDN - Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
* [MDN - What is Accessibility?](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility)
* [MDN Learn - HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML)  
* [The Open Graph Protocol](https://ogp.me/)
* [W3 Schools - Data attributes](https://www.w3schools.com/tags/att_data-.asp)
* [W3 Schools - Meta tags](https://www.w3schools.com/tags/tag_meta.asp)  
* [W3 Schools - Semantic HTML elements](https://www.w3schools.com/html/html5_semantic_elements.asp)
* [W3 Schools - XHTML](https://www.w3schools.com/html/html_xhtml.asp)  
### CSS
* [CSS tricks - BEM](https://css-tricks.com/bem-101/)
* [CSS tricks - Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [CSS tricks - Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
* [CSS tricks - position](https://css-tricks.com/almanac/properties/p/position/)
* [Elementor - What’s The Difference Between PX, EM, REM, %, VW, and VH?](https://elementor.com/help/whats-the-difference-between-px-em-rem-vw-and-vh/)
* [Emotionstudios - 6 reasons to use a CSS prerpocessor](https://www.emotionstudios.net/trending/6-reasons-you-should-use-a-css-preprocessor-2/)
* [Hongkiat - The basics of OOCSS](https://www.hongkiat.com/blog/basics-of-object-oriented-css/)
* [JavaTPoint - Materialize CSS](https://www.javatpoint.com/materialize-css-tutorial)
* [Learn.co - Layout](https://learn.co/lessons/css-layout-types)
* [MDN - Cascading Stylesheets](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [MDN - CSS basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
* [MDN - CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model)
* [MDN - CSS preprocessors](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor)
* [MDN - CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* [MDN - Introduction to the CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
* [MDN - Position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* [MDN - Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
* [MDN - The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
* [MDN - Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* [Medium - What is the difference between HTML and DOM?](https://medium.com/@leetcore/what-is-the-difference-between-html-and-dom-c704ed3d1305)
* [Quickstart - Bootstrap](https://www.quickstart.com/blog/what-is-bootstrap-and-how-does-it-work/)
* [Swaps - SMACSS](https://swapps.com/blog/what-is-smacss-and-how-to-use-it/)
* [Wikipedia - Bootstrap](https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework))
### JavaScript
* [Board - Top 10 Features of ES6](https://www.boardinfinity.com/blog/top-10-features-of-es6)
* [LoginRadius - AJAX and XHR](https://blog.loginradius.com/engineering/ajax-and-xhr-using-plain-javascript/)
* [JavaScript Info - Bubbling](https://javascript.info/bubbling-and-capturing)
* [JavaScript Tutorial - Closures](https://www.javascripttutorial.net/javascript-closure/)
* [MDN - Async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
* [MDN - Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
* [MDN - Callbacks](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
* [MDN - Document Object Model (DOM)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
* [MDN - Export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
* [MDN - Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
* [MDN - for ... of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
* [MDN - Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
* [MDN - Import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
* [MDN - Introduction to Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
* [MDN - Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* [MDN - Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#a_background_on_modules)
* [MDN - Object.is()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is)  
* [MDN - Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [MDN - Rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters#the_difference_between_rest_parameters_and_the_arguments_object)
* [MDN - Sets](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
* [MDN - Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
* [MDN - Spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
* [MDN - Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
* [MDN - XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
* [MDN Learn - What is JavaScript?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)  
* [Medium - 7 Javascript ES6+ Features You Must Know in 2020](https://medium.com/the-codehub/7-javascript-es6-features-you-must-know-in-2020-fe126cd65f7b)
### OOP
* [Digital Ocean](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
* [Free Code Camp](https://www.freecodecamp.org/news/solid-principles-explained-in-plain-english/)
* [MDN - OOP](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_programming)
* [MDN - Prototypes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)
### HTTP
* [Auth0 - Auth0](https://auth0.com/intro-to-iam/what-is-oauth-2/)
* [Auth0 - JSON Web Token](https://auth0.com/docs/secure/tokens/json-web-tokens)
* [Cloudflare - HTTPS](https://www.cloudflare.com/learning/ssl/what-is-https/)
* [Cloudflare - HTTP 3.0](https://www.cloudflare.com/learning/performance/what-is-http3/)
* [IONOS - CORS](https://www.ionos.com/digitalguide/websites/web-development/cross-origin-resource-sharing/)
* [IONOS - JSONP](https://www.ionos.com/digitalguide/websites/web-development/jsonp/)
* [IPWithEase - UDP vs TCP](https://ipwithease.com/tcp-vs-udp/)
* [MDN - An overview of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
* [Medium - CORS bypass](https://medium.com/the-crazy-coder/a-comprehensive-understanding-of-cors-all-frontend-developers-better-to-have-3ae46d35f19e)
* [Microsoft Learn - Status codes](https://learn.microsoft.com/en-us/troubleshoot/developer/webapps/iis/www-administration-management/http-status-code#the-http-status-codes)
* [OneLogin - SSO](https://www.onelogin.com/learn/how-single-sign-on-works)
* [RestAPITutorial - HTTP](https://www.restapitutorial.com/lessons/httpmethods.html)
* [SSL - HTTPS](https://www.ssl.com/faqs/what-is-https/)
* [StackOverflow - Cookies vs Session Storage vs Local Storage](https://stackoverflow.com/questions/19867599/what-is-the-difference-between-localstorage-sessionstorage-session-and-cookies)
* [TheNewstack - HTTP 3.0](https://thenewstack.io/http-3-is-now-a-standard-why-use-it-and-how-to-get-started/)
* [Upwork - HTTP 2.0](https://www.upwork.com/resources/what-is-http2)
* [WallArm](https://www.wallarm.com/what/oauth-vs-jwt-detailed-comparison)
### SEO
* [MDN - SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO)
### Security
* [Kaspersky - Brute Force Attacks](https://www.kaspersky.com/resource-center/definitions/brute-force-attack)
* [MDN - Validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
* [OneLogin - MFA](https://www.onelogin.com/learn/what-is-mfa)
* [OWASP - Top 10 Security Guidelines](https://owasp.org/www-project-top-ten/)
* [OWASP - XSS](https://owasp.org/www-community/attacks/xss/)
* [Veracode - OWASP](https://www.veracode.com/security/owasp-top-10)