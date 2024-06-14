# Mesoanalysis Archive Explorer (MAE Tk) v2.0

The purpose of this Python tkinter zipapp is to expedite viewing, retrieving, and storing imagery spanning 172 products (as of this release) found in the [Storm Prediction Center's](https://spc.noaa.gov) [Mesoscale Analysis Archive](https://www.spc.noaa.gov/exper/ma_archive/)

It is an implementation of [my online version of the Mesoanalysis Archive Explorer](https://ksgwxfan.github.io/mae/index.html).

### Contents
* [Features](#feature-overview)
* [Requirements](#requirements)
* [Installation](#installation)
* [Changing Dates](#changing-dates)
* [Changing Products](#changing-products)
* [Product Help](#product-help)
* [Zooming and Panning](#zooming-and-panning)
* [Changing Options](#changing-options)
* [Copyright/Credits](#copyright-credits)

### Feature Overview

- Makes working with SPC's mesoscale analysis archive substantially easier by enabling quick change of products and date.
  - Keyboard shortcuts included for more control over spatial (canvas) and temporal movement
- Optional archive mode (on by default) which allows local storage of imagery for offline and subsequent retrieval.
- Changing of default settings.

[&#8679; back to Contents](#contents)

### Requirements

- Python (`>= v3.7`) with `tkinter`
- Pillow (Python Imaging Library Fork)
  - `pip install pillow`
- Minimum monitor resolution of around 1600 x 900
- a folder with read/write permissions to place the files in

[&#8679; back to Contents](#contents)

### Changes in this Version
- Restructured code
- Faster in operation; especially the loading of more-recent archived images
- Expanded keyboard shorcuts
- Enhanced product compatibility and user-friendliness
  - Expanded past-compatibility to May of 2005, the beginning of the archive itself.
  - Handles older (600x500 or 800x600) and newer (1000 x 750 since 2023) archived images
  - Product availability is date-based now
- Archive mode is now `On` by default
- improved user-interface
  - removed background color options
    - it was a nice exercise to discover some features in tkinter, but it gave no real value to the purpose of the program
	- it's possible that I may add this back in a future release
  - for Windows systems with an HD monitor, I found some code online that will help everything look clearer. (see [credits](#copyright-credits))
  - product list is now based on categorical `tk.Button`s and a `tk.Listbox`
- Zoom and/or pan on the canvas
  - There are keyboard shortcuts for these too
- added link in the help menu that routes to SPC's brief description of currently-selected product.


### Installation

- Just place `maetk.pyz` into a folder of its own.
  - Archived (local) copies of images will be stored in a descended folder structure from here.
- Open the `maetk.pyz` file (you should be able to just double-click it).

[&#8679; back to Contents](#contents)

### Changing Dates

This program allows several different options to change the date.
- Using the date entry box, you can change the date with a properly formatted string (`YYYYMMDDHH`).
  - For example, to change the date to May 31, 2013 at 23Z, the proper string would be `2013053123`.
  - Other Accepted Formats:
    - Year - 2024 - takes you to January 1, 2024 at 0Z
	- Year & Month - 202406 - takes you to June 1, 2024 at 0Z
	- Year, Month, & Day - 20240614 - takes you to June 14, 2024 at 0Z
- Using the provided convenience buttons, the date can be changed by going back or forward by 1 year, 1 month, 1 week, 1 day, or 1 hour.
  - The `Present Time` button will take you to a near-real time date, usually offset by a few hours. This is due to that the imagery really represents forecast-hour 0 of the RAP model. As models take time to compile/run, generally, the most recent available imagery is from the previous 1 or 2 hours. Also, the archive may not be updated as fast as the 'real-time' data.

For convenience/reference, the current time (in UTC/Zulu) is displayed above the product.

- Hourly temporal movement is also supported via the keys `<` and `>` (well, technically `,` and `.` ... but the greater/lesser-than signs are much more recognizable).
  - Adding `SHIFT` will allow a daily jump
  - Adding `ALT` will allow a 6-hr jump
  - Adding `CTRL` will allow a 3-hr jump

[&#8679; back to Contents](#contents)

### Changing Products

The vast array of archived SPC Mesoanalysis products are grouped (categorized) and generally reflecting their placement on the [real-time SPC Mesoanalysis page](https://www.spc.noaa.gov/exper/mesoanalysis/new/viewsector.php?sector=19). Some "tabs" have been combined to simplify the layout.

- Just click the category, then the product. The change/current product will be highlighted in yellow.
- In addition, the current product description (along with the date) will be placed just above the map.
- Product availability is based on the date as items were added to the archive at different times...yes, it was a long, drawn-out process to find out all of the start/end dates...but I did it for you. Lol.

[&#8679; back to Contents](#contents)

### Product Help

The SPC has a brief description/overview available for a lot of products. A help menu option has been added directs you to the description on their website. If the option is disabled, it means that the product does not have a corresponding help/description on their site.

[&#8679; back to Contents](#contents)

### Zooming and Panning

To zoom into an image, click the zoom toggle near the top left, or alternatively, press the `Z` key

When zoomed in, this also allows the user to move around the canvas. Simply click-and-drag with the mouse/touchpad, use the scrollbars, or use the arrow keys.

[&#8679; back to Contents](#contents)

### Changing Options

##### Archive Mode

Archive mode (ON by default) saves a local (offline) copy of each map you view. This is why it is recommended to place this program in its own folder. A prominent, visible button at the top left of the program toggles its state. If the program loads a local copy of the requested file, a small notifier on the canvas will let the user know.

##### Saving Default Options

In the `Options` menu is `Make Current Settings Default`. It takes the current settings, like archive mode, date, and product and will save those settings for use when you open the program next.

[&#8679; back to Contents](#contents)

### Copyright/Credits

- Mesoanalysis Archive Explorer &copy; 2021-2024, Kyle S. Gentry
- License: MIT
- Background Map (from base_19.gif; base64-encoded into app): [](https://www.spc.noaa.gov) - Some pre-2023 archived files were transparent. This is used as a backdrop for those (convective outlooks, for example). This map was produced from an existing archived map that had little clutter and was easy enough to clean up.
- Stack Overflow results:
  - for the Clock and other things, I relied on searching here for how-to's, but I don't have specific links.
  - Improved text on high-res displays on Windows: [https://stackoverflow.com/questions/41315873/attempting-to-resolve-blurred-tkinter-text-scaling-on-windows-10-high-dpi-disp](https://stackoverflow.com/questions/41315873/attempting-to-resolve-blurred-tkinter-text-scaling-on-windows-10-high-dpi-disp)
- Product Titles/Descriptions were also retrieved via SPC's site too.
- Disclaimer: No products were archived from the end of November 2022 through most of December 2022.

[&#8679; back to Contents](#contents)

