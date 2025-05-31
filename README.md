## Data Versioning with DVC

This project demonstrates the use of **Data Version Control (DVC)** to manage and track datasets in machine learning workflows. By integrating DVC into the MLOps pipeline, we ensure that our data files are versioned, reproducible, and consistent across different development environments.

### 🔍 What is DVC?

DVC is an open-source version control system designed to handle large data files, models, and machine learning pipelines. It works seamlessly with Git by storing lightweight metafiles (`.dvc` files) in the Git repository, while keeping the actual data files in a separate storage (local or remote). This approach keeps the Git repository clean and efficient.

### 📄 Purpose of `iris.csv.dvc`

The `iris.csv.dvc` file is a DVC metafile that tracks the `iris.csv` dataset used in this project. It contains metadata such as:

- The relative path to the dataset (`data/iris.csv`)
- A checksum (MD5 hash) that uniquely identifies the dataset's contents
- The size of the dataset

By tracking this metafile with Git, we can monitor changes to the dataset over time. If the dataset is modified, DVC will detect the change through the checksum and allow us to version the new state, facilitating easy rollbacks and comparisons.

### 🛠️ How DVC Tracks Data

Here's how DVC manages data versioning:

1. **Adding Data to DVC**:
   ```bash
   dvc add data/iris.csv

This command tells DVC to start tracking `data/iris.csv`. It creates a `data/iris.csv.dvc` file and adds `data/iris.csv` to `.gitignore`.

### Committing Changes to Git:

```bash
git add data/iris.csv.dvc .gitignore
git commit -m "Track iris.csv with DVC"

