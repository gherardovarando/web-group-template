## web-group-theme for Jekyll based website

This simple Jekyll theme can be used to build research groups web pages using the 
standard github pages Jekyll compiler.  
It uses [`bibtex_js`](https://github.com/pcooksey/bibtex-js) to display publications 
and defines a set of collections for news, seminars and people with related includes 
to easily add content into your website.

See the [live demo](https://gherardovarando.github.io/web-group-theme/).


### Quick start

1. Add `web-group-theme` as a [remote theme](https://github.blog/2017-11-29-use-any-theme-with-github-pages/) in the `_config` file of your Jekyll's site 
 
```
remote_theme: gherardovarando/web-group-theme
```

2. Add the collections `people`, `talks` and `news` in the `_config.yml` file and set `future` to `true` to show upcoming seminars/talks.  

```
future: true
collections:
  talks:
    output: true
  news:
    output: true
  people:
    output: true
```

### Usage


#### Home 

Use `layout: front` for the landing page (`index.md` or `index.html`). 

#### Publications

Define the path to the used `bib` files in the `_config.yml` file as follow:

```
bibfiles: 
      - "path to a bib file"
      - "path to another bib file"
```

Use `layout: publications` for the publication page to automatically display 
the entries in the bib files.  

#### People

Place one file for each member of your group in the `_people` folder with the following content:
```
---
name: Full name of researcher
img: path to image
role: role id as defined in _config.yml
layout: default
---


First paragraph (excerpt) is displayed as a short bio next to the image.


This is not displayed in the people page but it is rendered if the page is published. 
```

You can define roles for your group in the `_config.yml` as follows
```
roles: 
    - id: full
      title: Full professor
    - id: associate
      title: Associate professor  
    - id: postdoc
      title: PostDoc
    - id: phd
      title: Phd student 
```

#### News

Place news post in the `_news` directory. News will be displayed in a page with 
`layout: news`. 

#### Talks/Seminars 

Place talks and seminars as single pages in the `_talks` folder, each page should should have 
the following structure
```
---
layout: default
title: Seminar title
speaker: speaker name
affiliation: affiliation
date: date in ISO format
location: location info
link: link for location or recordings
---

Abstract content goes here 
```
