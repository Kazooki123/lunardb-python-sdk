# LunarDB Python SDK

The LunarDB Python SDK provides a simple and intuitive interface to interact with a LunarDB instance, a high-performance in-memory cache database. It supports basic database operations such as `SET`, `GET`, `DEL`, as well as list operations like `RPUSH`, `RPOP`, and more.

## Features

- **Key-Value Operations**: Easily set and retrieve values using simple commands.
- **List Operations**: Push, pop, and manage lists within LunarDB.
- **Efficient in-memory operations** for high-performance caching.
- **RESTful API integration** for easy communication with LunarDB instances.

## Installation

To install the LunarDB Python SDK, run the following:

```bash
pip install lunardb-py
```

## Usage

Here is how you can use the SDK:

### 1. Connecting to LunarDB

```python
from lunardb.client import LunarDBClient

# Connect to a LunarDB instance
client = LunarDBClient(base_url="http://localhost:8000")
```

### 2. Setting and Getting Keys

```python
# Set a value
client.set("mykey", "myvalue")

# Get a value
value = client.get("mykey")
print(f"The value for 'mykey' is {value}")
```

### 3. Deleting Keys

```python
# Delete a key
client.delete("mykey")
```

### 4. List Operations

```python
# Push values to a list
client.rpush("mylist", "value1")
client.rpush("mylist", "value2")

# Pop the last value from the list
last_value = client.rpop("mylist")
print(f"Popped value: {last_value}")

# Get a range of values from the list
values = client.lrange("mylist", 0, -1)
print(f"Values in 'mylist': {values}")

# Get the length of the list
length = client.llen("mylist")
print(f"Length of 'mylist': {length}")
```

## API Reference

### `LunarDBClient` Class

- `__init__(base_url: str, api_key: Optional[str] = None)`: Initializes the LunarDB client.
- `set(key: str, value: Any)`: Sets a key-value pair in LunarDB.
- `get(key: str)`: Retrieves the value for a given key.
- `delete(key: str)`: Deletes a key from the database.
- `rpush(key: str, value: Any)`: Pushes a value to a list.
- `rpop(key: str)`: Removes and returns the last element of a list.
- `lrange(key: str, start: int, stop: int)`: Retrieves a range of elements from a list.
- `llen(key: str)`: Gets the length of a list.

## License

This project is licensed under the MIT License.
