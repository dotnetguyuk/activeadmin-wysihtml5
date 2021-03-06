# `activeadmin-wysihtml5`

![activeadmin-wysihtml5 screenshot](https://raw.github.com/stefanoverna/activeadmin-wysihtml5/master/screenshot.png)

![activeadmin-wysihtml5 screenshot](https://raw.github.com/stefanoverna/activeadmin-wysihtml5/master/link_screenshot.png)

![activeadmin-wysihtml5 screenshot](https://raw.github.com/stefanoverna/activeadmin-wysihtml5/master/image_screenshot.png)

This is a wysiyg html editor for the [Active Admin](http://activeadmin.info/)
interface using [wysihtml5](https://github.com/xing/wysihtml5).

## Installation

```ruby
# Gemfile

gem 'activeadmin-wysihtml5'
```

Now install the migrations:

```bash
$ rake active_admin_editor:install:migrations
$ rake db:migrate
```

## Usage
This gem provides you with a custom formtastic input called `:wysihtml5` to build out an html editor.
All you have to do is specify the `:as` option for your inputs.

**Example**

```ruby
ActiveAdmin.register Page do
  form do |f|
    f.inputs do
      f.input :title
      f.input :content, as: :wysihtml5, input_html: { commands: [ :link ], blocks: [ :h3, :p] }
    end

    f.buttons
  end
end
```

## Options to be passed into `input_html`

### `:commands`

* `:all`: all the available commands;
* `:barebone`: just bold, italic, and link (default);
* an array with one or more of the following symbols: `:bold`, `:italic`, `:underline`, `:ul`, `:ol`, `:outdent`, `:indent`, `:link`, `:image`, `:source`

### `:blocks`

* `:all`: all the available blocks;
* `:barebone`: just h3, h4, p;
* `:none`: just p (default);
* an array with one or more of the following symbols: `:h1`, `:h2`, `:h3`, `:h4`, `:h5`, `:h6`, `:p`

### `:height`

* `:tiny`
* `:small`
* `:medium`
* `:large`
* `:huge`
* an integer representing the height of the editor;

