# Grunt Cloudfiles

## About
Cloudfiles is Rackspace's cloud object storage. It's simliar to Amazon S3 and is based on [grunt-s3][grunts3]. This uses the [node-cloudfiles][nodecloudfiles] by [Nodejitsu][nodejitsu]. This is all designed to work with Rackspace Cloudfiles and hasn't been tested on Open Stack.

## Installation
1. npm install grunt-cloudfiles ***OR*** add `grunt-cloudfiles` to your `package.json
1. Add `grunt.registerNpmTasks('grunt-cloudfiles');` to `grunt.js`

## Configuration

You'll need something like the following in your grunt.js. The upload [] list contains the list of src -> container pairs, each of which can have "stripcomponents" specified, which will strip that many path components from the beginning of the path when calculating the destination path name. For instance, a file with a path of a/b/c/file.jpeg with stripcomponents=2 would be uploaded as c/file.jpeg.


        cloudfiles: {
            static: {
                user: 'cloudfilesuser',
                key: '1234longapikey42235',
                upload: [
                    {
                        src: "static/admin/**/*",
                        stripcomponents: 2,
                        container: 'mywiserhealth-cdn'
                    },
                ]
            }

## Changelog

* Auth and adding files

## Future Work

* Provide full management of files
* Implement meta tags

## Credits
* [Aaron Forsander <pifantastic>](https://github.com/pifantastic/grunt-s3)

 [grunts3]: https://github.com/pifantastic/grunt-s3
 [noddecloudfiles]: https://github.com/nodejitsu/node-cloudfiles
 [nodejitsu]: https://github.com/nodejitsu
