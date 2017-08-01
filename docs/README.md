## Building the documentation

The documentation HTML is produced with the Ruby-based `jekyll` tool. Sorry.

1. Make sure Ruby 2.x is installed.

2. `gem install jekyll`

3. In a terminal,

```
cd docs
jekyll serve --incremental --config _config.local.yml --port 4010
```

4. In another terminal,
```
npm run start-docs
```

5. Now open an editor and edit
```
docs/_sass/planswell.scss
```
