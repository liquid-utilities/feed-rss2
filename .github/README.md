# Liquid Feed RSS2 Development
[heading__title]:
  #liquid-feed-rss2-development
  "&#x2B06; Top of this page"


[`feed-rss2.html`][feed_rss2__master__source_code], a Liquid _plugin_ for embedding Feed RSS2s within GitHub Pages.


> See the [`master` branch][feed_rss2__master] for _Quick Start_ on installing and utilizing _`feed-rss2.html`_. This branch contains development, testing, and source files of the [live demo][demo__feed_rss2] for this project. Please review _`Contributing`_ guidelines for [Community][feed_rss2__community] prior to issuing first Pull Request.


## [![Byte size of feed-rss2.html][badge__master__feed_rss2__source_code]][feed_rss2__master__source_code] [![Open Issues][badge__issues__feed_rss2]][issues__feed_rss2] [![Open Pull Requests][badge__pull_requests__feed_rss2]][pull_requests__feed_rss2] [![Latest commits][badge__commits__feed_rss2__gh_pages]][commits__feed_rss2__gh_pages] [![feed_rss2 Demo][badge__demo__feed_rss2]][demo__feed_rss2]



------


#### Table of Contents


- [&#x2B06; Top of ReadMe File][heading__title]

- [:bridge_at_night: Development Tips][heading__development_tips]

  - [:trident: Forking][heading__forking]
  - [:herb: First Clone][heading__first_clone]
  - [:100: Local Testing][heading__local_testing]
  - [:arrows_counterclockwise: Merge Updates][heading__merge_updates]
  - [:arrows_clockwise: Merge Improvements][heading__merge_improvements]

- [&#x1F5D2; Notes][heading__notes]

- [:copyright: License][heading__license]


------


## Development Tips
[heading__development_tips]:
  #development-tips
  "&#x1F309; Quick reference for those ready to improve this project"


### Forking
[heading__forking]:
  #forking
  "&#x1F531;"


[Fork][fork__feed_rss2] this project to an Account or Organization with Push permissions. Doing so allows for _extended version locking_ as well as tracking any changes ready for consideration via Pull Requests.


### First Clone
[heading__first_clone]:
  #first-clone
  "&#x1F33F; Steps to ensure git knows about forked URLs in development branch and any tracked submodules"


The setup is a _bit_ more extensive because of how this project utilities submodules, however. following the next steps ensure _`Git`_ knows about forked URLs in development branch and any tracked submodules too.


**Shared Variables**


```Bash
_account_name="YourAccountsName"
_origin_url_git="git@github.com:liquid-utilities/feed-rss2.git"
_fork_url_git="git@github.com:${_account_name}/feed-rss2.git"
_fork_url_https="https://github.com/${_account_name}/feed-rss2.git"
```


**`gh-pages` branch initial setup**


1. Clone your fork via _`_fork_url_git`_ value, then setup alternate _`remote`_ pointing to the value of _`_origin_url_git`_ for future updates

2. Enter the root directory for this repository, `fetch` and `checkout` the `gh-pages` branch

3. Point submodule URL to _`_fork_url_https`_ value, then _`sync`_ and _`update`_ changes


```Bash
git clone --origin forked "${_fork_url_git}"
git remote add origin "${_origin_url_git}"


cd feed-rss2
git fetch forked gh-pages:gh-pages
git checkout gh-pages


git config --file=.gitmodules submodule.feed-rss2.url "${_fork_url_https}"
git submodule sync
git submodule update --init --recursive --remote
```


**_`ls -1a _layouts/modules/feed-rss2`_** example output


```Bash
#> .
#> ..
#> feed-rss2.html
#> .git
#> .github
#> LICENSE
```


**`master` branch as submodule initial setup**


1. Enter root directory of submodule, and reattach the _`HEAD`_ by explicitly checking out the _`master`_ branch

2. Setup submodule `remote` with _`_fork_url_https`_ value and fetch your fork one more time

3. Configure _`forked`_ _`remote`_ to be the default for _`git`_ interactions


```Bash
cd _layouts/modules/feed-rss2
git checkout master


git remote add forked "${_fork_url_git}"
git fetch forked


git branch --set-upstream-to=forked/master
```


**_`git status`_** example output


```Bash
#> On branch gh-pages
#> Your branch is up-to-date with 'forked/gh-pages'.
#> nothing to commit, working directory clean
```


**_`git submodule foreach git status`_** example output


```Bash
#> Entering '_layouts/modules/feed-rss2'
#> On branch master
#> Your branch is up-to-date with 'forked/master'.
#> nothing to commit, working directory clean
```


### Local Testing
[heading__local_testing]:
  #local-testing
  "&#x1F4AF; After initial setup, please test prior to public commits"


Local testing requires Jekyll via Bundler, for now see their documentation for how to install dependencies. After which issuing the following _should_ build site files...


```Bash
_srv_path="${HOME}/www"
_config_files="_config.yml,_config_baseurl.yml"

bundle exec jekyll build --destination "${_srv_path}" --config "${_config_files}"
```


### Merge Updates
[heading__merge_updates]:
  #merge-updates
  "&#x1F504; Update your fork with edits from this repository"


1. Pull submodule updates from _`origin`_ remote

2. Pull development updates from _`origin`_ remote


```Bash
git submodule foreach git pull origin master

git pull origin gh-pages
```


> Hint, `vimdiff` is an excellent command-line tool for resolving most merge conflicts.


```Bash
git submodule foreach git push forked master

git push forked gh-pages
```


### Merge Improvements
[heading__merge_improvements]:
  #merge-improvements
  "&#x1F503; Notify maintainers of this repository that your edits are ready for consideration"


```Bash
git submodule foreach git push forked master

git push forked gh-pages
```


**:tada: Pull Requests :tada:** should be opened via Web UI on GitHub to notify maintainers of this repository that your fork is ready for consideration.


___


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional resources and things to keep in mind when developing"


Once the _`gh-pages`_ branch has been checked out, please direct edits to the _`master`_ branch via the submodule path. And to avoid build errors be sure to commit and push updates for the _`master`_ branch **prior** to any commits required to update the _`gh-pages`_ branch references.


If developing on a local branch please merge back to the relevant _mainline_ branch before publicly pushing.


Periodically check the [Community][feed_rss2__community] page for this repository; specifically relevant updates can be found under _`Code of Conduct`_ guidelines and _`Pull Request`_ templates sections.


___


## License
[heading__license]:
  #license
  "&#x00A9; Legal bits of Open Source software"


```
Liquid Feed RSS2 submodule development documentation for Git tracked web sites
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



[feed_rss2__master]:
  https://github.com/liquid-utilities/feed-rss2/
  ""


[fork__feed_rss2]:
  https://github.com/liquid-utilities/feed-rss2/fork
  ""


[badge__commits__feed_rss2__gh_pages]:
  https://img.shields.io/github/last-commit/liquid-utilities/feed-rss2/gh-pages.svg

[commits__feed_rss2__gh_pages]:
  https://github.com/liquid-utilities/feed-rss2/commits/gh-pages
  "&#x1F4DD; History of changes on this branch"


[feed_rss2__community]:
  https://github.com/liquid-utilities/feed-rss2/community
  "&#x1F331; Dedicated to functioning code"



[badge__demo__feed_rss2]:
  https://img.shields.io/website/https/liquid-utilities.github.io/feed-rss2/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[demo__feed_rss2]:
  https://liquid-utilities.github.io/feed-rss2/index.html
  "&#x1F52C; Exposes examples of how to utilize code from this repository"


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
  "&#x2328; Project source code"
