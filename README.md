# Benicia Artists

Showcasing the lives and works of Benicia artists.

## Developing the site locally

Begin by installing [NodeJS](#) and [Ruby](#).

Then, after cloning the repo, install Jekyll and any necessary dependencies using:

```bash
npm install
bundle install
```

To run the site locally, from the project folder, run:

```bash
bundle exec jekyll serve
```

If all goes well, visit the site at `http://localhost:4000`.

## Updating the site

When updates are made to the source data the site needs to be regenerated.

```bash
git checkout master
git pull origin master
git checkout -b regen-$date # example: regen-120219
ruby regenerate-site
```

This will download the latest version of the Artists CSV from Google Docs and
update the Jekyll `_data` and `_pages/artists` sections.

Run the site locally to make sure all is well (optional). Push the branch to
Github:

```bash
git add .
git commit -m "Regenerated site: $date"
pit push origin regen-$date
```

Go to Github and make a pull request. Netflify will deploy a preview site and
make the URL available in the pull request.

If everything is ok merge the pull request.

## About the site

* This site uses [Jekyll](https://jekyllrb.com), a Ruby-based static site generator. For more information about using Jekyll, refer to the [Jekyll documentation](http://jekyllrb.com/docs/home/).

* The site is built with the [U.S. Web Design Standards](https://standards.usa.gov), a set of reusable, high-quality components for modern websites. We're using the Web Design Standards [Jekyll theme](https://github.com/18F/uswds-jekyll) with some customized styles and [Font Awesome](http://fontawesome.io/license/) icons.

### Public domain

This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be released under the CC0 dedication. By submitting a pull request, you are agreeing to comply with this waiver of copyright interest.
