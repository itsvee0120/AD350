# PySpark Setup Guide

Watch this video and follow along:

https://youtu.be/LeI4BPuWqCg

## Step 1: Download Required Software

Download the necessary files from the following link:

| Name | URL |
| --- | --- |
| Apache Spark | [[Downloads | Apache Spark](https://spark.apache.org/downloads.html)](https://spark.apache.org/downloads.html) |
| winutils.exe | [[winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-3.0.0/bin/winutils.exe)](https://github.com/steveloughran/winutils/blob/master/hadoop-3.0.0/bin/winutils.exe) |
| Anaconda | https://www.anaconda.com/download |

Ensure you download and extract the appropriate versions of Spark (3.5.4) and Hadoop (3.0.0).

---

## Step 2: Set Environment Variables

You need to set the following environment variables:

### **Environment Variables**

1. **HADOOP_HOME** → Set this to the path where Hadoop is installed. Example:
    
    ```
    C:\hadoop
    
    ```
    
2. **SPARK_HOME** → Set this to the path where Spark is installed. Example:
    
    ```
    C:\spark-3.5.4
    
    ```
    
3. **PYSPARK_DRIVER_PYTHON** → Set this to the Python interpreter you are using. Example:
    
    ```
    C:\Users\your_user\anaconda3\envs\pyspark-env-3\python.exe
    ```
    
4. **PYSPARK_PYTHON** → Set this to the Python interpreter inside your Anaconda environment. Example:
    
    ```
    C:\Users\your_user\anaconda3\envs\pyspark-env-3\python.exe
    
    ```
    

### **Path Variables**

Add the following directories to the `Path` system variable:

1. **%SPARK_HOME%\bin**
2. **%HADOOP_HOME%\bin**

### **How to Set Environment Variables on Windows:**

1. Open **System Properties** (Win + Pause → Advanced system settings).
2. Click on **Environment Variables**.
3. Under **System Variables**, click **New** or **Edit**.
4. Add or modify the variables as needed.
5. Click **OK** and restart your system.

---

## Step 3: Create and Configure Anaconda Environment

### **Check Available Environments**

Open **Anaconda Prompt** and run:

```
conda env list

```

### **Create a New Environment**

```
conda create -n pyspark-env-3 python=3.10

```

### **Activate the New Environment**

```
conda activate pyspark-env-3

```

---

## Step 4: Install Required Dependencies

Run the following commands in **Administrator PowerShell**:

```
pip install pyspark==3.5.4
pip install py4j==0.10.9.7

```

Then, install Jupyter in Anaconda Prompt:

```
conda install jupyter

```

Check if Jupyter kernels are installed:

```
jupyter kernel list

```

If needed, install the Jupyter kernel for this environment:

```
python -m ipykernel install --user --name=pyspark-env-3

```

**Debugging Tip:** If you face issues with Jupyter kernel, try:

```
pip install ipykernel

```

---

## Step 5: Verify Installation

To check if everything is set up correctly, activate the environment and start PySpark:

```
conda activate pyspark-env-3
pyspark

```

If you see the PySpark shell loading, the setup is successful.

---

## Step 6: Running PySpark with Jupyter Notebook

To use PySpark in Jupyter Notebook, run:

```
jupyter Lab

```

Create a new notebook and select the `pyspark-env-3` kernel.

Your PySpark environment is now ready to use!

---

## DEBUG

**Important:** You must use the following versions:

- **Java JDK 8**
- **Spark 3.5.4**
- **Py4J 0.10.9.7**
- **Python 3.10 when create environment for pyspark**
