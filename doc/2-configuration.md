
Configuration
=============

Start out by importing Juno:
    
    import juno

Juno has a number of configuration options that you can set by calling
init() with a dictionary of settings at the beginning of your application:
    
    init({'config_opt': 'val', 'other_option': 'val2'})

A full listing of options:
    

General Options
---------------

    * 'log': True
      => If True, writes information to stdout during requests.

Types and Encodings
-------------------

    * 'charset': 'utf-8'
      => The default charset encoding used to load and render templates.

    * 'content_type': 'text/html'
      => The default Content-Type header sent in responses.
  
Server Options
--------------

    * 'mode': 'dev'
      => Controls which interface Juno runs - 'dev' runs the development server,
         'scgi' runs the SCGI server, 'fcgi' runs the FastCGI server, and 'wsgi'
         allows you to retrieve an application() object for mod_wsgi.

    * 'scgi_port': 8000
      => The port where the SCGI server runs.

    * 'fcgi_port': 8000
      => The port where the FastCGI server runs.

    * 'dev_port': 8000
      => The port where the development server runs.

Static File Options
-------------------

    * 'use_static': True
      => If True, Juno sets up a static file handler for you.

    * 'static_url': '/static/*:file/'
      => The URL that is mapped to the static handler.  For example, matches
         '/static/stylesheet.css'.

    * 'static_root': './static/'
      => The filesystem path where static files are loaded from.  '/static/file.css'
         by default will map to './static/file.css' on your system.

    * 'static_handler': static_serve
      => The function that serves static files.

Template Options
----------------

    * 'use_templates': True
      => If True, set up templates.

    * 'template_lib': 'jinja2'
      => Juno has built-in template configurations for Jinja2 and Mako ('mako').

    * 'get_template_handler': _get_template_handler
      => The function Juno calls when you load a template with template().

    * 'render_template_handler': _render_template_handler
      => The function Juno calls when template() renders a template.

    * 'auto_reload_templates': True
      => If True, templates are automatically reloaded when they change.

    * 'template_kwargs': {}
      => Allows you to pass custom keyword arguments to the template lookup
         object (Environment for Jinja2, TemplateLookup for Mako).

    * 'template_root': './templates/'
      => The filesystem path where templates are loaded from.

    * '404_template': '404.html'
      => The template to load when no matching URL is found for a request.

    * '500_template': '500.html'
      => The template to load when an error occurs during a request.

Database Options
----------------

    * 'db_type': 'sqlite'
      => The type of database driver to use.  Can be 'sqlite', 'postgres',
         'mysql', 'oracle', or 'mssql'.

    * 'db_location': ':memory:'
      => The location/address of your database. Read the SQLAlchemy docs
         (http://www.sqlalchemy.org/docs/05/dbengine.html#create-engine-url-arguments)
         for details.

Session Options
---------------

    * 'use_sessions': False
      => If True, Juno will set up and use sessions.

    * 'session_lib': 'beaker'
      => The library to use for sessions.  Currently 'beaker' is the only option.


[dbdocs]: 