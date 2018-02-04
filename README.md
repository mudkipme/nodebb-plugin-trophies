Trophy Plugin for NodeBB
================

This plugin lets you create reward badges for your users and manually add them to their user profile.

It was developed for use on [52Poké Forums](https://52poke.net/).

## Setup

First, install it to your NodeBB instance. You can do it from the admin interface or you can install it with

```bash
npm install nodebb-plugin-trophies-updated
```

from your nodebb install directory.

Plugin uses widget system, but intended to be displayed only on the user profile page. Therefore, you have to have a widget area in your theme, template file `templates/account/profile.tpl` to be more specific, in order display this widget.

For the Persona theme, I had to add following, around line 26:

```html
<div widget-area="middle" class="text-center">
  <!-- BEGIN widgets.middle -->
  {{widgets.middle.html}}
  <!-- END widgets.middle -->
</div>
```

It's also needed to define the widget area in `filter:widgets.getAreas` hook.

```
{
  name: "Profile Middle",
  template: "account/profile.tpl",
  location: "middle"
}
```

You can also take a look at [nodebb-theme-persona-52poke-forums](https://github.com/mudkipme/nodebb-theme-persona-52poke-forums).

Then, you can go to your admin panel and go hog wild.

## License

[MIT](LICENSE)

## Credits

This plugin is a fork of [toxuin](https://github.com/toxuin)'s original [nodebb-plugin-trophies](https://github.com/toxuin/nodebb-plugin-trophies).