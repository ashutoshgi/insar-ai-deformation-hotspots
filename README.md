# insar_deformation_hotspots
Detecting deformation hotspots from InSAR derived deformation maps
This module gives a semi-supervised machine learning based information mining approach to detect deformation hotspots from InSAR derived displacement maps.

The set of programs can be used for post-processing InSAR deformation maps obtained from multi-temporal InSAR processing.

Related paper citation:
Tiwari, Ashutosh; Shirzaei, Manoochehr (2024). A novel machine learning and deep learning semi-supervised approach for automatic detection of InSAR-based deformation hotspots, International Journal of Applied Earth Observation and Geoinformation Volume 126, DOI: [10.1016/j.jag.2023.103611]

insar_deformation_hotspots-main
	Programs
		p01_time_series_unsupervised_clustering_rts.py: This program perform time series clustering for InSAR time series displacement using time series k-means algorithm
		p02_Individual_cluster_dbscan_clustering.py: This program performs spatial clustering over individual temporal clusters detected using p01.
		p03a_LSTM_supervised_classification_dbscan_out.py: Program for supervised classification using LSTM networks with clusters generated from results of p02 acting as training labels.
		p03b_LSTMP_supervised_classification_dbscan_out.py: Program for supervised classification using LSTM and perceptron networks with clusters generated from results of p02 acting as 			training labels.
		p03_plot_dbscan_clusters.m: A program for plotting the resulting clusters from p02.
		p04_finding_spatial_correlation_lengths.m: Finding spatial correlation lengths for displacement in the study area, to find out a threshold for removing widespread unwanted clusters.
		p05_spatial_dispersion.m: Finding spatial dispersion of individual clusters generated from p02. Those with large dispersions would be removed.
	
  LICENSE: the license appended to this software
	README.md: guidance on how to use this software
	requirements.txt: requirements to run this software

 # Dataset explanation
 Datasets can be downloaded from https://data.lib.vt.edu/articles/software/Detecting_deformation_hotspots_from_InSAR_derived_deformation_maps/25402327
 
	elpx_ll.mat: Coordinates for elite pixels
	MVel.mat: One dimensional line of sight velocities
	MVelq.mat: Standard deviation for line of sight velocities
	Pco_m.mat: Mean coherence
	R_TS_den.mat: Displacement time series

 # Funding
NSF and USGS have provided funding for this work. Authors thank Department of Energy for supporting this study.
