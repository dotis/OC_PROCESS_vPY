#### Prompts for py version of OC processing for IMaRS


#### Prompt #1
1. I want to set up a complex processing scheme for NASA ocean color and SST data from a suite of sensors.
2. We will download Level-2 ocean color files for two regions (GOM and SEUS). We can get data using NASA's CMR. Let's start with MODIS-Aqua, but keep in mind we will be using other sensors.
3. For MODIS-Aqua, we will want the Level-2 satellite overpass files.
4. % Define Bounding box (define one for each AOI)
% florida
bbox=([-89,24,-79.0,31]);
% gom
bbox=([-98,18,-78.5,31]);
% seus
bbox=([-82,29,-73,40.5]);
% safr
bbox=([15,-36, 35, -29]);

Output files should go here for now [example for modis aqua (moda for short) in the gom]:
/srv/pgs/rois2/gom/L2_moda/  

For now, let's use June 2025 as a test. All L2 files should go in one directory.   
You'll see the files from the existing processing scheme around this directory.  
However, ignore for now. I want to start fresh.

So, the first step is to simply develop code to access the CMR and fetch needed L2 files for the gom. Just do that for now and then we'll proceed.
