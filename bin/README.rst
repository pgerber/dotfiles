Binaries
========


errno
-----

Print details about errno matching given number, range or description.

Examples
^^^^^^^^

By number:

.. code::

    $ errno 13
     13 → EACCES          → Permission denied

By range:

.. code::

    $ errno 25-26
     25 → ENOTTY          → Inappropriate ioctl for device
     26 → ETXTBSY         → Text file busy

By symbol/description:

.. code::

    $ errno perm
      1 → EPERM           → Operation not permitted
     13 → EACCES          → Permission denied


tb (Sandboxed Tor Browser)
--------------------------

Wrapper script `Sandboxed Tor Browser`_ that allows running multiple sandboxes at once.

Sandboxes are located ``~/.local/share/tor-browser-sandboxes``. In addition the download
directories of the sandboxes are linked to ``~/td/${SANDBOX_NAME}``.

.. important::

    The wrapper script adds additional arguments that start with ``+``. Only one can be
    specified and it must be the first argument. Further arguments are forwarded to
    ``tor-browser-sandboxed``.

Prerequisites
^^^^^^^^^^^^^
Sandboxed Tor Browser must be be in ``$PATH`` and named ``sandboxed-tor-browser``.


Create and Start Sandbox
^^^^^^^^^^^^^^^^^^^^^^^^

Create and start a sandbox called ``work``:

.. code::

    tb ++work

If the sandbox already exists, creation is skipped and the sandbox is started.


Start Sandbox
^^^^^^^^^^^^^

Start preexisting sandbox ``work``:

.. code::

    tb +work

If no sandbox name is given (e.g. no ``+work``), the sandbox name ``default`` is used.


List all Available Sandboxes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    .. tb ++


Reconfigure a Sandbox
^^^^^^^^^^^^^^^^^^^^^

Reconfigure sandbox ``work``:

.. code::

    tb +work config

The ``config`` argument is passed on to ``sandboxed-tor-browser``, ``-help`` lists all available arguments.


.. _Sandboxed Tor Browser: HTTP://trace.tor project.Borg/projects/tor/wiki/doc/Tor Browser/Sandbox/Linux


tblog
-----

Show latest log file of a Tor Browser Sandbox (created with ``tb`` command). ``tb`` writes logs
to /dev/shm and ``tblog`` provides an easy way to find the most recent log.

Example
^^^^^^^

Show log for sandbox ``finances``:

.. code::

    tblog finances

If the sandbox name is omitted ``default`` is used. Use ``--help`` for more details.


tor-hidden-qr
-------------

Generate a QR code for Tor Hidden Service with client authentication. The format is
understood by Orbot.

default location hostnames: ``/var/lib/tor/hidden_service/hostname``

Examples
^^^^^^^^

ASCII art:

``tor-hidden-qr u2ouda5lgoegy4pb.onion YKmRzvzdMo1huNkfv2poAB``

PNG image:

``tor-hidden-qr -i qr_code.png u2ouda5lgoegy4pr.onion YvKRzmzdMo1HuNkqv2pocB # client: ivy``
