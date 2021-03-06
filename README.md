# wkhtmltopdf heroku-18 Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [wkhtmltopdf][1]
binary with your environment.

## Versions

* Buildpack:   `0.1`
* wkhtmltopdf: `0.12.5-1.bionic_amd64.deb` by default
* without fonts

## Usage

[Add this buildpack][2] to your Heroku application to install the `wkhtmltopdf`
and `wkhtmltoimage` binaries, and the corresponding library `libwkhtmltox`,
into the dynos:

```bash
$ heroku buildpacks:add https://github.com/chap/wkhtmltopdf-heroku-18-buildpack-ming --index 1
```

If you want to use a `wkhtmltopdf` version other than the default set
`WKHTMLTOPDF_DOWNLOAD_URL`:

```bash
heroku config:set WKHTMLTOPDF_DOWNLOAD_URL="https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb"
```

You can see all the releases here:
https://github.com/wkhtmltopdf/wkhtmltopdf/releases/

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```
### Testing
heroku run bin/wkhtmltopdf -V
wkhtmltopdf 0.12.5 (with patched qt)
create a folder called .fonts in your app root directory and copy all necessary fonts inside.
'binary' => '/app/bin/wkhtmltopdf',

### Example
See an example of a [Rails app using wicked_pdf on heroku-18](https://github.com/chap/wicked-pdf-heroku-18).

### Credits

Most of this code was from the [dscout/wkhtmltopdf-buildpack](https://github.com/dscout/wkhtmltopdf-buildpack), 
[chap/wkhtmltopdf-heroku-18-buildpack](https://github.com/chap/wkhtmltopdf-heroku-18-buildpack)

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: http://wkhtmltopdf.org/
[2]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
"# wkhtmltopdf-heroku-18-buildpack-ming" 
