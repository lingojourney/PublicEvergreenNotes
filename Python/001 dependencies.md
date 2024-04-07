The Python equivalent of Maven is **pip** for installing packages and **pipenv** or **Poetry** for managing project dependencies and virtual environments. To specify libraries needed for your project, you can use a `requirements.txt` file with **pip**, or a `Pipfile` with **pipenv**, or a `pyproject.toml` file with **Poetry**.

Here's an example of what a `requirements.txt` file might look like:

```plaintext
matplotlib==3.3.4
numpy==1.20.1
pandas==1.2.2
```

You can generate this file by running `pip freeze > requirements.txt` in your environment, which will list all installed packages and their versions. When you want to install all the dependencies listed in `requirements.txt`, you can run:

```bash
pip install -r requirements.txt
```

For more complex dependency management, **pipenv** and **Poetry** provide additional features such as handling virtual environments and dependency resolution similar to Maven's. They use the `Pipfile` and `pyproject.toml` respectively to declare project dependencies.