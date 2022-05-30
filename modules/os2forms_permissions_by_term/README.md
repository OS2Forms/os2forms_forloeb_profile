# OS2Forms permission by term module
This module implements permission by term access restrictions
on several lists and entity displays related to webform and maestro.

## Setup configuration
Add to your settings.php or local.settings.php
```
$config['permissions_by_term.settings'] = [
 'permissions_mode' => FALSE,
 'require_all_terms_granted' => FALSE,
 'disable_node_access_records' => FALSE
 'target_bundles' => ['user_affiliation']
]
```

Alternative change your site configuration on admin/permissions-by-term/settings to match the above.

## Usage
- The user affiliation taxonomy is added to webform config form, nodes (of type webform) and Maestro workflow forms.
- The Permissions by Term module adds a form element to the user form.
- When a user visits an entity of the above mentioned this module checks for match between the entity and the users
  affiliation. If no match is found access is denied.
