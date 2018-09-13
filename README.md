# 7506 - Organización de Datos

Grupo 30: Datatouille

https://fdelmazo.github.io/7506-Datos/

---

Es muy importante configurar el pre-commit hook del repo para que cada vez que se haga git add de un notebook, se limpie su output. Hecho con [nbstripoout](https://github.com/kynan/nbstripout). 

```shell
// Desde el root del repo
conda install -c conda-forge nbstripout
nbstripout --install
```

Por otro lado, cada vez que se graba un notebook se exporta su contenido a un .html para poder ser visto desde el sitio web. Esto se consigue con el archivo [jupyter_notebook_config.py](jupyter_notebook_config.py). Idea sacada de: [Jupyter notebook best practices for data science](https://www.svds.com/jupyter-notebook-best-practices-for-data-science/)
