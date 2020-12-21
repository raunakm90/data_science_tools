# Install Miniconda
Miniconda is a python distribution that is a popular option amongst data scientists who want a minimal installtion of conda.

To install miniconda in windows, please download the installer from [here](https://docs.conda.io/en/latest/miniconda.html).

To install WSL2 or any other linux distro, follow the instructions below -

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

bash Miniconda3-latest-Linux-x86_64.sh
```

Manually add conda location to `$PATH`. Add the following at the end of `~/.bashrc` file.

```bash
export PATH=/home/kauff/anaconda3/bin:$PATH
```
# Environment description

Using `conda` to manage environments, create a data science environment by adding/updating `environment.yml` file. Run the following command in the same location as the `environment.yml` file to create a new environment.

> If no version is specified for a given package, it will install the latest version available on the provided channels.

The file in this repository is set up to install the latest packages at first. After the first install, the `.yml` file will be updated the version numbers to manage project dependencies.

To create `environment.yml`, run the following command line code
```bash
touch environment.yml
code environment.yml
```
Once the file is created and updated according to the users preferences, run the following command to create (install all dependencies) and activate the enviroment.

```bash
conda env create
conda activate datascience
```

## Conda environment - frequently used commands

`conda` can be used to export an existing enviroment dependencies and generate a yaml file.

```bash
cond env export > environment.yml
```

Other frequently used commands -

```bash
# list all the conda environment available
conda info --envs
# Create new environment named as `envname`
conda create --name envname
# Remove environment and its dependencies
conda remove --name envname --all
# Clone an existing environment
conda create --name clone_envname --clone envname
```