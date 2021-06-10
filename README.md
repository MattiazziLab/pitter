
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

