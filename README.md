
## Pitter: Python implementation of gitter

gitter is used for quantification of microbial colonies in plate images, originally written in R. 

pitter uses Python to to identify the colonies on the plate, as well as calculate areas and perform different statistical analysis. 

### Installation and Usage
Clone the repository
```
git clone https://github.com/BooneAndrewsLab/pitter.git
cd pitter
```

Install required packages
```
pip install -r requirements.txt
```

or if using the Anaconda Python distribution, create a new environment with the dependencies (recommended):
```
conda create --name pitter_env --file requirements.txt
source activate pitter_env
```

### Running pitter

To run pitter, input the path to an image file or folder and run the test file.
```
python test.py input_image.jpg
```

### Input Options
 
  **--plate-format** (-f): Plate format as colony count. Default is 1536
  
  **--remove-noise** (-n): Try removing noise from the image.
  
  **--auto-rotate**  (-r):  Fix image rotation.
  
  **--inverse**      (-i):  Work on inverse image.
  
  **--contrast**     (-c):  Adjust image contrast.
  
  **--rescale**      (-s):  Resize image before working on it. This speeds up the processing.  
 
  **--save-grid**    (-g):  Save gridded image. Helps with debugging.
  
  **--skip-dat**     (-d):  Skip saving dat file.
  
  **--walk-folders** (-w):  Recurse into subfolders.
                        
  **--ignore-errors** (-e): Ignore processing errors, continue processing next image.
  
  **--resume-processing** (-R): Resume processing, skip images with existing dat files.
                        
  **--colony-compat**     (-C):   Enable colony imager compatibility mode (header).
 
  **--template-plate**    (-t): Use this plate as the gridding reference for other plates.
                        
  **--detect-template**   (-l):  Automatically detect the last timepoint of each plate and use it as the template. If provided,
                        the script will ignore (-t) template-plate flag.
                       
  **--liquid-assay**      (-L): This is a timecourse liquid assay. Must be used in combination with -l. Use last timepoint to
                        detect the area of each colony and measure opacity instead of area.
                        
  **--local-illumination**  Calculate local illumination correction for liquid assays. Background intensity will be
                        calculated for each colony. Produces better quantification resolution, but takes much longer
                        to run. WiP WARNING there are still some problems with edge cases, ie: border colonies.
