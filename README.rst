=======
webargs
=======

.. image:: https://badge.fury.io/py/webargs.png
    :target: http://badge.fury.io/py/webargs

.. image:: https://travis-ci.org/sloria/webargs.png?branch=master
    :target: https://travis-ci.org/sloria/webargs

Homepage: https://webargs.readthedocs.org/

webargs is a Python library for parsing HTTP request arguments, with built-in support for popular web frameworks, including Flask, Django, Bottle, Tornado, and Pyramid.

.. code-block:: python

    from flask import Flask
    from webargs import Arg
    from webargs.flaskparser import use_args

    app = Flask(__name__)

    hello_args = {
        'name': Arg(str, required=True)
    }

    @app.route('/')
    @use_args(hello_args)
    def index(args):
        return 'Hello ' + args['name']

    if __name__ == '__main__':
        app.run()

    # curl http://localhost:5000/\?name\='World'
    # Hello World

Install
-------

::

    pip install -U webargs

webargs supports Python >= 2.6 or >= 3.3.


Documentation
-------------

Full documentation is available at https://webargs.readthedocs.org/.

Project Links
-------------

- Docs: http://webargs.rtfd.org/
- Changelog: http://webargs.readthedocs.org/en/latest/changelog.html
- PyPI: https://pypi.python.org/pypi/webargs
- Issues: https://github.com/sloria/webargs/issues


License
-------

MIT licensed. See the `LICENSE <https://github.com/sloria/webargs/blob/master/LICENSE>`_ file for more details.
