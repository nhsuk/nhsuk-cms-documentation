# Style Guide

## Adding a new component or pattern

The live site pages are built from many components which have been tested for usability and accessibility. Please follow the criteria on the [service manual](https://service-manual.nhs.uk/community/contribution-criteria) for contributing new patterns and components.


## Python

Python code needs to pass our automated linting checks. See [testing](../tests/index.md#formatting).

* [PEP8](https://www.python.org/dev/peps/pep-0008/) style, except:
    * 119 maximum line width
    * Hanging indents
    * Trailing commas
* [PEP257](https://www.python.org/dev/peps/pep-0257/) for Docstrings
    * Triple double-quoted strings
    * One line summary ending in full-stop on same line as opening quotes
    * Closing quotes on separate line

---

Do not write HTML in python code, use `render_to_string` and a template file.

Don't do:
```python
# source_code.py
my_html = "<img src='{}'>".format(img_src)
```

Instead, do:
```python
# source_code.py
my_html = render_to_string("image_tag.html", {"source": img_src})
```

```html
<!--image_tag.html-->
<img src="{{ source }}">
```

## Models

### Inheritance

All page models should ultimately inherit from a schema.org abstract page type from `core.schema_org.models`

### Naming

Stick to the python convention of using `UpperCaseCamelCase` for classes.
The last word of the class should be the type of model, so page models should end in `Page`, mixins should end in `Mixin`.

e.g `HomePage`, `ConditionsHubPage`, `TagMixin`, `SectionBlock`, `HeaderSetting` etc.

### Migrations

Always give your data migration files a sensible name. Running `python manage.py makemigrations`
will sometimes result in a migration file such as `0005_auto_20180601_1455.py`. You should rename this file to be
descriptive of the change, e.g `0005_add_homepage_description.py`

Always squash migrations into one migration per feature. Usually this means deleting your migrations and running `makemigrations` again before opening a pull request.

## Templates

[http://docs.wagtail.io/en/v2.5/topics/writing_templates.html](http://docs.wagtail.io/en/v2.5/topics/writing_templates.html)

Templates should go into the default location that wagtail expects them based on the model name.

Use `{{ page.field }}` instead of `{{ self.field }}`.

Use `{% pageurl page %}` instead of `{{ page.url }}`.

2 spaces of indentation for nested HTML tags or django tags.
```html
<ul>
  {% for item in list %}
    <li>{{ item }}</li>
  {% endfor %}
</ul>
```

Spaces around django tags brackets: `{{ page.field }}` instead of `{{page.field}}`.

Keep complex logic out of html, using templatetags or custom page context instead.

## CSS and JS

Stylesheets are currently written with SASS and compiled to CSS during the build process. Contributions to styling are done following the [BEM](http://getbem.com/introduction/) convention.

CSS linting rules are defined in the `frontend/linter/.sass-lint.yml` file.

JS linting rules are are defined by [eslint-config-nhsuk](https://github.com/nhsuk/eslint-config-nhsuk).
