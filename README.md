# The Local Ibex

This repository hosts the source for the hiking website ___The Local Ibex___.  All of the pages for this website are written in Markdown and have been converted to HTML using [Hugo](https://gohugo.io/) in conjunction with the [Doks](https://getdoks.org/) theme.

To view the actual website for The Local Ibex, see [here](https://pat-marty.github.io/the-local-ibex/).

## The Basics

Here is some general information about how the website works to get you started. Below is an approximate workflow for all of the moving parts that are behind this
website:

![A workflow for how this site is generated.](/assets/images/website_workflow.png)

### What is HTML?

HTML is the standard language used for displaying webpages in a browser such as Chrome or Firefox.  We won't actually be writing any HTML here (unless you want to change something within the inner workings of the website) as we'll be writing all of the webpages in Markdown which we'll then convert to HTML using a tool called Hugo.

Pretty much every website (including the one we generate here) use both CSS and JavaScript in addition to HTML.  Each of these have a specific functionality:
- **HTML:** Contents of the page
- **CSS:** Tells the browser how to style/display the HTML page
- **JavaScript:** Lets the user interact with the webpage

Again though, we won't be writing any CSS or JavaScript here since we do everything in Markdown.

### What is Markdown?

Markdown is a very user friendly markup language that can be used for creating formatted text using a plain text editor.  This very document you're reading right now was written in Markdown!

All Markdown documents have the extension `.md` and can be edited in any text editor such as Notepad or Visual Studio Code.  Unlike a word processor such as Microsoft Word, the user explicitly writes the formatting which the document should possess directly within the Markdown document.  For example, something like:

```
This is some text.  And here's the wave equation just for proof of concept:

$$
    \frac{1}{c^2 (\textbf{x})} \partial_t^2 \varphi(\mathbf{x}, t) + \nabla^2 \varphi = f (\textbf{x}, t)
$$

Here's also some ~~crossed-through text~~, **bold text**, and some *italicized text*.
```

which would look like this when rendered:

> This is some text.  And here's the wave equation just for proof of concept:
> 
> <img src="https://render.githubusercontent.com/render/math?math=\frac{1}{c^2 (\textbf{x})} \partial_t^2 \varphi(\mathbf{x}, t) + \nabla^2 \varphi (\mathbf{x}, t) = f (\textbf{x}, t)">
>
> Here's also some ~~crossed-through text~~, **bold text**, and some *italicized text*.

There are a ton of different formatting options that you can add into your Markdown files to make them look pretty.  See [here](https://www.markdownguide.org/cheat-sheet/) for some additional details on some of the standard formatting that is available in Markdown.

You can nicely render Markdown documents in something such as **Visual Studio Code** where you can have a side-by-side of the raw Markdown document beside the rendered text.  See [here](https://code.visualstudio.com/docs/languages/markdown) for an example of how to do this.

### What is Hugo?

At its most basic level, [Hugo](https://gohugo.io/) is a tool that lets you convert Markdown files to HTML, CSS, and JavaScript.  With Hugo, you can write your entire website in Markdown and then easily convert it to HTML.  The handy thing with this is that Hugo does all of the formatting in the background and builds a visually appealing website with little additional user intervention.  While this ease of use comes at the cost of customizability, there are a ton of different possible "themes" we can choose from to make the website look nice.

### What is Doks?

Hugo uses so-called "themes" for stylizing the look of the website; here we use the [Doks](https://getdoks.org/) theme.  Doks was initially intended for creating user documentation for various software tools.  However, it coincidently serves as a convenient structure for this hiking website as well.

You can check out some of the other available themes [here](https://themes.gohugo.io/).

### How does the GitHub Repository work?

[GitHub](https://github.com/) is a popular platform for hosting code within software projects.  We're using GitHub here for hosting both the code which is used for building the website as well as the website itself.  The place where everything for this project lives is called a "repository".

This project uses two separate repositories:
- [the-local-ibex-source](https://github.com/pat-marty/the-local-ibex-source): Where the "raw" documents for the website live
- [the-local-ibex](https://pat-marty.github.io/the-local-ibex/): Where the actual website is hosted

We've split up these two repositories here just for the sake of convenience.  The website in `the-local-ibex` is run through **GitHub Pages** — a very handy static website hosting service that's offered through GitHub.

Something that makes GitHub very different from something such as Google Drive or Dropbox is that GitHub uses something known as "version control".  I won't go into the nitty gritty of what this is/exactly how it works, but the gist of it is that it keeps track of who made what changes to the repository so that we can easily go back to a previous version of the website in case someone were to accidentally break the website.  

---

## Suggested Tools
Some of the core tools required:
- [Visual Studio Code](https://code.visualstudio.com/)
- [Hugo](https://gohugo.io/)

## How to Create New Pages

Here are some instructions for creating new website pages.  Note that all text is created using Markdown.  For a quick crash course in how to properly format things in Markdown, see [here](https://www.markdownguide.org/cheat-sheet/).

1. Create a new markdown (`.md` file extension) file in the respective directory under `/content/en/docs/`
    - Eg. Adding a hike for the Dufourspitze would involve creating the file `/content/en/docs/hiking/dufourspitze.md`
    - It is recommended to make a copy of the `_template.md` file and then rename it to the above so that you have a starting point to work from
    - Make sure that the names of your files follow the naming conventions outlined below
2. Create a new directory where your images will be stored
    - Eg. Adding the directory `/content/en/docs/hiking/dufourspitze/` for the above example
3. Write the article in the Markdown file.  Be sure to fill out the header information at the top of the Markdown file especially:
    - `title`
    - `description`
    - `authors` (put as a list like `['Bruno']` or `['Bruno', 'Pat']`)
    - `categories` (difficulty rating)
    - `date` (hiking date)
    - `lastmod` (current date you are writing this article on)
4. Build the HTML pages by running the `hugo` command in the terminal from the root directory of the repository
5. Upload the following documents to the GitHub repository:
    - Markdown file
    - Images
    - Built HTML pages in the `/public/` directory

## Guidelines and Conventions

Here are a few best practices to follow when creating new posts and documenting fresh tours.

### Adding Pictures

Use the following snippet of code for embedding images into a Markdown page:

```
<p align="center">
    <img src="filename.jpg" alt="" width="100%" class="center">
    <em>A very nice and descriptive caption.</em>
</p>
```

In the above snippet you should:
- Change the name of the image from `filename.jpg` to whatever the filename of the image is that you want to add.
- Add a descriptive caption for the image between the `<em>` and `</em>` tags.
- You can adjust the width of the image by modifying the `100%` to something different.  It is suggested to use `width="100%"` for landscape images and `width="75%"` for portrait images.

As of the time of writing, all images are hosted in the same GitHub repository where all of the source code is located.  This may be changed in the future as the website continues to grow, but for now, this is a convenient solution.  Here are a few things to keep in mind when adding pictures to the repository:
- All images should be saved as either `.png` or `.jpg` format
- In the interest of keeping the size of the repository down, try limiting the size of individual images to about 3 MB or less.  You can reduce the size of images by importing them into some image editing software like [Gimp](https://www.gimp.org/), [Lightroom](https://www.adobe.com/products/photoshop-lightroom.html), or [Digital Photo Professional](https://www.canon-europe.com/support/camera_software/#EOSDPP) and exporting the image at a reduced resolution.

### Metadata for New Pages

Every HTML page generated using Hugo requires some `yaml` style metadata at the start of the markdown page.  This information helps Hugo during the process of converting the Markdown documents to HTML by providing information such as:
- Name of the webpage
- Who wrote it
- When it was written
- Additional info (eg. what sport the the tour involved, difficulty rating, etc.)

Here's an example of what should be included in the metadata at the start of every tour Markdown document:
```
---
title: Piz Random
description: Some random mountain.
toc: true
authors: ['Pat', 'Bruno']
tags:
categories: 'T6'
series:
date: '2020-01-01'
lastmod: '2021-01-01'
draft: false
menu:
  docs:
    parent: "hiking"
---
```

### Naming Conventions

There are a few naming conventions that you should follow to ensure that the Markdown to HTML conversion cooperates.  Here are a few things to watch out for:
- Ensure that the name between tour names and its respective pictures directory match
    - Eg. if you have a tour under `hikes/matterhorn.md`, make sure that the directory that contains all of the relevant pictures for the tour is under `hikes/matterhorn/`
    - If these names to not match exactly, then the images will not display properly in the resulting webpages
- Use underscores instead of spaces or dashes
    - `banana_phone.md` is good, `banana phone.md` or `banana-phone.md` are not
- Avoid capital letters in file names
    - `bananaphone.md` is good, `Bananaphone.md` is not

