# Force Download #

When this event is attached to a page, it enables the page to force a download. The download can be triggered by adding the parameter `file` to the URL:

	<a href="/download/?file=workspace/uploads/manual.pdf">Download manual</a>

## Security ##

To prevent that anyone can download any file from your website you have to set which folders are allowed for visitors to download files of. Otherwise evil people can download your config-settings for example simply by changing the URL in the browser bar to: `/download/?file=manifest/config.php`.

To do this, you need to add a list of trusted locations to the _'Force Download'_-section on the preferences page.

## Download the current page ##

You can also download the page itself, by adding the parameter `download` to the URL. The value of this parameter will be the name of the file. For example:

	<a href="/sheet/?download=sheet.xml">Download sheet in XML-format</a>

## Default Download Directory ##

The *first* directory listed in `$allowedDirs` will act as a default download directory if you do not wish to include a path in the `?file=` parameter. For example, if the first entry in `$allowedDirs` is `workspace/uploads` then a GET request of `?file=my-example-file.pdf` will download the file `workspace/uploads/my-example-file.pdf`

## Missing or Unauthorised Files ##

Requests for files that cannot be found on the filesystem, or are not included in the `$allowedDirs` will show Symphony's 404 page.
