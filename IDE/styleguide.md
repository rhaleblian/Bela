# Bela IDE style guide

This is a document that specifies how the html/css/js are written for this IDE so consistency can be maintained in the future.

## CSS 

### Structure

The only stylesheet is belastyles.css. This is a css file that is compiled from the sass files in `../dev/sass`. *Don't edit the style sheet itself* - it will just be overwritten the next time Gulp compiles the sass directory. 

In the sass directory there is a `belastyles.scss` file, which includes all the relevant components from the `/components` file. In the future I'd really like these compoennts to be auto-included from the Sample scss library, but not at the moment.

These components include files for the colour scheme and fonts that are design pattern compliant. We should be keeping things like the colour variable names consistent across every web property and platform so updates to the sass components can be dropped into the directory and not break absolutely everything. (I had this problem moving from the new IDE that was developed in isolation to the live one on Bela, before I had solid naming conventions. Trust me, it's a buttpain.)

All legacy css that was surplus to requirements (such as GoldenLayout) has been removed.

### Class and ID naming conventions

- *IDs*: Generally these are only used for structural elements (of which there is - and should only ever be - one). The names of these are camelcased, #likeThis.
- *Classes*: Classes are lower case and are separated by hyphens, `.like-this`.
- *Naming*: All classes and IDs should have descriptive names. Good: `#editingPane`. Less good: `#contentWindow`.

## JavaScript

There is one file with all the js that has the front end relevant bits: `bela.js`. 

## Text data and HTML partials

Previously the text data for popups and other elements was buried in the JS file for the relevant element as HTML partials. This means that it was difficult to edit these, or to be consistent across all written communication.

The text data for the IDE is now contained in, and included from, `dev/src/site-data.json`. 

## To Do: General 
- Incorporate new diagrams for Mini and CTAG (tabbed windows).
- Incorporate these and the existing diagram into the JS better than they currently are (which is not very well at all).
- Bring new skin and front-end elements up to date. Sync with pattern library.
- Look at simplifying - or at least documenting - how the current elements of Node and the MVC works, in case updates are needed in the future.
- Get rid of as much external CSS cruft as possible, such as goldenlayout.
- Look for/amend any legacy naming conventions (such as references to BeagleRT). Do the same for CSS names and document what these are.