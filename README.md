# dagster-playground
dagster playground






## Python Setup


```bash

pyenv install 3.11.2
pyenv virtualenv 3.11.2 dagster-playground
pyenv local dagster-playground


## confirm

pyenv local
python --version

pip install -e ".[dev]"

```

## Notes

used example project for initial setup

```bash
pip install dagster
dagster project from-example \
  --name dagster-playground \
  --example quickstart_etl
```


UI doesn't have any sort of authenication, so it's not really suitable for production use. and not sure they will add it. based on his [logic](https://github.com/dagster-io/dagster/issues/2219#issuecomment-1489873034)


Makes me really want [airflow  AIP-56](https://cwiki.apache.org/confluence/display/AIRFLOW/AIP-56+Extensible+user+management) in airflow 3.X.  


## Running Guide

[Guide from Dagster for Quickstart](guide.md)


## I get an error "ModuleNotFoundError: No module named '_ctypes'".

If you are using Linux, you are probably missing the `libffi-dev` package on your system. You need to install that package using your distribution's package manager and then re-install python.

I experienced this issue on Ubuntu 23.04.

```bash
sudo apt-get update
sudo apt-get install libffi-dev

## REinstall python
# Load the new libffi.so, as suggested here https://stackoverflow.com/questions/27022373/python3-importerror-no-module-named-ctypes-when-using-value-from-module-mul/48045929#48045929
sudo ldconfig

# re-install python # what ever version we list above.
pyenv install 3.X.X 


# remove the old virtualenv
pyenv virtualenv-delete dagster-playground
# list 
pyenv virtualenvs

# now create a new virtualenv from above
```





## Links

- [dagster.io](https://dagster.io/)
- [python-poetry.org](https://python-poetry.org/)
- [Deploying Dagster to Amazon Web Services](https://docs.dagster.io/deployment/guides/aws)
- [dagster open-core-business-model-dagster](https://dagster.io/blog/open-core-business-model-dagster)