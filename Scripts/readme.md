## R Scripts

This folder contains R scripts associated with the following publication: 

Kagawa-Viviani, A., N. Lincoln, S. Quintus, M. Lucas, and T. Giambelluca. 2018. Spatial patterns of seasonal crop production suggest coordination within and across dryland agricultural systems of Hawaiʻi Island. _Ecology and Society_ 23(3):20. https://doi.org/10.5751/ES-10369-230320.

Feel free to download and use the data and code in this repo for non-commerical purposes. If you publish analyses using our data or code, be sure to cite the paper above. Thank you!

## [FieldSystemCovariates_Polygons_GraphsFin.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/FieldSystemCovariates_Polygons_GraphsFin.R)
This script extracts values of gridded climate data for known locations and generates visualizations including Figures 2, 3, A2 in the manuscript.

## [FieldSystemCovariates_CombinedAnalysesFin.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/FieldSystemCovariates_CombinedAnalysesFin.R)
This script, associated with [FieldSystemCovariates_Polygons_GraphsFin.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/FieldSystemCovariates_Polygons_GraphsFin.R), 
1) generates rasters for seasonality metrics of aridity
2) explores intra-annual shifting of pre-defined "optimal" growing conditions
3) generates Figures 4, 7 in the manuscript

References: 
* Feng X, Porporato A, Rodriguez-Iturbe I (2013) Changes in rainfall seasonality in the tropics. Nature Clim Change 3:811-815. [doi: 10.1038/nclimate1907](https://www.nature.com/articles/nclimate1907)  
* Valenzuela, H., S. Fukuda, and A. Arakaki (1994) Sweetpotato Production Guides for Hawaii. Pages 1-10. Hawaii Institute of Tropical Agriculture and Human Resources. http://hdl.handle.net/10125/5497  

## Sensitivity analyses
The following two scripts are for a sensitivity analysis calculating percent area meeting various combinations of rainfall/aridity and air temp values. The code takes monthly rainfall (mm)/aridity & tair (C) rasters and reclasses multiple combinations of these two variables on a monthly basis to define a crop-able (cultivable) area, then combines all 12 months to calculate annual % of dry ag system that is crop-able (defined by pixels that are crop-able for >=1 month).
* [MPL_tair_rf_cond_loop_dryag_area_sensitivity.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_tair_rf_cond_loop_dryag_area_sensitivity.R)
* [MPL_tair_airdity_cond_loop_dryag_area_sensitivity.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_tair_airdity_cond_loop_dryag_area_sensitivity.R)
  
## [FieldSystemThresholding3.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/FieldSystemThresholding3.R)
This script relies on output (rf_tair_per_crop_FINAL_fine.csv, arid_tair_per_crop_FINAL_fine.csv) generated by MP Lucas with scripts [MPL_tair_rf_cond_loop_dryag_area_sensitivity.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_tair_rf_cond_loop_dryag_area_sensitivity.R) and [MPL_tair_airdity_cond_loop_dryag_area_sensitivity.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_tair_airdity_cond_loop_dryag_area_sensitivity.R) respectively.  It generates Plotly interactive graphs that we used to assess system "cultivability" based on temperature x rainfall or temperature x aridity combinations (Figures A3.1 and A3.2).  We used this to define a common threshold across the three systems for sake of visualizing the shifting seasonal envelope. Values selected (rainfall 90 mm/mo, temperature 18 C, and aridity 2.5) were then used to generate Figures 5, 6, and 7. See the following scripts for details:
* [MPL_monthly_suit_calc_and_plot_RF90_Temp18.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_monthly_suit_calc_and_plot_RF90_Temp18.R) for Figure 5,
* [MPL_monthly_suit_calc_and_plot_Arid2.5_Temp18.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/MPL_monthly_suit_calc_and_plot_Arid2.5_Temp18.R) for Figure 6, and
* [FieldSystemCovariates_CombinedAnalysesFin.R](https://github.com/akkagawa/DrylandAg/blob/master/Scripts/FieldSystemCovariates_CombinedAnalysesFin.R) for Figure 7.
