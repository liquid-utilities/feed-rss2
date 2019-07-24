# Liquid Feed RSS2
[heading__title]:
  #liquid-feed-rss2
  "&#x2B06; Top of ReadMe File"


Liquid layout that builds RSS2 feeds from Jekyll collections via FrontMatter configurations


## [![Byte size of feed-rss2.html][badge__master__feed_rss2__source_code]][feed_rss2__master__source_code] [![Open Issues][badge__issues__feed_rss2]][issues__feed_rss2] [![Open Pull Requests][badge__pull_requests__feed_rss2]][pull_requests__feed_rss2] [![Latest commits][badge__commits__feed_rss2__master]][commits__feed_rss2__master] [![Feed RSS2 Demos][badge__demo__feed_rss2]][demo__feed_rss2]



------


#### Table of Contents


- [:arrow_up: Top of ReadMe File][heading__title]

- [:zap: Quick Start][heading__quick_start]

  - [:memo: Edit Your ReadMe File][heading__your_readme_file]
  - [&#x1F578; Utilize Feed RSS2][heading__utilize]
  - [:floppy_disk: Commit and Push][heading__commit_and_push]

- [:card_index: Attribution][heading__attribution]

- [&#x2696; License][heading__license]


------



## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


**Bash Variables**


```Bash
_module_name='feed-rss2'
_module_https_url="https://github.com/liquid-utilities/${_module_name}.git"
_module_relative_path="_layouts/modules/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "_layouts/modules"

git submodule add\
 -b master --name "${_module_name}"\
 "${_module_https_url}" "${_module_relative_path}"
```


### Your ReadMe File
[heading__your_readme_file]:
  #your-readme-file
  "&#x1F578; Suggested additions for your ReadMe.md file so everyone has a good time with submodules"


Suggested additions for your _`ReadMe.md`_ file so everyone has a good time with submodules


```MarkDown
Clone with the following to avoid incomplete downloads


    git clone --recurse-submodules <url-for-your-project>


Update/upgrade submodules via


    git submodule update --init --merge --recursive --remote
```


### Utilize Feed RSS2
[heading__utilize]:
  #utilize-feed-rss2
  "&#x1F578; How to make use of this submodule within another project"


Assign `site.url`, either via command line Jekyll `build`/`serve` command line option or with the following `_config.yml` configuration...


```
url: "http://example.com"
```


Each collection `page` should have FrontMatter definitions similar to...


```YAML
---
title: Title of Page
date: 2019-04-17 11:12:11 -0300
#date_updated:  # Optional and formatted like `date` above
description: A description of page content
#excerpt: Or a snipit about this page
## Following is optional and in this example case would allow
##  for embeding CSV data within `content` tags, defaults to `html`
#content_type: 'text/delimited'
time_to_live: 1800  # Number of seconds till update is recommended
---
```


> Note, `excerpt` requires `site.show_excerpts` to be _non-`false`_ and __not__ setting a `description` for those pages using `excerpt`s


This layout may utilize the GitHub MetaData plugin, please enable within the following configuration files to avoid build errors popping because of code from this repository...


**`_config.yml`**


```YAML
plugins:
  - jekyll-github-metadata
```


**`Gemfile`**


```Gemfile
# gem "jekyll", "~> 3.8.5"
gem "github-pages", group: :jekyll_plugins

gem "jekyll-github-metadata"
```


### Commit and Push
[heading__commit_and_push]:
  #commit-and-push
  "&#x1F4BE; It may be just this easy..."


```Bash
git add .gitmodules
git add _layouts/feed-rss2


## Add any changed files too


git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/feed-rss2#1` submodule



**Additions**


- `.gitmodules`, tracks submodules AKA Git within Git _fanciness_

- `README.md`, updates installation and updating guidance

- `_layouts/feed-rss2`, builds RSS2 feeds via FrontMatter configurations
EOF


git push origin gh-pages
```


**:tada: Excellent :tada:** your site is now ready to begin unitizing code from this repository!


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


Resources that where helpful in building this project so far


- https://stackoverflow.com/a/42057699/2632107
- https://gist.github.com/roachhd/f664d2cae2da899be3f6
- https://www.w3schools.com/xml/xml_rss.asp


___


## License
[heading__license]:
  #license
  "&#x2696; Legal bits of Open Source software"


Legal bits of Open Source software


```
Feed RSS2 ReadMe documenting how things like this could be utilized
Copyright (C) 2019  S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation; version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```



[badge__commits__feed_rss2__master]:
  https://img.shields.io/github/last-commit/liquid-utilities/feed-rss2/master.svg

[commits__feed_rss2__master]:
  https://github.com/liquid-utilities/feed-rss2/commits/master
  "&#x1F4DD; History of changes on this branch"


[feed_rss2__community]:
  https://github.com/liquid-utilities/feed-rss2/community
  "&#x1F331; Dedicated to functioning code"


[feed_rss2__gh_pages]:
  https://github.com/liquid-utilities/feed-rss2/tree/gh-pages
  "Source code examples hosted thanks to GitHub Pages!"



[badge__demo__feed_rss2]:
  https://img.shields.io/website/https/liquid-utilities.github.io/feed-rss2/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[demo__feed_rss2]:
  https://liquid-utilities.github.io/feed-rss2/index.html
  "&#x1F52C; Check the example collection tests"


[badge__issues__feed_rss2]:
  https://img.shields.io/github/issues/liquid-utilities/feed-rss2.svg

[issues__feed_rss2]:
  https://github.com/liquid-utilities/feed-rss2/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."


[badge__pull_requests__feed_rss2]:
  https://img.shields.io/github/issues-pr/liquid-utilities/feed-rss2.svg

[pull_requests__feed_rss2]:
  https://github.com/liquid-utilities/feed-rss2/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"


[badge__master__feed_rss2__source_code]:
  https://img.shields.io/github/size/liquid-utilities/feed-rss2/feed-rss2.html.svg?label=feed-rss2.html

[feed_rss2__master__source_code]:
  https://github.com/liquid-utilities/feed-rss2/blob/master/feed-rss2.html
  "&#x2328; Project source, one Liquid file of actionable code!"
