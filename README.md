## Editing the styles locally

### Prerequisites

#### Ruby

The documentation HTML is produced with the Ruby-based `jekyll` tool.

Make sure Ruby 2.x is installed.

#### NodeJS

The Sass compiler uses NodeJS.

Make sure NodeJS is installed.

#### AWS command line tools (only for HTML changes)

Our style guide is hosted on AWS so we need tools to push code there.
You will need to get AWS credentials and authenticate your command tools.

### First time

1. Clone the repo

```
git clone git@github.com:planswell/bulma.git styleguide
cd styleguide
npm install
gem install jekyll
```

### Every time


1. In a terminal

```
npm run start-docs
```

2. In another terminal,

```
cd docs
jekyll serve --incremental --config _config.local.yml --port 4010
```

3. Open a browser to

```
http://localhost:4010
```

4. Now open an editor and edit

```
docs/_sass/planswell.scss
```

Save the files, refresh the browser, and you should see the changes.


#### Publish changes once done

1. Push to git

```
git commit -am "<describe changes>"
git push origin master
```

2. Push to AWS (might not be needed unless HTML is changed)

```
jekyll build
aws s3 sync ./docs/_site s3://styleguide.planswell.ca
```
