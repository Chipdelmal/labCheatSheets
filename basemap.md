# Basemap

For basemap to work correctly in MoNeT, it needs to be installed as follows:

```bash
conda install -c anaconda basemap
conda install -c conda-forge basemap-data-hires 
```

Matplotlib has to be installed in version 3.1 or 3.2:

```bash
pip install matplotlib==3.2
```

And, finally, to deactivate the 'dedent' warning:

```python
import warnings
warnings.filterwarnings("ignore", category=UserWarning)
```

Additionally, for non *UTF-8* map regions, all the `utf-8` matches have to be replaced with `latin-1` found in the file:

```bash
~/miniconda3/envs/ENV_NAME/lib/pythonVER/site-packages/shapefile.py
```
