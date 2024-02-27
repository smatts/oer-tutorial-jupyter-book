# Reference
<!--  style="background-color:#ff5959;" -->
> This part is still under construction.

> You have your OER in different output formats, complete with your own content and metadata and it is even already indexed in [oersi](https://oersi.org),
> but you want to learn more about what you can do with this template?

In this part of the tutorial, we highlight further configuration options, Markdown basics, workflows in GitHub and much more.

## Configuration options
> In the repository, there is a file called `config.yml`. This gives you some configuration options concerning the automatic generation of your OER, like the order of your content.

In the top level of the repository, there is a file named `config.yml`. It includes configuration for these four things:

* `output`: state the output formats that you want to be automatically generated
* `generate_landingpage`: decide whether or not to create a landing page
* `content_files`: define the order of your content files
* `generate_reuse_note`: decide whether or not to generate a reuse note on the generated documents

### Editing this file

As you are editing this file, you have to consider the format of this file. This file is a `yaml` file. This file has a specific structure you have to follow, or else the automatic generator will not work.

As you can see when opening the file, the structure looks like this:

``` yaml
output:
  - format: asciidoc
  - format: epub
  - format: html
  - format: pdf
generate_landingpage: true
# content_files:  # uncomment this to set the order of the documents (default alphabetical)
#   - chapter01.md
#   - chapter02.md
#   - chapter03.md
#   - chapter04.md
generate_reuse_note: true
```

So we have to consider the identation and the correct symbols to use. If we want to use the `content_files` option, we uncomment this by deleting the `#` before each line and removing the residual spaces:

``` yaml
output:
  - format: asciidoc
  - format: epub
  - format: html
  - format: pdf
generate_landingpage: true
content_files:  # uncomment this to set the order of the documents (default alphabetical)
  - chapter01.md
  - chapter02.md
  - chapter03.md
  - chapter04.md
generate_reuse_note: true
```

The dashes (`-`) have to start with two spaces before the dash and then one space after the dash.
Basically, just make sure the number of spaces is consistent throughout the whole file.

### Video tutorial
!?[Config file explained](videos/config.mp4)

## Markdown
> For a good overview on what Markdown is and what you can do with it, you can check out the Markdown guide from Matt Cone:
> 
> * [What is Markdown and why should I use it?](https://www.markdownguide.org/getting-started/)
> 
> * [Basic Syntax](https://www.markdownguide.org/basic-syntax/)

### Headings

To create a heading, add number signs (`#`) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (`<h3>`), use three number signs (e.g., `### My Header`) [[1](https://www.markdownguide.org/basic-syntax/)].

<!-- data-type="none" -->
| Heading level | How to write it | How it looks |
|---|---|---|
| Heading level 1 | # Heading level 1 | <h1>Heading level 1</h1> |
| Heading level 2 | ## Heading level 2 | <h2>Heading level 2</h2> |
| Heading level 3 | ### Heading level 3 | <h3>Heading level 3</h3> |
| Heading level 4 | #### Heading level 4 | <h4>Heading level 4</h4> |
| Heading level 5 | ##### Heading level 5 | <h5>Heading level 5</h5> |
| Heading level 6 | ###### Heading level 6 | <h6>Heading level 6</h6> |

### Markdown elements
<!-- data-type="none" -->
| Element | How to write it | How it looks |
|---|---|---|
| Bold | \*\*Bold text\*\* | **Bold text** |
| Italic | \*Italicized text\* | *Italic text* |
| Blockquote | > blockquote | To be seen at the top of this section |
| Ordered list | 1. First item <br> 2. Second item | 1. First item <br> 2. Second item |
| Unordered list | - First item <br> - Second item | - First item <br> - Second item |
| Code | \`code\` | `code` |
| Horizontal rule | \-\-\- | --- |
| Link | [Link text](link url) | [Markdown Guide](https://www.markdownguide.org) |
| Image | ![Alt text](image url) | ![Image showing the text placeholder](http://via.placeholder.com/50x50) |

[1] Matt Cone, [markdownguide.org](https://www.markdownguide.org), [Basic Syntax](https://www.markdownguide.org/basic-syntax/)

### Links to other sections

You can link to sections within your document using the link syntax shown in the table above.
The links are generated from the heading:

* `# Heading` -> `#heading` (You can reference it like this: `[Heading](#heading)`)
* `# Heading 1` -> `#heading-1`
* `### Lower heading level!` -> `#lower-heading-level`

You can also set custom links like this:

`## My heading {#custom-id}`

Now the link to this section is `#custom-id`.

## Git
<!--  style="background-color:#ff5959;" -->
> This part is still under construction.

> This section only gives a brief overview of Git.
> If you want to learn more about it, check out the free online [Pro Git](https://git-scm.com/book/en/v2) textbook.

### What is Git and why should you use it?
Have you ever worked on different versions of a document, or even with different people?
Then you likely know how hard it is to keep track of changes, and how easy to accidentally overwrite them.
Git is a tool that helps with that. **It is a so-called *version control system*.**
To learn more about version control, you can check out the [Version Control section of the Pro Git book](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control).

## Working offline
<!--  style="background-color:#ff5959;" -->
> This part is still under construction.

> If you want to work offline, using some kind of text editor (similar to working with Word on documents), some necessary steps and background knowledge are required.

Since we are working with `Git` (see [Git section](#git) for more information), and want to publish our content on `GitHub` (see [GitHub section](#github)), we have to find a way to bring our offline work online. For this, you should check out the [Git section](#git).

### Editors
First off, let's talk about editors.

Of course, you know text editors like *Word* or *LibreOffice*.
However, for the automatic output generation used in this template, we need *plain text* that is easily readable for machines.
This is why we are working with [Markdown](#markdown-1) to format our *plain text*.

There are a lot of editors that help you with writing text using the Markdown syntax.
On of the ways they help is by showing a rendered preview as you type.

![Editor](_static/img/vscode.png "VSCodium, the open source version of the popular editor VSCode")

The editor you can see in the screenshot is called **VSCodium**, which is the open source version of a popular editor **VSCode** by Microsoft.
In this editor, you can install lots of plugins that can help you out.
It also has a built-in Git functionality which helps you publish your changes.

## Put your changes online
Your local changes have to be uploaded.
This brings some possible challenges.

You could simply copy the whole file content, click on edit on the file in the repository that you want to update, delete that file's contents, paste your new content and commit those changes.
But that is rather tedious and unnecessary. Neither is it the way Git is supposed to be used.

We will stick to the *VSCodium*/*VSCode* editor for this example.

### Immediate update in OERSI
> Your OER will be automatically inserted into the [OERSI](https://oersi.org) if you fulfill the requirements listed in the [insert your OER into OERSI section](#insert-your-oer-in-oersi). The resources are updated each night. If you want to see **immediate** changes, you can use the (experimental) record updater.

Head to the [record updater page](https://oersi.org/resources/pages/de/record_update/) on [oersi.org](https://oersi.org).
Insert the link to your GitHub repository or to the generated landing page of your OER.

![Record updater](_static/img/record-updater.png)

Then, click on update. Your OER should now be updated in the OERSI.

## Different formats
> After following this tutorial, we have different output formats like a HTML version, a PDF version and so on.
> We could, however, generate all kinds of different formats, for example a course format like this tutorial.

Using this template is not the only option to host OER using GitHub.
For example, this tutorial runs using LiaScript.

Below you find a short list of several possible formats your OER could use. <br><br>

nicht unbedingt github

### [Markdown documents template](https://github.com/TIBHannover/markdown-documents-template)

This is the template that is described in this tutorial.
As you know by now, it takes your Markdown files, puts them together and generates different formats from them.
These formats are linked to and can be downloaded from the landing page that is generated using GitHub Actions and GitHub Pages.

| | |
|-|-|
| ✅ | Easy setup with our template |
| ✅ | Automatic generation of different formats |
| ✅ | Can include interactive elements |
| ✅ | Always have the newest changes online |
| ✅ | GitHub automatically tracks changes made to your files | 
| ✅ | Easy collaboration with others on GitHub |
| ✅ | Customizable with CSS |
| ❌ | Needs a GitHub account |
| ❌ | Customizing can be tricky / Limited page layout customization ? textfluss gestaltung |


### [Markdown slides template](https://github.com/TIBHannover/markdown-slides-template)

The Markdown slides template is very similar to the Markdown documents template from this tutorial.
But instead of creating a single text document, the slides template creates several slides.
For this, you create one Markdown file for one set of slides and the template generates the slides in both HTML and PDF format and shows a list of all generated slides together with preview images in a GitHub Page.

| | |
|-|-|
| ✅ | Easy automatically generated slides in two formats |
| ✅ | Easy setup with our template |
| ✅ | Automatic up to date overview page |
| ✅ | Always have the newest changes online |
| ✅ | Automatically tracks changes made to your files |
| ✅ | Easy collaboration with others |
| ❌ | Slides are only partly customizable |
| ❌ | Needs a GitHub account |

### [LiaScript](https://liascript.github.io)

LiaScript takes a markdown file and automatically generates a course format from it.
The tutorial you are currently viewing is actually made with LiaScript!
Or rather, the Markdown file this tutorial is written in is being interpreted by LiaScript, which therewith generated this course.
So all you really need is a Markdown file.

| | |
|-|-|
| ✅ | Super easy to set up, just need one markdown file somewhere on the internet! |
| ✅ | Runs everywhere  |
| ✅ | Large number of elements you can use like: ... graphen, tabellen, karten, ... |
| ✅ | No installation, everything happens live & online |
| ✅ | Easy to click through the different sections |
| ✅ | Automatic translation into many different languages |
| ✅ | Interactive elements and extended Markdown can be used |
| ✅ | responsive website, good mobile view |
| ❌ | Only online, no download |
| ❌ | Depends on one single service |
| ❌ | Only one Markdown file at a time |

Including resources outside of Github might not work (to prevent cross-site-scripting attacks)
--> einzelne fallstricke ausprobieren und dann tipps erläutern

### [Static Site Generators](https://github.com/collections/static-site-generators)

A static site generator generates a static site.
Typically, it will be possible to also write your content using Markdown, but at the same time, you will be able to edit your layout and include more elements yourself which the static site generator then uses to create your web page.
Of course, this requires some basic knowledge about HTML, CSS and the static site generator you are using.
You should also be familiar with the command line or using GitHub Actions yourself.

| | |
|-|-|
| ✅ | Creates a lightweight web page |
| ✅ | Very customizable |
| ❌ | Not automatically responsive |
| ❌ | Not for complete web dev beginners |
| ❌ | Takes longer to get a first version running / more configuration and technical know-how necessary |

### [JupyterBooks](https://jupyterbook.org/en/stable/intro.html)

Jupyter Book is a free and open source tool to create online books.
You can create sections and subsections that you can click through.
They are added to a table of contents, which can be viewed in a sidebar or accessed via a menu.
It is also possible to include executable content.
Moreover, you can download your book in both Markdown and PDF format.
You can start out with a template supplied by the software itself.

| | |
|-|-|
| ✅ | Creates online books with sections and table of contents to click through| 
| ✅ | Allows lots of configuration and structuring| 
| ✅ | Supplies download as Markdown and PDF| 
| ✅ | Can include executable content| 
| ❌ | Not for complete beginners (you will need to run commands from the command line or create a GitHub Action)| 
| ❌ | Configuration is done via config files, which can be tricky to learn if you are unfamiliar with coding| 

## Troubleshooting
Something does not work?
Maybe you find your issue right here.

### I do not see my changes
You have added your content and your metadata but can not see your changes in your landing page and generated documents?
Following these steps might help you.

1. Delete your cache and reload your page/document

Often, the old version of the page is still loaded in your browser's cache.
If you reload the page or document by hitting `Ctrl + F5` together, you can reload your page while deleting the cache of that page.
You can also open your page or document in a new private tab or window, as the browser usually does not use its cache there.

2. Check your file names and content

Check if your file name contains characters like **spaces**. These are not allowed and cause the document generation to break.

Also, ensure that there are no special characters like emojis or other unicode characters in your documents. Our document processor does not understand these characters, which also leads to breaking the document generation.

3. Check your media

Sometimes, images or videos can cause the document generation to break.
Usually, this happens when you use an unsupported format. Stick to widespread formats like `png` and `jpg` to be sure.

## FAQ

### Can I upload non-text files like PDF files?
Yes, you can! Git however won't be able to track changes made to those files, it can only track _that_ it was changed.

### How can I change how images are displayed?
You can change image size, placement and more by using HTML-tags. HTML is, like Markdown, a markup language, basically converting plain text into formatted output.

**Change image size**:

`<img src="path/to/image.png" alt="Image description" style="width:100px"; />`

The **src** contains the path to your image, the **alt** contains an image description, and the **style** contains the information about the image size. Here, we have set the **width** to **100 pixels**. You can also set the height (but note that setting a fixed width *and* height that does not match the original ratio of the image can skew it), and of course, change the size how you want.

**Make text float around an image**:

`<img src="path/to/image.png" alt="Image description" style="float: left; margin: 0 20px 20px 0;" />`

Again, **src** contains the path to the image and **alt** its description. Now in the **style** tag, you find two directions: `float: left;` places your image on the left and allows other content like text to *float* around it. The tag `margin: 0 20px 20px 0;` is about spacing: you can set a margin around your image (or element in general), leaving that space blank. Here, the values for the margin are sorted top, right, bottom, left. So in this case, there is a margin of 20 pixels to the right and to the bottom. This prevents the text to directly "touch" your image, making it easier to read.

### Why are the direct paths to my files different?
You may have encountered links containing `https://raw.githubusercontent.com/`. If you are wondering what this means and why GitHub changes your URL this way, the reason is the following:

When you go through your repository's files in GitHub, you see them embedded in the GitHub web page, which lets you do several things like edit, delete, show its history and so on. So when you have a link to this file, the link points to this web page and not to the file itself (which is called the *raw* file). If you want to access the file *only*, so the raw file, GitHub allows you to do that by changing the URL to `https://raw.githubusercontent.com/`.

### How can I create a new folder?
You can not create an empty folder. This means you have to add files in GitHub *in* that new folder. Either create a new file and change the path to that new folder (i.e. instead of creating a new file `file.md`, write it with a new folder like `newfolder/file.md`, a new folder will be automatically created) or upload a non-empty folder.

