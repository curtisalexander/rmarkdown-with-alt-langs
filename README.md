# rmarkdown-with-alt-langs
Example of an html document with syntax highlighting not supported natively by R Markdown (SAS & Crystal).

For a full description of how this is accomplished and stitched together, refer to my [blog post](https://www.calex.org/blog/r-markdown-syntax-highlighting/).

<br/><br/>

### Github Pages + Post Commit Hook
For future reference, this makes use of a super simple [post-commit hook](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) for git that copies the html document into the `docs` folder so that it can be viewed on Github Pages &mdash; https://curtisalexander.github.io/rmarkdown-with-alt-langs/.

Create the file `.git/hooks/post-commit` with the following.

```sh
#!/bin/sh

cp rmarkdown-with-alt-langs.html docs/index.html
git add docs/index.html
git commit -m "$(git log -1 master --pretty=%B)"
```

