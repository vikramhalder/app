If you ever need to download an entire website, perhaps for off-line viewing, wget can do the job — for example:

    $ wget --recursive --no-clobber --page-requisites --html-extension --convert-links --restrict-file-names=windows --domains website.org --no-parent  www.website.org/path1/file.html

This command downloads the website www.website.org/tutorials/html/.

The options are:

  * `--recursive`: download the entire website
  * `--domains website.org`: don't follow links outside website.org
  * `--no-parent`: don't follow links outside the directory tutorials/html/
  * `--page-requisites`: get all the elements that compose the page (images, css and so on)
  * `--html-extension`: save files with the .html extension
  * `--convert-links`: convert links so that they work locally, off-line
  * `--restrict-file-names=windows`: modify filenames so that they will work in Windows as well
  * `--no-clobber`: don't overwrite any existing files (used in case the download is interrupted and resumed).

*Source: [http://www.linuxjournal.com/content/downloading-entire-web-site-wget](http://www.linuxjournal.com/content/downloading-entire-web-site-wget)*
