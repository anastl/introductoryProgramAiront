# Handbook  

# Table of Contents
1. [GIT](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#git)
2. [HTML](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#html)
3. [CSS](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css)
4. [JavaScript](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#javascript)
5. [SEO](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#seo)
6. [Bibliography](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#bibliography)  

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
16. [CSS preprocessors](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#css-preprocessors)
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

# JavaScript  

<details>
    <summary>
    Table of contents
    </summary>

1. [Basic syntax](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#basic-syntax)
2. [DOM](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#dom)
3. [Strict](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#strict)
4. [Scope](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#scope)
5. [Hoisting](https://github.com/anastl/introductoryProgramAiront/blob/master/studyMaterials/studyMaterial.md#hoisting)
</details>

## Basic syntax
It’s a scripting language that enables you to create dynamically updating content, control multimedia, etc. JavaScript is a lightweight and dynamic interpreted language, used to create client-side dynamic pages. It is an open-source and cross-platform language. It allows implicit type conversion.  
### Comments
* // Single line comment
* /* Multiple  
lines comment */  
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
* Arithmetic: `\+` `\*` `\-` `/` `%`  
* Assignment: `=` `+=` `-=` `/=` `*=` `%=`  
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
* Strict equals ( === )
    * Compares values ***and*** type 
    * Only on primitive types
* Loose equals ( == )
    * Only on primitive types
* Object.is() === true if ***both*** elements to compare are:
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

# SEO  
SEO (Search Engine Optimization) is the process of making a website more visible in search results. Search engines crawl the web, following links from page to page, and index the content found.  
Crawlers follow rules, if you follow those rules closely when doing SEO for a website, you give the site the best chances of showing up among the first results, increasing traffic and possibly revenue.  
SEO combines official search engine guidelines, empirical knowledge, and theoretical knowledge from science papers or patents. SEO methods fall into three broad categories:  
* Technical: Tag the content using semantic HTML. When exploring the website, crawlers should only find the content you want indexed.
* Copywriting: Write content using your visitors' vocabulary. Use text as well as images so that crawlers can understand the subject. 
* Popularity: You get most traffic when other established sites link to your site.
You must ensure that your crawlers/bots get the closest experience to that of your user’s, and that your site (and any fetches that need to be executed) loads within 5 seconds or less.  

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
* [The basics of OOCSS](https://www.hongkiat.com/blog/basics-of-object-oriented-css/)
### JavaScript
* [MDN - Document Object Model (DOM)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
* [MDN - Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
* [MDN - Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* [MDN - Object.is()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is)  
* [MDN - Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
* [MDN - Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
* [MDN Learn - What is JavaScript?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)  
### SEO
* [MDN - SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO)