# Jekyll Art Gallery plugin

An advanced Jekyll plugin for generating art galleries on static/generated sites. Supports image tagging, thumbnails, sorting, image rotation, post-processing (remove EXIF, add watermark), multiple collections and much more.
You can see a gallery generated with this plugin on [this artist's site](http://olgaivkin.com)

## Installing
You need rmagick, exifr, imgemagick and magickwand lib. On Ubuntu run

	sudo apt-get install libmagickwand-dev imagemagick
	sudo gem install rmagick exifr

Then place art_gallery_index.html, art_gallery_page.html and jekyll-art-gallery-generator.rb into your site's _plugins directory or into jekyll global (plugin folder)[https://github.com/jekyll/jekyll/blob/master/site/_docs/plugins.md]. Add gallery.yaml into your data folder and edit it appropriatelly.
Use _data/gallery.yml, not _config.xml for the gallery settings.

Note that  art_gallery_index.html, art_gallery_page.html are just samples and should be modified to fit your site.

## How it works

The plugin will use copy files from the source folder into the destination folder per your settings in gallery.yaml, and transform them in the destination folder per your settings. The source files will never be changed.
The plugin enumerates the folders and files, copies if necessary into the destination/generated site directory, then creates the thumbnails if necessary, saves that info into the page
 data and into the site data (like auto generating navigation links), then runs the templates through jekyll/liquid engine and creates appropriate index.html pages in each portfolio folder
source-jekyll-gallery-generator. The individual portfolio pages are generated from the templates in _plugins directory like art_gallery_index.html. If a file or a folder name starts with . it will be skipped.

## Configuration

Look in the gallery.yaml, it should be pretty self explanatory.

* scale_method - fill, fit, limit
* symlink - makes it link, not copy files.
* images are .jpg, .jpeg, .png, .gif

The plugin is not yet packaged as a gem, just not time to do it.

