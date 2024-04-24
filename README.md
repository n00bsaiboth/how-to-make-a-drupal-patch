# How to make a Drupal patch

It's easier, than you think. This is for demonstration purposes only and this is a poor example.

## First download Drupal Paragraph module

`git clone git@git.drupal.org:project/paragraphs.git`

Then edit the paragraphs.info.yml file, like so.

`description: 'Enables the creation of paragraphs entities. So I edit this line here. '`

Now you need to run the `git diff > my-patch.patch` command. That creates the actual patch.

Now that you got your patch, you need to copy that to your Drupal project folder, let say for example /patches/my-patch.patch.

## Add the patch to composer.json

The next thing is to add it to your composer.json file, so it goes someways, like this,

```
"extra": {
        "patches": {
            "drupal/paragraphs": {
                "Edited the description": "patches/description-patch.patch"
            }
        }
```