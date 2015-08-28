---
layout: with-sidebar
title: Using the Map Fields Dialog
bodyclass: homepage
---

This guide covers the advanced features of the Map Fields dialog

<img src="/images/map_fields.png" alt="Map Fields Dialog" width=50% align="middle">

### Overview

The Map Fields dialog controls how the items in your CSV map to fields in your dataset.  By default, DataSync will automatically analyze the shape of your CSV and the associated dataset.  Once analyzed, it will attempt to automatically map your fields in the CSV to your fields in the dataset.  While most of the times this is sufficient, sometimes DataSync will need a little more help before it's ready to upload the file.  This is where this dialog comes in.  

As you change options in the dialog, DataSync will provide immediate, realtime feedback around how it views your CSV.  For example, toggling the "has header row" option in the UI will immediately reflect the fact that the first row in the CSV will be imported as data, rather than as a header.  

![Header row before and after](/images/header_row_before_after.png)

Similarly, changing the "separator" under advanced options will reflect the fact that there are new columns which you can map.

![Using different separator](/images/different_separator.png)

DataSync will also automatically validate that your configuration is correct *before* the upload takes place.  When you click on "OK" DataSync will validate all of the fields and ensure that their values are valid for the given fields.  If not, you'll be presented with a friendly error that should help you quickly identify and fix the issue:

<img src="/images/sample_error.png" alt="Sample Error" width=50% align="middle">

Once validated, this dialog simply generates the same [control file]({{ site.root }}/resources/control-config.html) that you would use from the command line.  Because of this, any saved job can also be run as a scheduled job in headless mode. 

While typically the default settings will be sufficient, every once in a while you will need to take additional steps to get your CSV uploaded.  The following sections detail how you can use the more advanced features of this UI to successfully upload your CSV. 

### Mapping items in the CSV to fields in the dataset

To map items in the CSV to fields in your dataset, simply click the dropdown and select the dataset field to which the column in the CSV should map.

<img src="/images/select_field.png" alt="Select field" width=50% align="middle">

If you don't want to include this column in the upload, simply select "Ignore this field"

<img src="/images/ignore_field.png" alt="Ignore field" width=50% align="middle">

As mentioned above, the UI will show you a preview of your data inline.  The top row is your header, while the bottom row is your data.  

<img src="/images/inline.png" alt="Inline Preview" width=50% align="middle">

We recommend checking this prior to upload to ensure that all data is uploaded.  Common mistakes include having the "has header row" set when there is no header row in the dataset. 

![Header row before and after](/images/header_row_before_after.png)

### Synthetic locations

When creating a dataset, you can choose to create a location column from components in the original file.  To do the same in DataSync, simply click on the "Add synthetic columns" link in the bottom left to get the synthetic columns dialog:

<img src="/images/synthetic_columns.png" alt="Synthetic columns" width=33% align="middle">

Select the location field in the top dropdown and then map the items in your CSV to the components of your location component.  

Once set, you'll see the following when you click the "Manage Synthetic Columns" link

<img src="/images/show_synthetic_columns.png" alt="Show synthetic columns pane" width=50% align="middle">
 
To manage or remove the column, simply click either the manage or remove link.  To add another synthetic location, simply click "add" and follow the above steps

### Advanced options

All other options available in the Control File can be found under the Advanced Options panel.  

<img src="/images/advanced_options.png" alt="Advanced Options" width=50% align="middle">

Authoritative documentation on the accepted values can be found in the [Control file configuration]({{ site.root }}/resources/control-config.html) page