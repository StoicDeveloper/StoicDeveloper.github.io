# Static Page Resume README

## Purpose

The purpose of this document is to provide a guide for creating a resume with markdown, hosted as a static page, and to relate this process to general principles of technical writing.

## Prerequisites

- Have a markdown-formatted resume
- Have a GitHub account
- Have a text editor (I used Vim)

## Instructions

1. Create github pages repository
	- make sure that the repository name is <accountName>.github.io
2. Install and Configure Jekyll
	- follow the instructions found in the [Jekyll documentation.](https://jekyllrb.com/docs/installation/)
	- using your preferred command line shell, navigate to the directory you want to create the project in
	- create the Jekyll project with `jekyll new <projectName>`
	- enter the project directory: `cd <projectName>`
	- clone the github repository gor the project `git clone <repositoryURL`
	- add the jekyll files to the repository `git add .`
3. Add resume to repository
	- copy your markdown-formatted resume to the project directory
	- name it index.md
	- add it to the project `git add index.md`
4. Publish the static site
	- build the project `build exec jekyll build
	- alternatively, host it locally to examine static page output by executing `bundle exec jekyll serve` and accessing `http://localhost:4000` in a web browser
	- commit changes `git commit -a -m "<commit message>"`
	- publish the static page `git push`
		- it may be necessary to log in to github locally to push to the repo
5. (optional) Select and Install a different theme
	- Themes can be found in the [ruby gems site](https://rubygems.org/search?utf8=%E2%9C%93&query=jekyll-theme)
	- Install by following the instructions in the [Jekyll documentation](https://jekyllrb.com/docs/themes/#installing-a-theme)
	- publish the changes as in 4

My 

## Acknowledgments

Author: Xian Mardiros
Thanks to Chris Rogers and Brett Downey for discussing how this document can be improved.

## FAQs

1. Why is Markdown better than a word processor?

There are several reasons why Markdown files are more suited to certain uses than word processors. Work processor documents are resistant to version control, since the lines displayed in the word processor program do not directly correspond to the lines in the source file, which is XML. According to Modern Technical Writing, word processors are not good at exporting to HTML, and so is not useful for producing documents that will be part of a webpage. There are also a great variety of options for open-source text editors, whereas Microsoft Word requires a license. It also has open-source alternatives, but they're often buggy, unsupported, or lack certain important features.

2. Why won't my Jekyll static site build?

I had this same problem. It is possible that when installing Jekyll your Gemfile.lock file became configured to require contradictory dependencies. To fix this, run remove the problematic file with `rm Gemfile.lock` and then run `bundle install`. This should generate a correct Gemfile.lock, at which point you can try to build the project again.
