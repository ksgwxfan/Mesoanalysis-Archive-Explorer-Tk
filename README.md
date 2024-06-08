# Mesoanalysis Archive Explorer (MAE Tk) v1.01

The original version of this app (`v1.0`) was released in July 2021.

The purpose of this Python tkinter zipapp is to expedite viewing, retrieving, and optionally storing imagery found in the [Storm Prediction Center's](https://spc.noaa.gov) [Mesoscale Analysis Archive](https://www.spc.noaa.gov/exper/ma_archive/).

It is an implementation of [my online version of the Mesoanalysis Archive Explorer](https://ksgwxfan.github.io/mae/index.html).

### Contents
* [Changes From v1.0](#changes-from-v1)
* [Features](#feature-overview)
* [Requirements](#requirements)
* [Installation](#installation)
* [Changing Dates](#changing-dates)
* [Changing Products](#changing-products)
* [Changing Options](#changing-options)
* [Credits/Links](#credits)

### Changes from v1
- fixed message in the change defaults dialog where it always reported archive mode as being turned off.
- fixed some syntax where I used the statement `is` instead of `==`. This will clear the formerly displayed warning in the console.

### Feature Overview

- Makes working with SPC's mesoscale analysis archive substantially easier by enabling quick change of products and date.
  - Keyboard shortcuts included for more control over temporal movement
- Optional archive mode which allows local storage of imagery for offline use
- Changing of background-color.
- Changing of default settings.

[&#8679; back to Contents](#contents)

### Requirements

- Python (`>= v3.5`) with `tkinter`
- Pillow (Python Imaging Library Fork)
  - `pip install pillow`

[&#8679; back to Contents](#contents)

### Installation

- Just place `maetk.pyz` into a folder of its own.
- Open the `maetk.pyz` file (you should be able to just double-click it).

[&#8679; back to Contents](#contents)

### Changing Dates

![Change the date](https://ksgwxfan.github.io/mae/project_resources/v01_change_date.gif)

This program allows several different options to change the date and move between times.
- Using the date entry box, you can change the date with a properly formatted string (`YYYYMMDDHH`).
  - For example, to change the date to May 31, 2013 at 23Z, the proper string would be `2013053123`.
- Using the provided buttons, the date can be changed by going back or forward by 1 year, 1 month, 1 week, 1 day, or 1 hour.
  - The `Present Time` button will take you to a near-real time date, usually offset by a few hours. This is due to that the imagery really represents forecast-hour 0 of the RAP model. As models take time to compile/run, generally, the most recent available imagery is from the previous 1 or 2 hours. Also, the archive may not be updated as fast as the 'real-time' data.

For convenience/reference, the current time (in UTC/Zulu) is displayed on the main toolbar.

- Hourly temporal movement is also supported via the keys `<` and `>`. Future updates/versions will likely include more.

[&#8679; back to Contents](#contents)

### Changing Products

![Change the Product](https://ksgwxfan.github.io/mae/project_resources/v01_change_products.png)

The vast array of archived SPC Mesoanalysis products are categorized into different categories, generally reflecting their placement on the [real-time SPC Mesoanalysis page](https://www.spc.noaa.gov/exper/mesoanalysis/new/viewsector.php?sector=19).

- Just click the category, then the product. The change/current product will be highlighted in yellow.

- In addtion, the current product description (along with the date) will be placed just above the map.

[&#8679; back to Contents](#contents)

### Changing Options

##### Archive Mode

Turning on `Archive Mode` will save the imagery locally (hence the need to place this program in its own folder). To turn this option on (or off), click `Options` on the toolbar and select `Archive Mode`. It will be turned on if there is a check-mark beside it. In subsequent loading of archived imagery, local existence is checked first before attempting to download.

##### Change the Background Color

Under `Options`, select `Theme`. There are a few pre-defined colors. Choose `Custom` to define your own background/theme color.

##### Saving Default Options

Below the archive mode setting is `Make Current Settings Default`. It takes the current settings, like archive mode, date, and product and will save those settings for use when you open the program next.

[&#8679; back to Contents](#contents)

### Credits

- Background Map (base_19.gif): [](https://www.spc.noaa.gov) - This map was produced from an existing archived map that had little clutter and was easy enough to clean up. It is used as the backdrop and to display transparent products like convective outlooks. This was done because I couldn't find a blank basemap that would match the archived transparent products.
- Product Titles/Descriptions were also retrieved via SPC's site too.

[&#8679; back to Contents](#contents)

