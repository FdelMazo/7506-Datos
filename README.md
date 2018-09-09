# 7506 - Organización de Datos

Grupo 30: Datatouille

https://fdelmazo.github.io/7506-Datos/

---

El repo contiene dos hooks:

* Pre-commit hook: Cada vez que se hace git add de un notebook, se limpia su output. Hecho con [nbstripoout](https://github.com/kynan/nbstripout)

* Jupyter notebook save hook: Cada vez que se graba un notebook, se exporta su contenido a un .html para poder ser vistio desde el sitio web. Esto se consigue con el archivo [jupyter_notebook_config.py](jupyter_notebook_config.py). Idea sacada de: [Jupyter notebook best practices for data science](https://www.svds.com/jupyter-notebook-best-practices-for-data-science/)
