===================
Propy Documentation
===================

.. image:: https://img.shields.io/pypi/pyversions/propy.svg
    :target: #

.. image:: https://img.shields.io/pypi/v/propy.svg
    :target: #

.. image:: https://travis-ci.com/mpewsey/propy.svg?branch=master
    :target: https://travis-ci.com/mpewsey/propy

.. image:: https://readthedocs.org/projects/propy/badge/?version=latest
    :target: https://propy.readthedocs.io/en/latest/?badge=latest

.. image:: https://codecov.io/gh/mpewsey/propy/branch/master/graph/badge.svg
    :target: https://codecov.io/gh/mpewsey/propy

About
=====
This package contains convenience functions for creating class properties
with type conversion and validation characteristics in Python. While Python's
lack of typecasting is certainly one of the features that make it an easy to
learn and code language, there are certainly times when you might want
to implement controls on the types of values a class property can assume.
This package provides a few functions to hopefully handle those situations
a little easier.

To provide an example, let's assume you have a property that you want to restrict
to boolean values. To do this normally, you would need to setup a property
manually by creating custom setter, getter, and deleter functions. With this
package, however, you can use the provided :func:`.bool_property` function instead
as follows:


.. code-block:: python

    import propy

    class Example():
        bool_prop = propy.bool_property('bool_prop')


The :func:`.bool_property` function creates the setter, getter, and deleter that you
would have needed to manually define. The 'bool_prop' name supplied to the
function is used to create a "private" '_bool_prop' attribute behind the scenes,
then the "public" 'bool_prop' attribute simply calls the defined setter, getter,
and deleter to perform the respective action on that private attribute.
It's not a huge gain, but using this package function reduces to a single line
of code what would have typically taken about 10 lines.

Installation
============
This package may be installed via pip:

.. code-block:: none

    pip install propy


API Documentation
=================
.. toctree::
    :maxdepth: 2

    propy
