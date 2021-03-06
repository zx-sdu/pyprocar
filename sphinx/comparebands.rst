.. _labelbandscompare:

Compare bands
=============

This module is useful to compare bands from different materials on the same band structure plot. The bands are plotted for the same :math:`k`-path in order to have a meaningful comparison but they do not need to have the same number of :math:`k`-points in each interval.
This makes use of the PyProcar ``exportplt`` feature. Any number of different modes of plots can be plot on the same figure with this function.  

Usage::

    import pyprocar
    import matplotlib.pyplot as plot

    plot.figure(figsize=(13,9)) #This is just to get better resolution. Not needed.

    plot = pyprocar.bandsplot(mode='parametric',elimit=[-5,5],code='elk',exportplt=True,orbitals=[4,5,6,7,8],vmin=0,vmax=1)
    plot = pyprocar.bandsplot('PROCAR1',kpointsfile='KPOINTS1',outcar='OUTCAR1',mode='plain',elimit=[-5,5],code='vasp',exportplt=True,color='k')
    plot.show()

The above command plots the figure displayed below. The black bands are plain bands of :math:`SrVO_3` calculated from VASP and the jet colormap is d orbital projected bands of the same material calculated from Elk.

.. image:: ElkvsVASP.png    
