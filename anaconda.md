# Anaconda Environments

Export to **YML**:

```bash
conda env export > dataPy.yml
```

Add to the kernels list:

```bash
source activate dataPy
python -m ipykernel install --user --name dataPy
```

Create environment from **YML**:

```bash
conda env create -f environment.yml
```

List environments:

```bash
conda list
```

Uninstall environment:

```bash
conda env remove -n dataPy
```

List environments:

```bash
conda info --envs
```
