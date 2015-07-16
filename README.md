# Amy Hemmeter
## Personal / Professional Website for Amy Hemmeter

View online at: http://ahemmeter.github.io/

**Note**: Most of the information below is more than you'll need to know. I do
recommend you read "Getting Started" and most of "Editing Pages: Detailed 
Description", though. You might also want to poke "Getting a Custom Domain 
Name" with a stick.

### Getting Started

This site uses a technology called [Jekyll](http://jekyllrb.com/) running on
[GitHub Pages](https://pages.github.com/) to make site management easy. What
that means is that the code for the website template is in one place, and the
content is elsewhere. It also means you can edit the content files extremely
easily.

All of the content pages for this site are in the content directory.

If you're reading this on GitHub, try simply clicking on one of the content
files (`index.md`, `research.md`, or `cv.md`), then click the pencil icon in
the top-right (it says "Edit this File" when you hover over it). Change the
text, then commit the changes (you can also add a description of what you
changed so that you can review the change history later). The online version of
the website gets updated a few seconds after you commit your changes.

### Editing Pages: Detailed Description

Page content is written in Markdown. Markdown is a simple document formatting
language that is designed to be naturally readable by humans while being
unambiguously parsable by computers. It accomodates most of the same semantics
as HTML: creating titles, emphasizing words or sentences, making bulleted or
numbered lists, creating tables of data, inserting images and links, etc.

You can probably just modify the Markdown files (`index.md`, `research.md`, or
`cv.md`) directly without reading anything about Markdown beforehand, since it's
basically plain text. Still, there are some neat syntax things which might not
be obvious. If you want to do something (like insert an image) and you don't
know how, try reading the [GitHub Markdown
Guide](https://help.github.com/articles/markdown-basics/).

All of the markdown files that are meant to be published on the web need to
start with a few lines called the "yaml frontmatter". That just means it needs
to have a space to declare some configuration. Each page that gets published has
the following frontmatter at the top. The layout parameter defines which
"template" gets loaded. This website currently only has one template (which I've
called the "default" template), so all pages are loading that one for now.

    ---
    layout: default
    ---

If you want to create a new page through the GitHub web interface, go to the
folder you want that page to be (this can be the root folder), then find the "+"
icon in the path (above the list of files) and click it. That makes a new file
in the current directory. If you want it to be a page on the site, give it a
name with the `.md` file extension. Make sure to include the YAML frontmatter.
You can also make an HTML file instead of the markdown file.

If you need to upload new files (like pictures that you want to embed in one of
your webpages), you can't do that with the web interface. :disappointed: You'll
need to download the repository and use Git to make and upload changes.

### Editing the Template Content (Navigation, Footer, etc.)

The "template" for the website (including the header image, the navigation, and
the footer) is written in HTML. This is the `_layouts/default.html` file. If you
need to change anything in the template, just modify that file. The file needs
to have a special templating directive that says where the page content gets
inserted, so make sure there is a line somewhere in the file that says `{{
content }}`. You can insert some other templating directives if you like, and
they'll be replaced with values (usually defined in each page's YAML
frontmatter). [Here](http://jekyllrb.com/docs/templates/) is a list of
templating directives you can use.

If you make a new template (maybe some pages need a different format), just
create a new HTML file in the `_layouts/` directory. It can be named anything
(as long as it has a `.html` file extension), but it needs to have the `{{
content }}` line somewhere in it. Then, modify any pages (the markdown files) to
use the new layout by changing the YAML frontmatter "layout" parameter to match
your new filename (but without the `.html` extension).

### Editing the Stylesheet

The styling is written in a "CSS Pre-processor" language called
[Sass](http://sass-lang.com/). It's basically CSS, except with a bunch of really
great language features slapped on top to make things much easier. You can do
things like define variables and nest selectors. Normally, you would need to
"compile" the Sass code into CSS code (Since browsers can't understand Sass
code), but Jekyll does this automatically as long as the Sass code has YAML
frontmatter. That's why the `css/style.scss` file needs to have the two lines of
three dashes (I also put a comment between the lines, but that's optional) at
the start of the file.

So if you make a new `.scss` file, put some empty frontmatter at the top and
upload it to the `css/` directory. You can then link to that file from an HTML
file or a template, but refer to it as if its file extension were `.css`. So, if
you made a Sass file called `css/mysass.scss`, you could include the following
line in an HTML document to use that stylesheet:

    <link rel="stylesheet" href="/css/mysass.css">

### Managing the Website with Git (Instead of the GitHub Web Interface)

If you don't want to use the GitHub web interface (or want to do something you
can't do on here), you can control the repository with much more precision by
downloading it, making changes, then uploading the changes using the Git
software. You can install [Git for the Command Line](https://git-scm.com/) and
do this [interactive tutorial](https://try.github.io/levels/1/challenges/1) to
learn how to use it. You can also install [GitHub for
Windows](https://windows.github.com/) if you'd prefer to use a Graphical
Interface rather than learn a command line tool.

Basically, the process boils down to this:

1. Clone (download) the Repository using Git into a folder on your computer. You
   only need to do this once.
2. Check if there are any updates you need to download (this is called "pulling"
   from the repository).
3. Modify / create files as you normally would.
4. Add any files you've created or modified to the "index" using Git (this is
   just a list of changes). This is called "staging".
5. Commit your changes using Git (basically, mark them as ready to upload).
6. Push (upload) your changes back into this repository using Git.

There are more advance features, but that's all you need to get started.

### Getting a Custom Domain Name

If you want a custom URL (like amyhemmeter.com or something), you can do that
and still host your website on here for free. This is actually pretty cheap
(like, $10/year) because you don't have to pay for hosting as well. I use
http://namecheap.com to pay for my domain name. I think you might be able to get
amyhemmeter.me for free on namecheap if you can prove you're a student. You can
get a domain from any "Domain Name Registrar". Once you've purchased it, you'll
need to use [this
guide](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/)
to configure your website here to use it.
