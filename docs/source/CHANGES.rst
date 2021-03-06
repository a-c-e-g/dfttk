=========
Changelog
=========

0.3.1 (2021-02-03)
==================

(Contributor: @YiWang, @mxf469, @bocklund)

- Change List:
 - Made a significant online documentation using readthdocs
 - Documentation open online by www.dfttk.org

0.3.0 (2020-12-10)
==================

(Contributor: @YiWang, @mxf469, @bocklund)

- Change List:

 - formally release dfttk version 0.3.0
 - Revised dfttk/script/run_dfttk.py
 - made workflow ``get_wf_gibbs`` run on ``robust`` with ``get_wf_gibbs_robust`` 
 - changed test module from ``get_wf_gibbs`` into ``get_wf_gibbs_robust``
 - Add elasticity calculation model
 - Add Born effective charge calculations

September 17, 2020
==================

•       Bug fixes:
•       Replaced ``curve-fit`` by ``ployfit`` for BM fitting
•       Fixed bugs on result checks
•       Summarizing installation/run documents for DFTTK (This documents)

September 3, 2020
=================

•       Added a module ``EVfind`` per discussion with Shunli and enhanced calculation summary
•       E-V, P-V, Stress-V, Strain-V
•       Implemented 4 numerical schemes for evaluating LTC
•       Enhanced plots
•       LO-TO splitting were marked
•       Gamma point phonon frequencies
•       Prepared ~50 testing structures/compounds
•       Made LDA pseudopotential as an option
•       Speed up calculation
•       Turned on ``LREAL=Auto`` from default 
•       Change into ``ISPIN=1`` for nonmagnetic system from default
•       For better relaxation
•       Turned on ``EDIFF=1.e-8`` (why it showed 2e-7 in the OUTCAR?)
•       Turned on ``EdiffG=-1.e-3`` (testing, could be the reason for poor phonon data quality) 
•       Data report
•       Phonon quality
•       LTC quality
•       Found phonopy was unable handle Cv below 1 K 
•       Added experimental data for plotting results 
•       Working on
•       Calculate Born effective charge/dielectric tensors for insulators 
•       Launch by module ``EVfind`` when band gaps found and if not calculated

0.2.2 (2020-08-18)
==================

(Contributor: `@YiWang`_, `@mxf469`_)

- Change List:

 - added codes in the dfttk/scripts directory:

  - run_dfttk_ext.py

   - handle the argumetns for the thelec and thfind modules

 - added python code in the dfttk directory:

  - pyfind.py

   - database search engine

  - pythelec.py

   - for compatibiliy with Yphon
   - generating the majority of thermodynamic properties, such as thermal expansion coefficient, Seebech coefficients, Lorenz number etc

  - pyphon.py for

   - calculate the phonon contributions to the various thermodynamic properties

 - added python code in the dfttk/analysis directory:

  - database

   - for plot phonon dispersions for all crystalline systems

  - ywutils.py

   - general utils code

  - ywplot.py

   - for plots of ~20 different phonon and thermodynamic properties in the png format 

* made Yphon compatibile with phonopy

 - added codes in the CRO-soc directory:

   - phonopy2yphon, phonopy2yphon.py

    - convert the phonopy force constant matrix in hdf5 format into superfij.out format used by Yphon

 - changed codes:

  - in the dfttk/scripts directory:

   - run_dfttk.py

    - added the following lines aimed to handle the argumetns for the thelec and thfind modules

    # extension by Yi Wang, finalized on August 4, 2020
    # -----------------------------------
    from dfttk.scripts.run_dfttk_ext import run_ext_thelec
    run_ext_thelec(subparsers)

  - in the dfttk/analysis directory:

   - debye.py is renamed as debye_ext.py

    - to include the vibrational entropy (S_vib) and heat capacity (C_vib) into the "qha" MongoDB collection

   - quasiharmonic.py:

    - copy the S_vib and C_vib from the "phonon" collection into the "qha_phonon" MongoDB collection

0.2 (2020-03-30)
================

New features

(Contributor: `@bocklund`_ , @Peng_Gao, `@hitliaomq`_ )

* The relax scheme is optimized. (from ``ISIF=3`` to ``ISIF=2`` followed by ``ISIF=4``) (@Peng_Gao)
* Change the static workflow to dynamic workflow. (``EVcheck_QHA.py`` increase the data points atomately if the fitting of initial points is incorrect) (@Peng_Gao)
* Support run dfttk by command. (Add ``dfttk run [options]``) (`@hitliaomq`_)
* Support configrate dfttk automately. (Add ``dfttk config [options]``) (`@hitliaomq`_)
* Documents' enhance. (`@hitliaomq`_)
* Bug fix. (Including `#8`_ ) (`@bocklund`_, @Peng_Gao, `@hitliaomq`_)

.. _`#8`: https://github.com/PhasesResearchLab/dfttk/issues/8

0.1 (2018-08-28)
================

Initial release. Includes

(Contributor: `@bocklund`_, `@mxf469`_)

* Gibbs workflow for stable structures
* Analysis code and libraries for calculation quasiharmonic Gibbs energies with 0K, vibrational and thermal electronic contributions
* Useful utilities for interfacing with structure, calculations and the Materials Project

.. _`@bocklund`: https://github.com/bocklund
.. _`@mxf469`: https://github.com/mxf469
.. _`@hitliaomq`: https://github.com/hitliaomq
.. _`@YiWang`: https://github.com/yiwang62
