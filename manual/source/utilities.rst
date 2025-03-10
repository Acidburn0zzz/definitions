.. _Utilities:

===============
NeXus Utilities
===============

There are many utilities available to read, browse, write, and use NeXus data files. Some
are provided by the NeXus technical group while others are provided by the community. Still,
other tools listed here can read or write one of the low-level file formats used by NeXus (HDF4,
HDF5, or XML).

..  see: http://www.nexusformat.org/Utilities

..  =============================
    section: Utilities from NeXus
    =============================

.. _Utilities-NeXus:

Utilities supplied with NeXus
#############################

Most of these utility programs are run from the command line. It will be noted if a
program provides a graphical user interface (GUI). Short descriptions are provided here with
links to further information, as available.

.. index:: 
	utility, NeXus; nxbrowse
	nxbrowse

**nxbrowse**
    NeXus Browser

.. index:: 
	utility, NeXus; nxconvert
	nxconvert

**nxconvert**
    Utility to convert a NeXus file into HDF4/HDF5/XML/...

.. index:: 
	utility, NeXus; nxdir
	nxdir

**nxdir**
    ``nxdir`` is a utility for querying 
    a NeXus file about its contents. Full
    documentation can be found by running this command:
    
    .. code-block:: c
    
        nxdir -h

.. index:: 
	utility, NeXus; nxingest
	nxingest

**nxingest**
    ``nxingest`` extracts the metadata from a NeXus file to create an
	XML file according to a mapping file.  The mapping file defines the structure 
	:index:`(names and hierarchy) <hierarchy>` and content (from either the 
	NeXus file, the mapping file or the current time) of the output file. See
	the man page for a description of the mapping file.  This tool uses the  
	:index:`NAPI`.  Thus, any of the supported formats (HDF4, HDF5 and XML)
	can be read.

.. index:: 
	utility, NeXus; nxsummary
	nxsummary

**nxsummary**
    Use ``nxsummary`` to generate summary of a NeXus file.
    This program relies heavily on a configuration file. Each ``item`` tag
    in the file describes a node to print from the NeXus file. The ``path``
    attribute describes where in the NeXus file to get information from. The
    ``label`` attribute will be printed when showing the value of the
    specified field. The optional ``operation`` attribute provides for certain
    operations to be performed on the data before printing out the result.
    See the source code documentation for more details.

.. index:: 
	utility, NeXus; nxtranslate
	nxtranslate

**nxtranslate**
    ``nxtranslate`` is
    an anything to NeXus converter. This is accomplished by
    using translation files and a plugin style of architecture where
    ``nxtranslate`` can read from new formats as plugins become available. The
    documentation for ``nxtranslate`` describes its usage by three types of
    individuals:
    
    + the person using existing translation files to create NeXus files
    + the person creating translation files
    + the person writing new *retrievers*
    
    All of these concepts are discussed in detail in the documentation
    provided with the source code.

.. index:: 
	utility, NeXus; nxvalidate
	nxvalidate

**nxvalidate**
    From the source code documentation: 
    
    	"Utility to convert a NeXus file into HDF4/HDF5/XML/..." 
    
    Note: this command-line tool is
    different than the newer Java GUI program: ``NXvalidate``.

.. index:: 
	utility, NeXus; NXvalidate
	NXvalidate
	
.. _NXvalidate-java:

**NXvalidate**
    Java program (in development in 2010) to check
    any NeXus data file for conformance with the NeXus
    NXDL-based standard. Note: This Java GUI is different than the command-line
    tool: ``nxvalidate``.


.. index:: 
	utility, NeXus; NXplot
	NXplot
	NeXus basic motivation; default plot

**NXplot**
    An extendable utility for plotting any NeXus file.  ``NXplot`` is
    an Eclipse-based GUI project in Java to plot data in NeXus files. (The project was
    started at the first NeXus Code Camp in 2009.)

.. _Utilities-DataAnalysis:

Data Analysis
#############

The list of applications below are some of the utilities that have been developed (or modified) to read/write NeXus files
as a data format.  It is not intended to be a complete list of all available packages.

.. index:: 
	utility; DAVE
	DAVE

**DAVE** (http://www.ncnr.nist.gov/dave/)
    DAVE is an integrated environment for the reduction, visualization and
    analysis of inelastic neutron scattering data. It is built using IDL (Interactive Data
    Language) from ITT Visual Information Solutions.

.. index:: 
	utility; GDA
	GDA

**GDA** (http://www.opengda.org)
    The GDA project is an open-source framework for creating customised 
    data acquisition and analysis software for science facilities such 
    as neutron and X-ray sources.

.. index:: 
	utility; Gumtree
	Gumtree

**Gumtree** (http://docs.codehaus.org/display/GUMTREE)
    Gumtree  is an open source project, providing a graphical user 
    interface for instrument status and control, data acquisition 
    and data reduction.

.. index:: 
	utility; ISAW
	ISAW

**ISAW** (ftp://ftp.sns.gov/ISAW/)
    The Integrated Spectral Analysis Workbench software project (ISAW) 
    is a Platform-Independent system Data Reduction/Visualization.
    ISAW can be used to read, manipulate, view, and save neutron 
    scattering data. It reads data from IPNS run files or NeXus files
    and can merge and sort data from separate measurements.

.. index:: 
	utility; LAMP
	LAMP

**LAMP** (http://www.ill.eu/data_treat/lamp/>)
    LAMP (Large Array Manipulation Program)  is designed for the treatment of 
    data obtained from neutron scattering experiments at the Institut Laue-Langevin. However,
    LAMP is now a more general purpose application which can be seen as 
    a GUI-laboratory for data analysis based on the IDL language.

.. index:: 
	utility; Mantid
	Mantid

**Mantid** (http://www.mantidproject.org/)
    The Mantid project 
    provides a platform that supports high-performance
    computing on neutron and muon data.  It is being developed as a collaboration between
    Rutherford Appleton Laboratory and Oak Ridge National Laboratory.

.. index:: 
	utility; NeXpy
	NeXpy

**NeXpy** (http://nexpy.github.io/nexpy/)
    The goal of NeXpy is to provide a simple graphical environment,
    coupled with Python scripting capabilities, for the analysis of X-Ray and
    neutron scattering data.
    (It was decided at the NIAC 2010 meeting that a large portion of this code
    would be adopted in the future by NeXus and be part of the distribution)

.. index:: 
	utility; OpenGENIE
	OpenGENIE

**OpenGENIE** (http://www.opengenie.org/)
    A general purpose data analysis and visualisation package primarily
    developed at the ISIS Facility, Rutherford Appleton Laboratory.

.. index:: 
	utility; PyMCA
	PyMCA

**PyMCA** (http://pymca.sourceforge.net/)
    PyMca is a ready-to-use, and in many aspects state-of-the-art, 
    set of applications implementing most of the needs
    of X-ray fluorescence data analysis.  It also provides a 
    Python toolkit for visualization and analysis of energy-dispersive
    X-ray fluorescence data.  
    Reads, browses, and plots data from NeXus HDF5 files.

.. _HDF-Tools:

HDF Tools
#########

Here are some of the generic tools that are available to work with HDF files.  
In addition to the software listed here there are also
APIs for many programming languages that will allow 
low level programmatic access to the data structures.

.. index:: 
	HDF tools; HDF Group command line tools
	HDF Group command line tools

**HDF Group command line tools** (http://www.hdfgroup.org/products/hdf5_tools/#h5dist/)
    There are various command line tools that are available from the HDF
    Group, these are usually shipped with the HDF5 kits but are also available for
    download separately.

.. index:: 
	HDF tools; HDFexplorer
	HDFexplorer

**HDFexplorer** (http://www.space-research.org/)
    A data visualization program that reads Hierarchical Data Format 
    files (HDF, HDF-EOS and HDF5) and also netCDF data files.

.. index:: 
	HDF tools; HDFview
	HDFview

**HDFview** (http://www.hdfgroup.org)
    A Java based GUI for browsing (and some basic plotting) of HDF files.

.. index:: 
	HDF tools; IDL
	IDL

**IDL** (http://www.ittvis.com/)
    IDL is a high-level technical computing language and interactive 
    environment for algorithm development, data visualization, 
    data analysis, and numeric computation.

.. index:: 
	HDF tools; IGOR Pro
	IGOR Pro

**IgorPro** (http://www.wavemetrics.com/)
    IGOR Pro is an extraordinarily powerful and extensible scientific 
    graphing, data analysis, image processing and programming software 
    tool for scientists and engineers.

.. index:: 
	HDF tools; MATLAB
	MATLAB

**MATLAB** (http://www.mathworks.com/)
    MATLAB is a high-level technical computing language and interactive 
    environment for algorithm development, data visualization, 
    data analysis, and numeric computation.

Language APIs
-------------

:h5py:
	(http://code.google.com/p/h5py/)
	HDF5 for Python (h5py) is a general-purpose Python interface to HDF5.

.. TODO: list more APIs
