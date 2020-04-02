# PiToDB
Python script for sending data from Pi to Realtime Firebase


Add to project and import

```python
from PiToDB import *
```
## Create database reference
Set up a reference to database. This must be done only once.

```python
ref = GetDbRef(keyLoc, dbURL)
```
This creates a reference to the database with url ```dbURL```. You will need a service account for the database, then use the key with the location (either relative or absolute) of the key ```keyLoc```  to access the database.

## Push to database

To push to database, just use the command

```python
PushDB(dbRef, data)
```
Where ```dbRef``` is the database reference you created earlier, and ```data``` is data in a dictionary form, withot a timestamp.

### Data dictionary example

```json
{
    "birds": 38,
    "temperature": -18,
    "wind": 19,
}
```
This cant be created by using the ```dict``` function.
```python
data = dict(
    birds = 38,
    temperature= -18,
    wind = 19,
)
```
which will produce the above dictionary. 

## Simple example

This example will push a simple data dictonary to a database

```python
from PiToDB import *

# Get reference
ref = GetDbRef("some_location", "some_url")

# Create data dict
data = dict(
    birds = 38,
    temperature= -18,
    wind = 19,
)

# Push the data to database
PushDB(ref, data)
```

