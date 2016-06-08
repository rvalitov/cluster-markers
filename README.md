# About
This project contains a collection of images (and related settings) that can be used as icons for clustering markers in Google Maps. This project was created as a support library for the **[MapEx Widget](https://github.com/rvalitov/widgetkit-map-ex)**: all icons posted here become automatically available in the [MapEx Marker Library](https://github.com/rvalitov/widgetkit-map-ex/wiki/Markers-Clustering).
  
# Structure of the project
## Description of a collection set
Each set of the collection describes a complete settings for clustering and are defined by the following parameters:

* **name** (required, string) - unique name (maximum size - 64 characters, otherwise it will be truncated) of the set that identifies it in plain text format.
* **info** (required, string) - detailed information about this set. This information should contain licensing information, authors credits, version information, source or origin of the images, etc. Maximum size - 2000 characters (including spaces and special chars), otherwise this set will be ignored. It's allowed to use the following HTML tags in info text:
	* `<strong>`
	* `<em>`
	* `<a>`
	* `h1`
	* `h2`
	* `h3`
	* `h4`
* **levels** (required, array) - contains information about each cluster level. This array must contain information at least for 1 level. Every level is described with the following parameters:

	* **icon** (required, string) - URL of the image (icon), can be in PNG or SVG format. This image must be located inside the _images_ folder of this project.
	* **color** (required, string) - color of the text label, can be one of the [HTML color names](http://www.w3schools.com/colors/colors_names.asp) or a color code (e.g. #ff0f11). 
	* **width** (required, number) - width of the image in pixels. 
	* **height** (required, number) - height of the image in pixels.
	* **size** (required, number) - size (in pixels) of the font used in the text label. 
	* **icon_x** (required, number or empty value) - the X anchor of the image, a place where the icon's hotspot is located. The position is defined in pixels and is relative to the the image's dimensions, so that the upper left corner of the image is a zero-point (0,0); axes have the following orientation: the X to the right; Y to the bottom. If the position is empty string `""` then the center of the image is set as the anchor.
	* **icon_y** (required, number or empty value) - the Y anchor of the image.
	* **label_x** (required, number) - the X anchor of the label, a place where the text label is located. The position is defined in pixels and is relative to the the image's dimensions. A positive value sets the offset relative to the top/left side of the image; negative value - relative to the right/bottom side of the image; zero - means to use center/middle position. The absolute value of the offset must be less than corresponding image's dimension, otherwise such value is considered to be invalid and is ignored.
	* **label_y** (required, number) - the Y anchor of the label.

## Files and folders

* **images** - folder contains subfolders. Each subfolder contains images that belong to a dedicated collection set.
* **config** - folder contains the following files: 
	* **config.json** - a list of all collections of this project in JSON format. All the fields are defined according to the description provided in the section above.

# How to contribute
You a welcome to extend this project by adding new icon sets. You can do this by [forking the project](https://help.github.com/articles/fork-a-repo/), then adding new icons and filling in the related information to the CSV and JSON files and then making a [pull request](https://help.github.com/articles/creating-a-pull-request/).