### AI-based PY coding for OC Processing Notes:  
#### Using OpenCode  

#### Tasks:  
1. Update level-3 mapped files using automated OPENDAP calls using PY
 - Code created: "/Users/imars_mbp2/Documents/Default Project/download_obdaac_l3m_8day.py"
 - This code can run for subsetted or full-res files
 - (default is subsetted, set "--full" flag for full files)
 - Example call:  
   python3 download_obdaac_l3m_8day.py --full \
  --start 2024-01-01 --end 2024-01-31 \
  --products chlor_a Rrs_443 adg_443 \
  --outdir "/Users/imars_mbp2/Documents/Default Project/obdaac_full"
   
 - For now (MBON meeting), use already downloaded files.
 - In the future, updates are best carried out using this new script (faster, less input needed)

 - For full global OC-CCI downloads (on Mac Mini):
 - Use "DL_oc_cci_chl.sh"
 - Or "DL_oc_cci_rrs.sh"
 - Or "DL_oc_cci_iop.sh"

 - New Method:
 - "download_cci_rrs_V2.sh" - Downloads only needed bands (chlor_a, adg_443, Rrs at 5 vis wavelengths)
 - Extracts OC-CCI data at regions defined in Excel sheet (need to specify)
 - Can set "full" tag to get global files, but these files are big
 - Not sure which is easiest; subsetted files are easier to move around

#### Next:
 - Ask OpenCode to create a py routine to compare time series of each variable.
 - Go one product at a time and create a plot of time series, differences
 - Ask OC for guidance; like the best way to compare outputs from different sensors



#### Future (for NRT dashboard files)
2. Use PY script(s) for full automated Level-2 OC processing for dashboards
 - Need to ask OpenCode for this after MBON meeting
 - Will need to call gpt, output L3 files, make 8D and MO composites at 1-km and create climatologies, calculate anoms
 - Then need to automate the whole thing w/chron
 - Will need to then move copy to ERDDAP server
 - SHould we run this locally or on the server?
