.. index:: ! FAQ

.. _FAQ:

==========================
Frequently Asked Questions
==========================

This is a list of commonly asked questions concerning the NeXus data format.

#. Is it Nexus, NeXus or NeXuS?

    NeXus is correct. It is a format for data from **Neutron** and **X-ray** 
    facilities, hence those first letters are capitalised. The format is also 
    used for muon experiments, but there is no *mu* (or m) in NeXus and no s 
    in muon. So the s stays in lower case. 

#. How many facilities use NeXus?

    This is not easy to say, not all facilities using NeXus actively
    participate in the committee. Some facilities have reported their
    adoption status on the `Facilities Wiki page <http://wiki.nexusformat.org/Facilities>`_.
    Please have a look at this list. Keep in mind that it is not
    complete.

#. NeXus files are binary? This is crazy! How am I supposed to see my data?

    NeXus files are not per se binary. If you use the XML backend the
    data are stored in a relatively human readable form (see
    `this example <http://trac.nexusformat.org/definitions/browser/exampledata/code/xml/NXtest.xml.txt>`_).
    This backend however is only recommended for very small data sets. With
    the multidimensional data that is routinely recorded on many modern
    instruments it is very difficult anyway to retrieve useful
    information on a VT100 terminal. If you want to try, for example
    ``nxbrowse``
    is a utility provided by the NeXus community that can be very
    helpful to those who want to inspect their files and avoid
    graphical applications. For larger data volumes the binary backends
    used with the appropriate tools are by far superior in terms of
    efficiency and speed and most users happily accept that after having
    worked with supersized "human readable" files for a while.

#. What on-disk file format should I choose for my data?

    HDF5 is the default file container to use for NeXus data. It
    is the recommended format for all applications. HDF4 is still
    supported as a on disk format for NeXus but for new installations
    preference should be given to HDF5. The XML backend is available
    for special use cases. Choose this option with care considering the
    space and speed implications.

#. Why are the NeXus classes so complicated? I'll never store all that information

    The NeXus classes are essentially glossaries of terms. If you
    need to store a piece of information, consult the class definitions
    to see if it has been defined. If so, use it. It is not compulsory
    to include every item that has been defined in the base class if it
    is not relevant to your experiment. On the other hand, a NeXus
    application definition lists a smaller set of compulsory items that
    should allow other researchers or software to analyze your data.
    You should really follow the application definition that
    corresponds to your experiment to take full advantage of NeXus.

#. I don't like NeXus. It seems much faster and simpler to develop my own file format. Why should I even consider NeXus?

    If you consider using an efficient on disk storage format,
    HDF5 is a better choice than most others. It is fast and efficient
    and well supported in all mainstream programming languages and a
    fair share of popular analysis packages. The format is so widely
    used and backed by a big organisation that it will continue to be
    supported for the foreseeable future.
    So if you are going to use HDF5 anyway, why not use the NeXus
    definition to lay out the data in a standardised way? The NeXus
    community spent years trying to get the standard right and
    while you will not agree with every single choice they made in the
    past, you should be able to store the data you have in a quite
    reasonable way. If you do not comply with NeXus, chances are most
    people will perceive your format as different but not necessarily
    better than NeXus by any large measure. So it may not be worth the
    effort. Seriously.

    If you encounter any problems because the classes are not
    sufficient to describe your configuration, please contact the :index:`NIAC`
    Executive Secretary explaining the problem, and post a suggestion
    at the relevant class wiki page. Or raise the problem in one of the
    `mailing lists <http://download.nexusformat.org/doc/html/MailingLists.html>`_.
    The NIAC is always willing to consider new proposals.

#. I want to produce an application definition. How do I go about it?

    Read the :index:`NXDL` Tutorial in :ref:`NXDL_Tutorial-CreatingNxdlSpec`
    and have a try. You can ask for help on the `mailing lists <http://download.nexusformat.org/doc/html/MailingLists.html>`_.
    Once you have a definition that is working well for at least your case,
    you can submit it to the NIAC for acceptance as a standard.
    The procedures for acceptance are defined in the NIAC :index:`constitution`. [#]_
        

	.. [#]
	    Refer to the most recent version of the NIAC constitution on the
	    NIAC wiki:
	    http://wiki.nexusformat.org/NIAC#Constitution


#. What is the purpose of ``NXdata``?

    ``NXdata`` contains links to the data stored elsewhere in the ``NXentry``. 
    It identifies the :index:`default plottable data <NeXus basic motivation; default plot>`. 
    This is one of the basic motivations (see :ref:`SimplePlotting`) for the NeXus standard. 
    The choice of the name ``NXdata`` is historic and does not really reflect its function.

#. How do I identify the plottable data?

    See the section: :ref:`Find-Plottable-Data`.

#. How can I specify reasonable axes for my data?

    ..  Is there a better answer for this?
    	FIXME: This link leads to the naming rules, not axes specification.  Change it.

    See the section: :ref:`multi-dimensional-data`.
    
    .. :ref:`DataRules`.

#. Why aren't ``NXsample`` and ``NXmonitor`` groups stored in the ``NXinstrument`` group?

    A NeXus file can contain a number of ``NXentry``
    groups, which may represent different scans in an experiment, or
    sample and calibration runs, etc. In many cases, though by no means
    all, the instrument has the same configuration so that it would be
    possible to save space by storing the  ``NXinstrument``
    group once and using multiple links in the remaining ``NXentry``
    groups. It is assumed that the sample and monitor information would
    be more likely to change from run to run, and so should be stored
    at the top level.

#. Specifications are complicated and often provide too much information for what I need.  Where can I find some good example data files?

    There are a few checked into the
    `definitions repository <http://trac.nexusformat.org/definitions/browser/exampledata>`_.
    At the moment the selection is quite limited and not very representative.
    This repository will be edited as more example files become available.


#. Can I use a NXDL specification to parse a NeXus data file?

    This should be possible as there is nothing in the NeXus
    specifications to prevent this but it is not implemented in :index:`NAPI`.
    You would need to implement it for yourself. You would be wise to
    consult the algorithms in the Java version of
    ``NXvalidate``
    (see the :ref:`Java-version of NXvalidate <NXvalidate-java>`) for more details.

#. Why do I need to specify the ``NAPItype``? My programming language does not need that information and I don't care about C and colleagues.  Can I leave it out?

    ``NAPItype`` is necessary. When implementing the NeXus-XML API we strived to
    make this as general as HDF and reasonably efficient for medium
    sized datasets. This is why we store arrays as a large bunch of
    numbers in C-storage order. And we need the  ``NAPItype``
    to figure out the :index:`dimensions <dimension; data set>` of the dataset.

#. Do I have to use the ``NAPI`` subroutines?  Can't I read (or write) the NeXus data files with my own routines?

    You are not required to use the NAPI to write valid NeXus
    data files. It is possible to avoid the NAPI to write and read
    valid NeXus data files. But, the programmer who chooses this path
    must have more understanding of how the NeXus HDF or XML data file
    is written. Validation of data files written without the NAPI is
    strongly encouraged.


#. I'm using links to place data in two places. Which one should be the data and which one is the link?
    
    .. index:: link
    
    .. note:: NeXus uses HDF5 hard links
    
	    In HDF, a hard link points to a data object.
	    A soft link points to a directory entry.
	    Since NeXus uses hard links, there is no need to distinguish
	    between two (or more) directory entries that point to the same data.
    
    Both places have pointers to the actual data.
    That is the way hard links work in HDF5.
    There is no need for a preference to either location.
    NeXus defines a ``target`` attribute to label
    one directory entry as the source of the data (in this, the
    link *target*).  This has value in
    only a few situations such as when
    converting the data from one format to another.  By identifying
    the original in place, duplicate copies of the data are not
    converted.

#. If I write my data according to the current specification for :ref:`NXsas` 
    (substitute any other application definition),  
    will other software be able to read my data?

    Yes.  :ref:`NXsas`, like other
    :ref:`application.definitions`,
    defines and names the *minimum information*
    required for analysis or data processing.  As long as all the
    information required by the specification is present, analysis software
    should be able to process the data.
    If other information is also present, there is no guarantee that
    small-angle scattering analysis software will notice.

#. Where do I store the wavelength of my experiment?

    See the :ref:`Strategies-wavelength` section.

#. Where do I store metadata about my experiment?

   See the :ref:`where.to.store.metadata` section.

