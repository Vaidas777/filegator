<p align="center">
<img src="https://raw.githubusercontent.com/filegator/filegator/master/dist/img/logo.gif">
</p>

<p align="center">
<a href="https://travis-ci.org/filegator/filegator"><img src="https://travis-ci.org/filegator/filegator.svg?branch=master" alt="Build Status"></a>
<a href="https://codecov.io/gh/filegator/filegator"><img src="https://codecov.io/gh/filegator/filegator/branch/master/graph/badge.svg" alt="Code Coverage"></a>
<a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License"></a>
  </p>


## FileGator - Powerful Multi-User File Manager

FileGator is a free, open-source PHP script for managing files and folders.

You can manage files inside your local repository folder (on your server's hard drive) or connect to other storage adapters (see below).

FileGator has multi-user support so you can have admins and other users managing files with different access permissions, roles and home folders.

All basic file operations are supported: copy, move, rename, create, delete, zip, unzip, download, upload.

If allowed, users can download multiple files or folders at once.

File upload supports drag&drop, progress bar, pause and resume. Upload is chunked so you should be able to upload large files regardless of your server configuration.


## Demo
[https://demo.filegator.io](https://demo.filegator.io)

This is read-only demo with guest account enabled.
- you can log in as `john/john` to see John's private files
- or `jane/jane` as readonly + download user.


## Documentation
[Check out the documentation](https://docs.filegator.io/)


## Features & Goals
- Multiple storage adapters (Local, FTP, Amazon S3, Dropbox, DO Spaces, Azure Blob and many others via [Flysystem](https://github.com/thephpleague/flysystem))
- Multiple auth adapters with roles and permissions (Store users in json file or database)
- Multiple session adapters (Native File, Pdo, MongoDB, Memcached and others via [Symfony](https://github.com/symfony/symfony/tree/master/src/Symfony/Component/HttpFoundation/Session/Storage/Handler))
- Single page front-end (built with [Vuejs](https://github.com/vuejs/vue), [Bulma](https://github.com/jgthms/bulma) and [Buefy](https://github.com/buefy/buefy))
- Chunked uploads (built with [Resumable.js](https://github.com/23/resumable.js))
- Zip and bulk download support
- Highly extensible, decoupled and tested code
- No database required
- Framework free [™](https://www.youtube.com/watch?v=L5jI9I03q8E)


## Requirements
- PHP 7.1.3+


## Download precompiled build
Precompiled build is created for non-developers. In this version, the frontend (html, css and javascript) is compiled for you and the source code is removed so the final archive contains only minimum files.

[Download & install instructinos](https://docs.filegator.io/install.html)


## Project setup for development (Linux)

You must have `git`, `php`, `npm`, and `composer` installed.

```
git clone git@github.com:filegator/filegator.git
cd filegator
cp configuration_sample.php configuration.php
sudo chmod -R 777 private/
sudo chmod -R 777 repository/
composer install
npm install
npm run build
```

We also have a sample docker image [here](https://github.com/filegator/demo)


## Compiles and hot-reloads

The following command will launch backend and frontend on ports 8081 and 8080:

```
npm run serve
```
Once everything is ready visit: `http://localhost:8080`


## Run tests & static analysis

Testing requires xdebug and sqlite php extensions.

```
vendor/bin/phpunit
vendor/bin/phpstan analyse ./backend
npm run lint
npm run e2e
```


## Deployment

Set the website document root to `/dist` directory. This is also known as 'public' folder.

NOTE: For security reasons `/dist` is the ONLY folder you want to be exposed through the web. Everything else should be outside of your web root, this way people can’t access any of your important files through the browser.

## Show your support

Please ⭐️ this repository if this project helped you!

## Security

If you discover any security related issues, please email alcalbg@gmail.com instead of using the issue tracker.

## License

Copyright (c) 2019 [Milos Stojanovic](https://github.com/alcalbg).

This project is MIT licensed.
