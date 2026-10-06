### AI-based PY coding for OC Processing Notes:  
#### Using OpenCode  

#### Tasks:  
1. Update level-3 mapped files using automated OPENDAP calls using PY
 - Code created: "/Users/imars_mbp2/Documents/Default Project/download_obdaac_l3m_8day.py"
 - This code can run for subsetted or full-res files
 - For now (MBON meeting), use already downloaded files.
 - In the future, updates are best carried out using this new script (faster, less input needed)
 - Next:
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
