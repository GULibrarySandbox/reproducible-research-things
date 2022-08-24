# lesson-template

Learn-Static Lesson Template is a minimal Jekyll theme with sidebar content nav for creating lesson and workshop websites using Markdown.
The sidebar nav supports pages nested into sections to help organize your lesson content. 
The template provides Liquid includes to simplify adding Bootstrap components to your pages.

{% capture aboutworkshop %}

## Topic and aims

Reproducible Research Things Lessons

The idea with this workshop/documentation is to help researchers move along the path in reproducibility. It doesn’t take them from 0 – 100 but if they can implement one or two things, it can help them later down the track. The ‘be better than you were yesterday’ idea. 

Our plan is do develop slides that pose the following questions and the corresponding answers and links.


Q1) What if a key person from your lab disappeared one day (family or personal emergency, no longer contactable)? Could you all continue your work? Would you know where all your data is stored? Could you keep running effectively for 1 month? 1 year?

* Bus factor
* Documentation
* Naming conventions
* Folder structure for readability
* Automation
* git


Q2) Imagine you're travelling and lose your laptop bag with your external hard drives? Or your office is robbed? Could you continue your work? Is your data backed up? Encrypted? 

* Research storage 
* Security- encrypt your hard drive
* Separating identified variables


Q3) Someone has published contradicting results to your published paper, and you've been asked to provide your data and methods. Could you?

* Research Storage – Vault
* Research Data Repository
* Documentation
* Versions of software
* Keep raw data separate (Research Storage – Vault)


Q4) If a research partner organization believes your "sensitive" data has been made available to others (ie a data breach). Could you show that steps were taken to avoid this or show that it couldn't happen?

* Research space – tracing who you have shared a file
* Computer encryption (General good computer safety)
* General good computer safety – unique passwords and use Multi factor Auth when possible
* Separating identified variables

## Audience

This workshop is aimed at researchers and academics in the field of biostatistics.

## Prerequisites

To successfully coplete this workshop you will need: 

- A modern browser
- An installation of [OpenRefine](https://openrefine.org)

## Assumed knowledge

It is assumed that you have the following level of understanding:

- Ability to install software on your own device
- Foundational data terminology such as tabular data, binary data, csv, tables, fields etc.

{% endcapture %}

{% include card.html header="About this site" text=aboutworkshop %}

## Creating Content

Content follows these conventions:

- All documentation files are written in Markdown. For clearer version control, editing, accessibility, and reusability please:
    - write one sentence per line.
    - always provide a blank line between elements (i.e. headers, paragraphs, lists, code blocks are always followed by a blank line).
    - headers should follow logical order on page without skipping levels. The page template includes an "h1" using the `title` set in the front matter--thus additional headers on the page should start at "h2", i.e. `##` in markdown.
    - code and variables should be given `code` class using backticks, filenames should be given in "quotes".
- Markdown files are located in the "content" folder and can be further organized into folders inside if desired.

## Create Navigation 

The sidebar navigation menu is controlled by front matter added to each page. 
There are two ways a page can appear in the nav: individual or in a section drop down.

The nav follows these rules:

- **Individual listing:** To list a page in the nav individually, add `nav_order` to the front matter of a content page. e.g. `nav_order: 1`. Do *not* include `section_id` or `section` in the front matter.
- **Section dropdown:** To create a "section" drop down, on the first content page of the section, add `nav_order` and `section_id` to the front matter. The value of `section_id` will be displayed as the label for the section drop down. e.g. `section_id: Workshop Prep`. The page's title will be listed as the first item in the section dropdown.
- **Section pages:** To add additional pages to the section dropdown, add `section` and `nav_order` to the front matter of a markdown file. The value of `section` must match a `section_id` set up on another markdown file. The page's title will appear under the corresponding section dropdown. The pages in the section will sort according to `nav_order` within the section--however, the page that sets up the section (with `section_id`) will always be listed first. 

Note: 

- The nav listings (individual pages and sections) will be sorted by the value of `nav_order`.
- If a markdown stub does not have `nav_order` *or* `section` in the front matter, the page will **not** appear anywhere in the navigation. Occasionally you might want to create pages that aren't linked in the nav, just be sure to link to them from somewhere else!
- The values of `section_id` / `section` should be unique. If you create multiple sections with the same name, the nav won't work as expected!

### Example Front Matter

Individual listing:

```
---
nav_order: 1
title: Introduction
---
```

Section lead:

```
---
section_id: Getting Started
nav_order: 3
title: Install Git and GitHub Desktop
---
```

Section content:

```
---
section: Getting Started
nav_order: 2
title: Configure Git
---
```

## License

Learn-Static documentation and general web content is licensed [Creative Commons Attribution-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-sa/4.0/).
Learn-Static code is licensed [MIT](https://github.com/learn-static/lesson-template/blob/main/LICENSE). 
This license does not include external dependencies included in the "assets/lib" directory, which are covered by their individual licenses.
