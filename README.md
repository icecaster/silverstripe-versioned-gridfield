silverstripe-versioned-gridfield / Versioned Model Admin
===============================
(well, its more a detailform, but who searches for silverstripe versioned gridfield detail form)


## Requirements

 * SilverStripe 3.1 

## Introduction

This module provides a gridfield detail form, with the asscoiated actions required for managing versioned objects, eg SiteTree descendants.

This comes in handy especially when using a modeladmin to manage parts of the sitetree.

It hooks into modeladmin via updateEditForm and inserts the VersionedDetailForm automatically
	
## Disclaimer

This code is not particulary nice and has been put together from many areas of the cms and framework.
I'm sure there are more elegant ways of doing this. Keep the pull requests coming!
