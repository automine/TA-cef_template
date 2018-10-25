# CEF Add-On Template

## Overview
This is a **template** which can be used to quickly onboard CEF-formatted data. Note that this is **NOT** a finished add-on, but is meant to help you create your own. Also note that some of the regular expressions used are not high performing, so it is not suggested that this be used on a high-volume sourcetype.

## Author
Aplura, LLC

## Version
1.4

## Index-time Operations
True
* linebreaking
* timestamping

## How to Use
* Make a copy of this app, which will be your new TA
* In the new TA:
  * Edit the README as needed
  * Edit the `props.conf`, adjusting the `my_sourcetype` to the correct sourcetype for your data
  * Edit the `props.conf` and change the `REPORT-*` directives so that they start with the name of your sourcetype, instead of `sourcetype`.
  * Edit the `transforms.conf` in the same way so that the `props.conf` entries match the stanza names in `transforms.conf`
* Distribute the TA as needed to your search heads and indexers.

## Field Mappings
The `cef_splunk_fields.csv` file contains a listing of the CEF fields and the aliases that are created. Fields which are not listed with a Splunk field will be extracted to the CEF field.

## Changelog

### 1.0
* Initial release

### 1.1
* Fix for CIM mappings (thanks, Greg!)

### 1.2
* Fix for the initial extraction to expect "CEF" at the start of the event

### 1.3
* Fix typo for dest (commented out by default)
* Fix typo for src_nt_host
* Thanks to tonysweet for reporting these!

### 1.4
* Fix another typo (thanks again tonysweet!)
* Added EVALs for dest, dvc, src
