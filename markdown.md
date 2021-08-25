# DVC
- Data version tool
- open source and extremely easy to integrate in a project
- It also interact perfectly with git , the combination of git/DVC is one of the most popular choice for version control 

## differnet popular ML production tools
- https://github.com/EthicalML/awesome-production-machine-learning

- DVC work by supplimenting each data file with a corresponding metadata file(.dvc) which is used to sync with a remote repo designed for large file (cloud storage)
- git tracks the meatdatafile wile DVC handle the remote repo.

- working with DVC 
- install the DVC
    - mamba install -c conda-forge dvc
    - install different storage dependencies
        - `pip install "dvc[all]"`

- make a empty dir
- A git project is init as a  DVC project 
    - git init 

- init a DVC - `dvc init`
- dvc get https://github.com/iterative/dataset-registry \
          get-started/data.xml -o data/data.xml

- Adding a data file to the dvc version control system moves the file to the local cache , letting the git to track only the corresponding .dvc file
    - dvc add data/data.xml

- storing and sharing
    - https://dvc.org/doc/command-reference/remote/add

- retrieving
    - remove the cache file and the data file
    - use the `dvc pull`

- making changes to the data file and pushing to the storage

- switching between the version 
    -  git checkout HEAD~1 data/data.xml.dvc
    - dvc checkout

# find a file or directory 

- dvc get
- dvc list
- dvc import

- for minio support
    -dvc remote add -d minio s3://test1
    - dvc remote modify minio endpointurl http://192.168.1.109:9001
    - dvcexport AWS_ACCESS_KEY_ID=minioadmin
    - export AWS_SECRET_ACCESS_KEY=minioadmin
    -   dvc push



