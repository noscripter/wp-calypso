Plugin Autoupdate Toggle
=========

This component is used to display a plugin autupdate toggle.

#### How to use:

```js
var PluginAutoupdateToggle = require( 'my-sites/plugins/plugin-autoupdate-toggle' );

render: function() {
	return (
		<div className="your-plugins-list">
			<PluginAutoupdateToggle
				plugin={ plugin }
				site={ site }
				notices={ notices }
				wporg={ true }
			/>
		</div>
	);
}
```

#### Props

* `plugin`: a plugin object.
* `site`: a site object.
* `notices`: a notices object.
* `wporg`: whether the plugin is from .org or not
