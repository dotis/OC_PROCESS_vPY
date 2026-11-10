#### Notes for downloads of global 4-km OC data

Code:"/Users/imars_mbp2/OC_Process/fetch_obdata.py"


Example calls (From AI agent):
cd /Users/imars_mbp2/OC_Process

#### monthly chlor-a, all of 2025  
python3 fetch_obdata.py --res MO  --start 202501 --end 202512 -p chlor_a --sensor aqua  

#### 8-day windows of a MODIS Rrs band overlapping June 2025 (dates as YYYYMM accepted too)  
python3 fetch_obdata.py --res 8D  --start 202506 --end 202506 -p Rrs_412 --sensor aqua  

##### several products in one call (suite inferred per product)  
python3 fetch_obdata.py --res MO --start 202503 --end 202505 \  
    -p chlor_a -p Rrs_443 -p adg_443 -p SST4 --sensor aqua  

#### PACE OCI (AOP/IOP/BGC suites)  
python3 fetch_obdata.py --res MO --start 202503 --end 202504 -p chlor_a --sensor pace --suite BGC  

#### inspect candidate file names without downloading  
python3 fetch_obdata.py --res 8D --start 2025-06-01 --end 2025-06-15 -p Rrs_412 --dry-run  


Design points worth knowing:
Suite inference from the field name: chlor_a → CHL, Rrs_xxx → RRS (→ AOP for PACE)  
adg_/aph_/bb_/kd_ → IOP, sst/SST4, PAR, PIC; --suite BGC etc. always overrides.  

Sensors: aqua | terra | snpp | n20 | n21 | pace with the OB.DAAC platform tokens  
(AQUA_MODIS, SNPP_VIIRS, JPSS1_VIIRS, PACE_OCI, …) and archive name variants tried in order.  

8-day windows are anchored to OB.DAAC's convention (Jan 1 + n·8 days each year, last window    
clipped to Dec 31); specifying month tokens automatically selects every window overlapping the month.  

Resilience: transient throttle/5xx responses are retried with backoff (prints the HTTP code it gave up on), 
404s are skipped as genuinely absent, per-thread sleeps keep the server happy,    
and everything reuses your existing ~/.netrc Earthdata login, skipping files already on disk.  

All time frames as well as products/suites are command-line arguments — nothing is hard-coded per run.  
