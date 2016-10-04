Customizing the Public API
==========================

When you add a new project, The default is to create pages for **any public** function/class/etc... found in your repository. 

In your project's **autodoc settings**, you can customize which parts of your public API you want to display, and which you want to hide.

There are various customization options.

Exclude or Include Files and Directories
-------------------------------------
You can exclude or include specific files or directories from being auto-documented.

Paths are relative to your repository root directory. You can exclude or include multiple files and directories by separating them with a new line.

**Examples:**

1.  Writing the following in the include section:

        src/public
        src/myproj/myproj.h

    will result in auto-documentation only of the directory `src/public` and the file `src/myproj/myproj.h`

2.  Writing the following in the exclude section:

        tests

    will result in auto-documentation disregarding any code written in the `tests` directory.
    
!!! note
    In many projects, the public API for end users is separated from the rest of the code.
    
!!! note
    In C/C++, including header files without including their complementary implementation files will result in API function pages with no body.  

!!! note
    If both include and exclude conditions exist, both will be met.
    
Exclude or Include Specific API Pages
-----------------------------------------
You can exclude or include specific public API pages (functions, classes, namespaces, etc...) from being auto-documented.

You can edit which API pages you wish to display and which you wish to hide.

The easiest way to exclude specific pages is to go to a public API page and delete it using the <code><i class="fa fa-trash-o"></i></code> icon on the right top corner. 
You will then notice that the page_path has been added to the autodoc settings.

Another method is to add the **page_path** directly to the excluded list in your **autodoc settings**.

The page_path is a concatenation of **all** the scopes (functions, classes, namespaces, etc...) that led to the page.

**Examples:**

1.  Writing the following in the excluded_paths section:

        namespace-my_namespace/class-my_class/function-my_func
        namespace-my_namespace/class-my_other_class

    will exclude `my_func` and `my_other_class` (and all it's methods, see note.).
        
2.  Writing the following condition in the included_paths section:

        namespace-my_other_namespace

    will create documentation only of API pages that are inside the scope `my_other_namespace`.

The **page_path** can also be located from the url - http://docsforge.com/project_id/project_name/docs/version_name/page_path/.

!!! note
    Any descendant of an excluded page will be deleted as well. Therefore, if your want to remove a certain class and all its methods, you only need to exclude the class page_path.
     
!!! note
    If both include and exclude conditions exist, both will be met.

!!! tip
    The most consistent way to remove a specific API page, is to change the permission in the code to private.

Additional Customization
------------------------
The following settings can also be set to `True` or `False`:

*   Regard names that start with a single underscore (_) as 'private', disabling their documentation. `Default=True` only in Python, but a common convention in other languages.

*   Document keyword static as part of the Public API. `Default=True` in all languages except C.

*   Document keyword protected as part of the Public API. `Default=True` in all languages.

*   Disable auto-documentation. No Public API page will be created. `Default=False` in all languages.

Maximum Number of API Pages Reached
-----------------------------------
A project with too many public API pages can be confusing to end users.

At this moment, if there are more than 5,000 public API pages, DocsForge will not save or display your public API in the sidebar.

If there are more than 500 public API pages, the project maintainers will see an alert on the top of the page, advising them to decrease the number of displayed public API pages.

If your project exceeded this limit, we strongly encourage you to reduce the amount of public API pages.

We suggest:

-   The most consistent way is to go over your code and change to private anything that should not be public.

-   If you do not wish to change your code, you can tailor which parts of your public API will be displayed, as explained in the beginning of this page.


Advantages of a Small Public API
--------------------------------

Your code API plays a big factor on whether or not people will be using your code. The simpler it is, the better. At least the **Basic usage** should be extremely simple to use.

The advantages of a small public API are:

1. Easier to learn and use.

2. Easier to maintain.

3. Easier for end users to replace if maintenance stops.

!!! note
    A fascinating presentation by Google on [How to design a good API and why it matters](https://www.youtube.com/watch?v=aAb7hSCtvGw).


Extensions
----------

You can separate your project into **Core** and **Extensions**. 

You can build support for 3rd party extensions, and let other programmers extend your code. This will both reduce the maintenance for you, and get others to help in your project.

You can mark any project as an extension to another core project through your project settings <code><i class="fa fa-cog"></i></code>. You don't need a permission from the core project to become an extension. Both projects will then be linked. In the **Core** project, a link to the extension will appear in the sidebar. In the **Extension** project, a link to the core project will appear in the top bar.