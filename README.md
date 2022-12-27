# Zipndel

Zipndel is a lightweight python package equipped with two main functionalities; **Zipndel** or **Unzipndel**

## A - Creation
The **Zipndel** class provides automatic functionality for zipping and password-protecting a pandas DataFrame, and then deleting the original file.
1. First takes the name of a pandas DataFrame given by the user as input with default name df, and writes the DataFrame into any Pandas supported file format given by the user with if applicable index=False, with csv file as default file_format and df as default file_name I.e. df.to_csv('df.csv', index=False) where ‘file_name.file_format’ is default set’ to df.csv' 
2. Second, compresses the same ‘file_name.file_format’ to a password protected zip file ‘file_name.zip’ default as ‘df.zip’ (f"{self.df}.zip")
3. Lastly, deletes the file_name created in in step 1 is safely secured in a password protected zip file in step 2

## Extraction
The **Unzipndel** class provides automatic functionality for unzipping and reading a password-protected zip file containing a pandas DataFrame, and then deleting the extracted file.
1. First, unzips the password protected zip file created in the first function or class and extracts the file_name
2. Second, reads the file_name into a DataFrame default called df.csv
3. Lastly, deletes the extracted file_name now that the file_name is stored in a DataFrame and a backup of the same file_name is kept in the zip file

# Installation & Example Usage
`pip install zipndel`

## Example usage A: Creation
```df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]}) # dummy df```
```Zipndel().zipit(df) # Create and remember password```

## Example usage B: Extraction
```df = Unzipndel().unzipit() # Provide the password created in A``` 


# Directory tree
```
├── README.rst
├── poetry.lock
├── pyproject.toml
├── src
│   └── zipndel
│       ├── __init__.py
│       └── zipndel.py
└── tests
    ├── __init__.py
    └── test_zipndel.py
```  
