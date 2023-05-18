# Overview

This github repository serves as a template for a short-form workshop, lesson, or course to be shared in the form of a pkgdown website with slides rendered by xaringan.

# Instructions

1. Click the green "Use this template" button from https://github.com/uf-repro/lesson-template.

2. Modify `README.Rmd` with basic metadata for the package and lesson.
  - When knit, this will produce an updated `README.md` file and also update the package's `DESCRIPTION` file.
  - Note: fields such as `prerequisites`, `priorCourse`, and `learningOutcomes` are read from the `DESCRIPTION` file for intro content in the slides.
  - *Be sure to update the badges to point to the correct repo location!*

3. Update the slides at `slides/slides.Rmd`.
  - You may want to read up on the instructions for [xaringan](https://bookdown.org/yihui/rmarkdown/xaringan.html) - the basic platform,
  - [kunoichi](https://emitanaka.org/ninja-theme/themes/kunoichi/kunoichi-theme-example.html) - a theme with some fancier CSS styling, and
  - [xaringanthemer](https://pkg.garrickadenbuie.com/xaringanthemer/) - an extension with more font/color customizability.

4. Update the list of resources at `resources.md`

5. Push changes for the new repo.

6. Modify the `About` box on the repo page to include the GitHub Pages URL as the Website.

== OPTIONAL ==

7. Configure Zenodo for the new repo.

8. Release a version on GitHub.

9. Update the DOI badge.


# Tech Stack

This repository is structured as an R package. For details on creating R packages, see the [R Packages book](https://r-pkgs.org/).

The website is built using [`pkgdown`](https://pkgdown.r-lib.org/), which depends on the repository being a functional R package. Basic configuration of the menu is done via the `_pkgdown.yml` file.

Deployment of the website is handled on GitHub and automated via GitHub Actions. The script `/.github/workflows/pkgdown.yaml` is a modified version from the [r-lib/actions](https://github.com/r-lib/actions/blob/v2-branch/examples/pkgdown.yaml) repository:
* [RMDconverter](https://github.com/ha0ye/RMDconverter) processes the slide content into a single continuous markdown file to show as a notes page.
* A separate call is made to render the slides, so that the resulting HTML slides do NOT have the pkgdown formatting.

The static content for the site is then stored on the `gh-pages` branch, and viewable at the standard web location: {github account}.github.io/{repo name}.




