Welcome to kw6's documentation!
===============================

Minimalistic library for reading files in the kw6 file format.

Install
=======

.. code-block::

    pip install kw6

Usage
=====

.. code-block:: python

    from pathlib import Path
    import kw6

    path = Path('...')

    for position in kw6.Reader.from_path(path):
        for camera in position.cameras:
            camera.image.save(
                f'{position.header.frame_index}_{camera.header.camera_index}.png'
            )

Command line tool for converting a kw6 file to a video or folder with images:

.. code-block::

    python -m kw6.to_video path/to/kw6
    python -m kw6.to_png path/to/kw6

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   reader
   position
   camera
   to_png
   to_video

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
