# Lysander: Finding political journalists on Twitter
[![DOI](https://zenodo.org/badge/87090173.svg)](https://zenodo.org/badge/latestdoi/87090173)
[![Research Software Directory](https://img.shields.io/badge/rsd-Research%20Software%20Directory-00a3e3.svg)](https://research-software.nl/software/finding-journalists)

This directory contains software developed in the pilot of
the project [Automated Analysis of Online Behaviour on
Social
Media](https://www.esciencecenter.nl/project/automated-analysis-of-online-behaviour-on-social-media),
a cooperation of the University of Groningen and the
Netherlands eScience Center. The main project software
repository is called [machine
learning](https://github.com/online-behaviour/machine-learning).

The goal of the project is to analyze tweets of politicians
and political journalists. Names of relevant politicians can
be collected from documents like parliament member lists
and ballots but it is much harder to find the names of
relevant journalists. The software in this directory aims to
find such journalists by examining the follower links
between politicians and other users on Twitter.

## Usage

Run like:

```
python getFollowers.py markrutte sybrandbuma apechtold > getFollowers.out 
```

to collect the people that are followed by the users in
your seed list. The script needs your Twitter account data
to be stored in a file definitions.py in the format:

```
# twitter.com authentication keys
token = "???"
token_secret = "???"
consumer_key = "???"
consumer_secret = "???"
```

Replace the strings "???" with the key information from
https://apps.twitter.com , see
https://www.slickremix.com/docs/how-to-get-api-keys-and-tokens-for-twitter/
for instructions

In order to find more relevant users, you can run this command 
after getFollowers.py is finished:

```
python makevec.py markrutte sybrandbuma apechtold < getFollowers.out > makevec.out 2> makevec.err
```

It generates a selection of relevant users (makevec.err) and 
a vector representations for these users (makevec.out)

Input data files for Dutch politicians can be requested
from Erik Tjong Kim Sang e.tjong.kim.sang(at)esciencenter.nl

# Information added by the Python template

## Badges

(Customize these badges with your own links, and check https://shields.io/ or https://badgen.net/ to see which other badges are available.)

| fair-software.eu recommendations | |
| :-- | :--  |
| (1/5) code repository              | [![github repo badge](https://img.shields.io/badge/github-repo-000.svg?logo=github&labelColor=gray&color=blue)](https://github.com/online-behaviour/find-journalists) |
| (2/5) license                      | [![github license badge](https://img.shields.io/github/license/online-behaviour/find-journalists)](https://github.com/online-behaviour/find-journalists) |
| (3/5) community registry           | [![RSD](https://img.shields.io/badge/rsd-find-journalists-00a3e3.svg)](https://www.research-software.nl/software/find-journalists) [![workflow pypi badge](https://img.shields.io/pypi/v/find-journalists.svg?colorB=blue)](https://pypi.python.org/project/find-journalists/) |
| (4/5) citation                     | [![DOI](https://zenodo.org/badge/DOI/<replace-with-created-DOI>.svg)](https://doi.org/<replace-with-created-DOI>) |
| (5/5) checklist                    | [![workflow cii badge](https://bestpractices.coreinfrastructure.org/projects/<replace-with-created-project-identifier>/badge)](https://bestpractices.coreinfrastructure.org/projects/<replace-with-created-project-identifier>) |
| howfairis                          | [![fair-software badge](https://img.shields.io/badge/fair--software.eu-%E2%97%8F%20%20%E2%97%8F%20%20%E2%97%8F%20%20%E2%97%8F%20%20%E2%97%8B-yellow)](https://fair-software.eu) |
| **Other best practices**           | &nbsp; |
| Static analysis                    | [![workflow scq badge](https://sonarcloud.io/api/project_badges/measure?project=online-behaviour_find-journalists&metric=alert_status)](https://sonarcloud.io/dashboard?id=online-behaviour_find-journalists) |
| Coverage                           | [![workflow scc badge](https://sonarcloud.io/api/project_badges/measure?project=online-behaviour_find-journalists&metric=coverage)](https://sonarcloud.io/dashboard?id=online-behaviour_find-journalists) |
| Documentation                      | [![Documentation Status](https://readthedocs.org/projects/find-journalists/badge/?version=latest)](https://find-journalists.readthedocs.io/en/latest/?badge=latest) |
| **GitHub Actions**                 | &nbsp; |
| Build                              | [![build](https://github.com/online-behaviour/find-journalists/actions/workflows/build.yml/badge.svg)](https://github.com/online-behaviour/find-journalists/actions/workflows/build.yml) |
|  Metadata consistency              | [![cffconvert](https://github.com/online-behaviour/find-journalists/actions/workflows/cffconvert.yml/badge.svg)](https://github.com/online-behaviour/find-journalists/actions/workflows/cffconvert.yml) |
| Lint                               | [![lint](https://github.com/online-behaviour/find-journalists/actions/workflows/lint.yml/badge.svg)](https://github.com/online-behaviour/find-journalists/actions/workflows/lint.yml) |
| SonarCloud                         | [![sonarcloud](https://github.com/online-behaviour/find-journalists/actions/workflows/sonarcloud.yml/badge.svg)](https://github.com/online-behaviour/find-journalists/actions/workflows/sonarcloud.yml) |
| MarkDown link checker              | [![markdown-link-check](https://github.com/online-behaviour/find-journalists/actions/workflows/markdown-link-check.yml/badge.svg)](https://github.com/online-behaviour/find-journalists/actions/workflows/markdown-link-check.yml) |

## How to use find_journalists



The project setup is documented in [project_setup.md](project_setup.md). Feel free to remove this document (and/or the link to this document) if you don't need it.

## Installation

To install find_journalists from GitHub repository, do:

```console
git clone https://github.com/online-behaviour/find-journalists.git
cd find-journalists
python3 -m pip install .
```

## Documentation

Include a link to your project's full documentation here.

## Contributing

If you want to contribute to the development of find-journalists,
have a look at the [contribution guidelines](CONTRIBUTING.md).

## Credits

This package was created with [Cookiecutter](https://github.com/audreyr/cookiecutter) and the [NLeSC/python-template](https://github.com/NLeSC/python-template).
