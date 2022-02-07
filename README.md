# org-nested

This helper allows you to create links within Org-files that jump to nested sections without the use of header-specific ID properties.



## Example

Assume you have a diary which looks like this:

```
* 01/01/2022
  * Meetings
    ..
  * TODO
    ..
* 02/02/2022
  * Meetings
    ..
  * TODO
    ..
```

Now assume you wish to link to the `Meetings` section within the `02/02/2022` entry:

* You __cannot__ simply link to `[[Meetings]]` because it is not unique.
  * Although you could certainly generate a unique property to allow that link.
* You could link to `[[02/02/2022]]` and then search forward to "Meetings"
  * That's what this package allows.

The link you will add would be:

```
[[02/02/2022#Meetings]]
```



## Caveats

The link will **not** be visible on any HTML-exports.



## Installation

Save this file to a directory upon your load-path, and then require it after you've loaded `org-mode`:

```lisp
(require 'org-nested)

```

I personally configure `org-mode` to allow searches for internal links to match sub-strings of headlines, rather than requiring complete matches.  This isn't required, but it's a nice companion:

```lisp
(setq org-link-search-must-match-exact-headline nil)
```



## Bugs?

Please report them as issues.
