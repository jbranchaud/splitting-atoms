# Atom Events

Within your packages, you have the ability to subscribe to various events
so that your package can react to those events being triggered. For example,
whenever the active buffer changes, Atom's status bar package updates the
various pieces of information with respect to the new active editor.

Subscribing to Atom events is an integral part of most Atom packages.

## Events

Currently there is no formal documentation of Atom events to which a package
can subscribe. Furthermore, as the API evolves during the Atom beta, some
events may come and go. Nevertheless, you should still take advantage of
Atom events in your packages.

To find Atom events that are available to you, you can dig through code of
[existing packages](https://github.com/atom) or checkout this [unofficial
list of events](https://gist.github.com/ardcore/9262498) that has been
aggregated by [ardcore](https://github.com/ardcore).

The following is a listing of events, in what context they can be used, and
examples of how one might go about using them:

### active-buffer-changed

Used by: [atom/status-bar](https://github.com/atom/status-bar/blob/master/lib/cursor-position-view.coffee)

### cursor:moved

Used by: [atom/status-bar](https://github.com/atom/status-bar/blob/master/lib/cursor-position-view.coffee)
