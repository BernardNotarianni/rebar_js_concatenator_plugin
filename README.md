# Rebar JS Concatenator Plugin

Concatenate your JavaScript files when building your Erlang OTP
application.

## Installation

1. Specify ```rebar_js_concatenator_plugin``` as a dependency in your
   ```rebar.config```.

```erlang
{deps, [
       {rebar_js_concatenator_plugin, ".*",
        {git, "git://github.com/cmeiklejohn/rebar_js_concatenator_plugin.git", {branch, "master"}}}
]}.
```

2. Configure as a plugin in your ```rebar.config```.

```erlang
{plugins, [rebar_js_concatenator_plugin]}.
```

## Configuration

Below is an example configuration with one concatenation.  In this example, ```vendor.js``` is the destination file, compiled from both JQuery and Ember.js.  Place the below configuration in your applications ```rebar.config``` file.

```erlang
{js_concatenator, [
    {out_dir,    "priv/assets/javascripts"},
    {doc_root,   "priv/assets/javascripts"},
    {concatenations, [
        {"vendor.js", ["jquery-1.7.2.js", "ember-latest.js"]}
    ]}
]}.
```
