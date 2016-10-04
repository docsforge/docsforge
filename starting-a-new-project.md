Starting a New Project
======================

Each project docs contain two types of pages - Public API pages, and manual documentation pages.

Documentation Page Types
------------------------

-  **Public API Pages**

    Automatically created from your source code using [Doxygen](http://www.stack.nl/~dimitri/doxygen/). 
   
    The default is that any namespace/class/method/etc... with permission `public` or `protected` will be documented into its own page. 
    
    You can [customize](http://docsforge.com/help/customizing-the-public-api/) which pages you wish to hide or display.
   
    You can edit these pages online using [Markdown](http://docsforge.com/help/markdown-cheat-sheet/), and let the page documentation diverge from the code documentation. 
    This supports leaving the code documentation short for other developers, while the online documentation can be longer for end users.
    
    You can track changes relative to the automatic version.
   
-  **Manual Documentation Pages**
   
    Documentation pages (or tutorial pages) that are not created from the source code.
    
    They can however have a mirror to an existing file in your docs directory.
    
    The content is editable online using markdown. 

Tutorial Levels and Sidebar
---------------------------

Any page can be marked as part of the **Basic** or **Advanced** tutorial, to allow for easy access in the project sidebar.

- The **Basic Tutorial** should get new users starting with the basic features.

- The **Advanced Tutorial** should be for users that need more customization.

- The **Public API** should be for users that need even more customization. It is advisable to mark key API pages as part of the basic/advanced tutorial.

The project main page is the first page amongst the `Basic Tutorial` pages. When starting a new project, the default first page is `Getting Started`, but feel free to change it.


Tracking Page Changes and History
---------------------------------

Each page holds two content versions - the current content version, and an auto-documented version.

The current content version can be edited online, while preserving a copy of the auto-documented version.
Any page that contains changes will have a <code>[≠]</code> button, that allow maintainers to review changes.
Additionally, maintainers can view changes in all pages through the project settings <code><i class="fa fa-cog"></i></code>.

For Public API pages, the auto-documented version is created automatically from the source code.

For manual documentation pages, the auto-documented version is created if linked to a markdown file (extention `.md`) in your repository.
By default, the link is to the same name as exists in your docs repository.
For example, an online documentation page named `installation`, and a markdown file `docs/installation.md`. 

Auto documented pages (both API and manual) are created when adding a new version or recreating autodoc - actions that are available through the project settings <code><i class="fa fa-cog"></i></code>.


Project Settings
----------------

You can customize your project through the project settings <code><i class="fa fa-cog"></i></code> button.

You can edit the project brief, tags, maintainers, autodoc settings, etc...


Adding a New Version
--------------------

When adding a new code version to an existing project, a new documentation version will be created.

To help get the new documentation version up and running fast, the following will be done: 

-   The auto-documentation will generate new public API pages, while keeping any changes that have manually been made in the previous version.

-   All manual documentation pages will be copied from a previous version. An 'auto-documented' version will also be created if a the page is linked to a markdown file in the repository.

-   Basic/Advanced tags will be copied.

When this process is complete, the contents of each documentation version will be kept separately and can diverge. The documentation of the old version can be changed without it affecting the new version and vice versa.

After adding a new version, it is advised to review the `changed pages`, to see differences in page contents between the current and auto-documented version.

At the moment, we support up till 5 different versions per project.

Discussions
-----------

Registered users can start discussions on any project. The aim is mainly for Q&A regarding documentation.

Discussions are not only linked to the project, but also to a specific documentation page.

This allows users viewing a documentation page, to scroll down and see relevant discussion without needing to search through all project discussions. 

When viewing a page, any discussions created about it and its descendants will be visible as page discussions.
For example, when viewing a class page, all discussions asked about itself and any of its methods pages will be visible.