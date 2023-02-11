# ezconfig
This is a library that makes creating a configuration file easy.  

Steps to follw:
```python
# Import EzPackage
from ezconfig.config_manager import EzConfig

# Initialize EzConfig object
ezcfg = EzConfig(directory='your-desired-directory', filename='filename.json')

# Write a configuration file. If file already exists, replace=True
ezcfg.write_config_file(config_dict={"a":1})

# Read a configuration file. It's a good practice to use this method after writing, inserting, updating, deleting method.
ezcfg.read_config_file()

# Insert a new configuration. If a config already exists, replace=True
ezcfg.insert_config(config_dict={'b':[2,3,4]})

ezcfg.read_config_file()

# Update the existing configuration. Always replace=True
# Note: in the case when you want to update the nested configuration, use insert method with the whole nested config instead
ezcfg.update_config(key='a', value=5, replace=True)

ezcfg.read_config_file()

# Delete a configuration. Input delete config
ezcfg.delete_config(key='b')

# Delete the configuration file. Input permanently delete
ezcfg.delete_config_file()



```
