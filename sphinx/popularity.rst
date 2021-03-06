.. -*- mode: rst; fill-column: 78 -*-
.. ex: set sts=4 ts=4 sw=4 et tw=79:

.. _chap_popularity:

*********************
Popularity Statistics
*********************

Repository subscriptions
========================

Interactive visualization of new NeuroDebian repository subscriptions. Plotted
are each week's average number of daily subscriptions for all Debian and Ubuntu
releases. Statistics for individual releases can be compared by clicking on the
respective curves and labels in the legend.

Note that each machine only needs to be subscribed to the repository once, and
only subscriptions done via the website are counted.


.. raw:: html

  <link href="/_static/nv.d3.css" rel="stylesheet" type="text/css">
  <div><svg style="height:500px" id="subscriptionchart"></svg></div>

  <script src="/_static/d3.v2.min.js"></script>
  <script src="/_static/nv.d3.min.js"></script>
  <script src="/_static/subscriptionchart.js"></script>


Popularity Contest
==================

We encourage you to participate in the `popularity
contest <http://popcon.debian.org>`_ (popcon), which anonymously
collects the list of packages you installed/use on your system.
Collecting such statistics is of particular importance for research
software projects as a proof of existing user-base.

In addition to popcon stats for your "core" distribution (e.g. `Debian
<http://popcon.debian.org/>`__ or `Ubuntu
<http://popcon.ubuntu.com/>`__), an interactive plot below summarizes number
of submissions to NeuroDebian's popcon server.

.. raw:: html

  <div><svg style="height:500px" id="popconchart"></svg></div>

  <script src="/_static/popconchart.js"></script>

You can get more information about submissions from `NeuroDebian Popularity
Contest <http://neuro.debian.net/popcon/>`__ page.

If upon installation of the system you rejected the invitation to participate
you can always change your decision by running::

 sudo dpkg-reconfigure popularity-contest

.. note::

   If you are deploying multiple systems through cloning, to not have
   all systems considered as one, it would be necessary to re-generate
   the random MY_HOSTID.  Following commands ran as root should do it
   (as root) without any interactive dialog::

    sed -i -e 's,PARTICIPATE *= *.no.,PARTICIPATE="yes",g' -e '/^ *MY_HOSTID/d' /etc/popularity-contest.conf
    DEBIAN_FRONTEND=noninteractive dpkg-reconfigure popularity-contest


.. include:: link_names.txt
