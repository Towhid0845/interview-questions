## ✅ What is Encapsulation ?
It is the mechanism of hiding of data implementation by restricting access to public methods. Instance 
variables are kept private and accessor methods are made public to achieve this.

## What is Serialization and its Types?
**Serialization** is the process of converting the state of an object into a format that can be easily stored or transmitted. This process transforms the object into a series of bytes, allowing it to be saved to a file, sent over a network, or stored in a database. The reverse process, known as **deserialization**, reconstructs the object from the byte stream.

### Types of Serialization

1. **Binary Serialization**:
   - Converts an object into a binary format.
   - Efficient in terms of space and speed.
   - Not human-readable, making debugging more challenging.
   - Commonly used in applications where performance is critical.

2. **Text Serialization**:
   - Converts an object into a human-readable format, such as JSON or XML.
   - Easier to debug and understand.
   - Typically larger in size compared to binary serialization.
   - Useful for data interchange between different systems or languages.

3. **XML Serialization**:
   - A specific type of text serialization that uses XML format.
   - Allows for structured data representation.
   - Widely used in web services and configuration files.

4. **JSON Serialization**:
   - Converts an object into JSON format.
   - Lightweight and easy to read.
   - Commonly used in web applications for data exchange between client and server.

5. **Custom Serialization**:
   - Developers can define their own serialization logic by implementing specific methods.
   - Provides flexibility to control how an object is serialized and deserialized.
   - Useful for complex objects or when specific data needs to be excluded or transformed during serialization.
