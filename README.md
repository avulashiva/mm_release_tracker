# MediaMonks Release Tracker
 
Allows you to track the release number of your site. This can be used
to determine the version of a project once deployed onto a server. This 
allows you to determine if a new build was successfully deployed to the
server _and_ that updated configuration was imported too by looking at
the Drupal Status Page.
 
We recommend to use the same release number as Git tag that was used for
the code, and use the release number as part of the commit message. That 
way it is easy to track and search for the release numbers.

## How to use

The release number will be show on the status page. If the version is
shown without errors but doesn't match your new release number, the new
configuration was not deployed successfully. If the release number in
the sync configuration doesn't match the release number in the active
configuration an error will be shown in the status report that the
active configuration is out of date. Run a configuration import to sync.

Update the release number and export config before tagging a new
release. This will allow you to check on the live/staging server if your
release has been successfully uploaded and imported.

Using drush:
- Set release to 1.1: 
  ```
  drush config-set mm_release_tracker.settings release 1.1
  ```
- Export the configuration: 
  ```
  drush config-export
  ```
- Add your exported config to version control.

## Is there no user interface?
No, and that is on purpose. That way nobody can manually fake the 
release.
