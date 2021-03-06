# Drupal 8

Get the [Component Libraries module](https://www.drupal.org/project/components):

```bash
drush dl components
drush en components -y
```

## Integration
Ensure the [twig-namespaces gulp task](../gulp/tasks/twig-namespaces.md) is also writing to the theme file. This allows for shorthand pattern inclusion inside of Drupal templates, ie `{% include '@molecules/card.twig %}`

From your Drupal Twig templates in templates/ you can `{% include %}`, `{% extends %}`, and `{% embed %}` your Pattern Lab Twig template files (found in `/source/_patterns`). Each of the top level folders has a Twig Namespace like @organisms and then you append the path down to the file like below.

```twig 
{% include "@organisms/path/to/file.twig" with {
  title: label,
  largeCTA: true
} %}
```

For a demonstration in a sample codebase of how exactly to integrate templates, we will include examples in the default /templates/ folder eventually. :)


## Not using Drupal?

These files are only used for Drupal integration and can be safely ignored/removed:

- drupal/
- templates/
- patternlab.info.yml
- patternlab.libraries.yml
- patternlab.theme
- webpack.drupal.config.js

Make sure the twig-namespaces task is not still attempting to write to the non-existent theme-file!