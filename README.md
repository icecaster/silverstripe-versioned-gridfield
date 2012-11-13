silverstripe-versioned-gridfield
===============================
(well, its more a detailform, but who searches for silverstripe versioned gridfield detail form)


## Requirements

 * SilverStripe 3.0 or newer

## Introduction

This module provides a gridfield detail form, with the asscoiated actions required for managing versioned objects, eg SiteTree descendants.

This comes in handy especially when using a modeladmin to manage parts of the sitetree.

Add this to your modeladmin to get the magic going:


	function getEditForm($id = null, $fields = null) {
		$form = parent::getEditForm();

		$fieldList = $form->Fields();

		foreach($fieldList as $field) {
			if($field instanceof GridField) {
				$class = $field->getList()->dataClass();
				if(Object::has_extension($class, "Versioned")) {
					$config = $field->getConfig();
					$config->removeComponentsByType('GridFieldDeleteAction')
						->removeComponentsByType('GridFieldDetailForm')
						->addComponents(new VersionedGridFieldDetailForm());
					$field->setConfig($config);
				}
			}
		}
		return $form;
	}
	
## Disclaimer

This code is not particulary nice and has been put together from many areas of the cms and framework.
I'm sure there are more elegant ways of doing this. Keep the pull requests coming!
