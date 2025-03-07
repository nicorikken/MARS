# YML configuration file

This README serves as a guide for the dynamic yml config file located in this directory. It defines the repository structure for various Working Groups that are to be included in the metrics release report. The working groups would be cloned and parsed for relative links according to the structure defined here. It serves as the only input for the automation process.

## File Structure

This file follows a simple yet strict structure, make sure you follow it to avoid unnecessary errors.

* The following is a template for the same, with explanation:

```
wg-name:
  include-wg: boolean
  wg-fullname: WG-name
  github-link: git-link
  github-branch: git-branch
  focus-areas:
    focus-area1:
    - metric1-name.md
    - metric2-name.md
    focus-area2:
    - metric1-name.md
    - metric2-name.md
```

**Explanation:**
* `wg-name`: WG name that is same as the repository name for the WG
* `include-wg`: boolean flag that defines if the WG should be included in the report (mainly for debugging purposes)
* `wg-fullname`: complete name of WG that you want in the report headings
* `github-link`: github link for the WG repo (for cloning)
* `github-branch`: git branch for the WG repo (for cloning)
* `focus-area1`: focus-area name should be same as the focus-area dir name in the WG
* `metric1-name.md`: the name of metric markdown file as in the repo (should include .md extension as well)

Note: Empty focus-areas (focus-areas with no metrics) will work as well.

* A sample structure for [wg-common](https://github.com/chaoss/wg-common) would look like this:

```
# WG Common

wg-common:
  include-wg: True
  wg-fullname: Common Metrics WG
  github-link: https://github.com/chaoss/wg-common
  github-branch: master
  focus-areas:
    what:
    - technical-fork.md
    - types-of-contributions.md
    when:
    - activity-dates-and-times.md
    - burstiness.md
    - review-cycle-duration-within-a-change-request.md
    - time-to-close.md
    - time-to-first-response.md
    where:
    who:
    - contributor-location.md
    - contributors.md
    - organizational-diversity.md
```

## Usage

Now that you are familiar with the structure of the file, it is important to note that this file also determines in which order the working groups, focus-areas and metrics would be displayed in the release report. The order is from top to bottom, and is applicable for WG, focus-areas and their respective metrics.

This file is expected to be altered during each metrics release process.

A series of steps to be performed during the release process:
* Before making any changes, make sure a copy of the previous release PDF and this yml file for THAT release exist in the website repo here (add link)
* Update this file - perform the following operations, if applicable:
    * Add new metrics to their respective focus-areas (mind the order)
    * Remove outdated/retired metrics
    * Reorder the WG, focus-areas or metrics as per convenience
* Save changes to the new finalized file
* Refer to main [README](../README.md), to continue with the release process


