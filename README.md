# adhd200_athena_scripts
Scripts that implement The Athena Pipeline for the ADHD-200 preprocessed initiative.

## Prerequisites

These scripts require that AFNI and FSL be installed.

## Usage

This script expects that the data is organized in the file structure that the 
data is distributed in by INDI. The scripts are then run with:

    ./preproc.sh SUBJECT_DIR

There is a different script for each site, the differences between the scripts
are the configuration parameters at the top of the scripts. These are:

	TEMPLATE_1mm=/home/drcc/ADHD200/templates/nihpd_asym_04.5-18.5_t1w.nii
	TEMPLATE_2mm=/home/drcc/ADHD200/templates/nihpd_asym_04.5-18.5_t1w_2mm_ss.nii
	TEMPLATE_4mm=/home/drcc/ADHD200/templates/nihpd_asym_04.5-18.5_t1w_4mm.nii
	TEMPLATE_CFG=/home/drcc/ADHD200/templates/T1_2_NIHPD_2mm.cnf
	PNAS_TEMPLATES=/home/drcc/ADHD200/templates/PNAS_Smith09_rsn10_nihpd_4mm.nii.gz
	TR=2.5
	MIDSLICE=24
	ACQ=seqplus

The various templates correspond to the templates that are used to spatially 
normalize the data into MNI space and the RSNs used in dual regression. The 
next parameters are determined by the acquisition and include the sampling rate (TR),
the number of the middle slice (num slices/2) and the order in which the slices were
acquired. Please see the AFNI documentation for 3dTshift for information on the slice 
acquisitions.

These are old scripts that have been replaced by the [Configurable Pipeline for the 
Analysis of Connectoms (C-PAC)](http://fcp-indi.github.io/).
