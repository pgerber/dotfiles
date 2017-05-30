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
