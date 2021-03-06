﻿=============
Bus
=============

.. seealso::
    :ref:`Unit Systems and Conventions <conventions>`

Create Function
=====================

.. _create_bus:

.. autofunction:: pandapower.create_bus

Input Parameters
=========================

*net.bus*

.. tabularcolumns:: |p{0.12\linewidth}|p{0.10\linewidth}|p{0.25\linewidth}|p{0.30\linewidth}|
.. csv-table:: 
   :file: bus_par.csv
   :delim: ;
   :widths: 10, 10, 25, 40

.. |br| raw:: html

   <br />
   
\*necessary for executing a power flow calculation |br| \*\*optimal power flow parameter

.. note:: Bus voltage limits can not be set for slack buses and will be ignored by the optimal power flow.

*net.bus_geodata*

.. tabularcolumns:: |p{0.10\linewidth}|p{0.10\linewidth}|p{0.30\linewidth}|
.. csv-table:: 
   :file: bus_geo.csv
   :delim: ;
   :widths: 10, 10, 30
 
   
Electric Model
=================

.. image:: bus.png
    :width: 10em
    :alt: alternate Text
    :align: center
    

Result Parameters
=========================

*net.res_bus*

.. tabularcolumns:: |p{0.10\linewidth}|p{0.10\linewidth}|p{0.40\linewidth}|
.. csv-table:: 
   :file: bus_res.csv
   :delim: ;
   :widths: 10, 10, 40
    
The power flow bus results are defined as:

.. math::
   :nowrap:
   
   \begin{align*}
    vm\_pu &= \lvert \underline{V}_{bus} \rvert \\
    va\_degree &= \angle \underline{V}_{bus} \\
    p\_kw &= Re(\sum_{n=1}^N  \underline{S}_{bus, n}) \\
    q\_kvar &= Im(\sum_{n=1}^N  \underline{S}_{bus, n}) 
   \end{align*}


*net.res_bus_est*

The state estimation results are put into *net.res_bus_est* with the same definition as in *net.res_bus*.

.. tabularcolumns:: |p{0.10\linewidth}|p{0.10\linewidth}|p{0.40\linewidth}|
.. csv-table:: 
   :file: bus_res.csv
   :delim: ;
   :widths: 10, 10, 40
    

.. note::

   All power values are given in the consumer system. Therefore a bus with positive p_kw value consumes power while a bus with negative active power supplies power.