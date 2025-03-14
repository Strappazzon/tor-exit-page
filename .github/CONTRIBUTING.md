# Contribution Guidelines

By participating, you agree to abide by the [Code of Conduct](https://github.com/Strappazzon/.github/blob/-/CODE_OF_CONDUCT.md).  
When submitting changes to this repository, you agree that the content you contribute may be provided under the terms of the [GPLv3 License](https://opensource.org/license/gpl-3-0).

## I Have a Question

Before you ask a question, search for existing [Discussions](https://github.com/Strappazzon/tor-exit-page/discussions/categories/questions) that might help you.  
In case you have found a suitable discussion and still need clarification, you can write your question in that discussion. It is also advisable to search the internet for answers first.

If you then still need to ask a question and need clarification you can [create a discussion](https://github.com/Strappazzon/tor-exit-page/discussions/new?category=questions).

## Issue Reporting and Feature Requests

> [!CAUTION]
> If you found a security issue, **DO NOT** report it in the issue tracker or elsewhere in public.  
> See: [Security Policy](https://github.com/Strappazzon/.github/blob/-/SECURITY.md).

- Take a look at the [issues](https://github.com/Strappazzon/tor-exit-page/issues) first to make sure your issue/feature hasn't been reported/requested before.  
  If so, engage in the already existing discussion.
- Check whether your issue/feature is already fixed/implemented.
- Issues in languages other than English will be closed and ignored.
- If you are familiar with the languages used in this repo, you are always welcome to fix/implement an issue/feature yourself.
- Add one issue at a time. Do not put multiple issues into one thread.
- When reporting a bug please describe the steps which reproduce the problem.
- All issues must be properly formatted with Markdown.  
  If you don't know what that is, read [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) before submitting an issue.

### DO NOT post "+1" comments

If you don't have any additional info/context to add but would like to indicate that you're affected by the issue, upvote the original issue.  
See: [Add Reactions](https://github.blog/news-insights/product-news/add-reactions-to-pull-requests-issues-and-comments/)

## Getting Started

Before you can start contributing, you'll need to set up your environment first.

### Dependencies

This Tor Exit Router page is built with [Jekyll](https://jekyllrb.com/) so you will need [Ruby](https://www.ruby-lang.org) installed.  
I recommend you install it using [rbenv](https://github.com/rbenv/rbenv), [asdf](https://github.com/asdf-vm/asdf), [frum](https://github.com/TaKO8Ki/frum) or other packaging system, before attempting to install the dependencies.

Clone the repo and run `bundle install` to install the required dependencies.

```sh
git clone https://github.com/Strappazzon/tor-exit-page.git
cd tor-exit-page/
bundle install
```

### Local Previews

To view your changes locally use the following command:

```sh
bundle exec jekyll serve --force_polling --livereload
```

Then navigate to <http://localhost:4000> in your web browser.

Press <kbd>CTRL</kbd>+<kbd>C</kbd> to stop the web server.

## Code style and Conventions

### Liquid

The notice page is written in the Jekyll [Liquid](https://shopify.github.io/liquid/basics/variations/#jekyll) templating language.

#### Syntax

- Indent using tabs.
- Use "double quotation marks" except when a filter or expression is inside an HTML attribute.

<!-- markdownlint-disable MD010 -->

```liquid
{% comment %} bad {% endcomment %}
<head>
	<meta property="og:url" content='{{ site.url }}{{ page.url | replace: "index.html",""}}'>
</head>

{% comment %} good {% endcomment %}
<head>
	<meta property="og:url" content="{{ site.url }}{{ page.url | replace: 'index.html',''}}">
</head>
```

<!-- markdownlint-enable MD010 -->

#### Comments

Indent multiline comments.

<!-- markdownlint-disable MD010 -->

```liquid
{% comment %}
bad
  this comment block is not indented correctly.
{% endcomment %}

{% comment %}
	good
	this comment block is indented correctly.
{% endcomment %}

{% comment %} No need to indent brief comments. {% endcomment %}
```

<!-- markdownlint-enable MD010 -->

#### Filters

- Do not wrap filters.
- Put a space before the filter value.

<!-- markdownlint-disable MD010 -->

```liquid
{% comment %} Bad {% endcomment %}
{{ object.prop
  | downcase
  | prepend:"value"
}}

{% comment %} Good {% endcomment %}
{{ object.prop | downcase | prepend: "value" }}
```

<!-- markdownlint-enable MD010 -->

### Markdown

Documentation is written in [GitHub Flavored Markdown](https://docs.github.com/en/get-started/writing-on-github).

[markdownlint](https://github.com/DavidAnson/markdownlint) is used to enforce style rules for Markdown files.

## Submitting Changes

- Make changes on a separate branch, not on the master branch, then send your changes as a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).
- When submitting changes, you confirm that your code is licensed under the terms of the [MIT License](https://opensource.org/licenses/MIT).
- Please test your code before you submit changes. Untested code will **not** be merged!
- Make sure your Pull Request is up-to-date with the rest of the codebase.

## Git Commit Messages

- Use the present tense ("Add feature" not "Added feature").
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...").
- Wrap all lines at 70 columns (except for long URLs).
- Writing a detailed description is not mandatory.
- Reference issues and Pull Requests after the description, if any.  
  Use `Closes:` or `Fixes:`.

### Sample Complete Commit Message

```plaintext
explain the commit in one line

The body of the commit message should explain things in more detail.
Please word-wrap to keep columns to 70 characters or less.

Fixes: https://github.com/Strappazzon/tor-exit-page/issues/513
```

## Branching

`dev` and `test` is where all changes that are not ready for production yet go.

From dev and test, there are multiple branches related to what is being developed inside each branch.

A branch name must be short and descriptive, all lowercase. For branches with multiple words use hyphens.

## Repository Structure

This is a brief description on how the repository files and folders are structured and what each one contains.  
It only contains the most relevant files and folders as some of them are self-explanatory.

```sh
.
├── _sass           # SCSS Stylesheets
├── .github
│   └── labeler.yml # "actions/labeler" configuration
├── _config.yml     # Jekyll configuration
└── SUPPORT.md      # Support resources
```
