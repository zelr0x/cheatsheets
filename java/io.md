# Java I/O streams
Not all methods and constructors are listed here, as well as not all classes. Work in progress.


Class | &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Notable methods &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  | Desctiption
--- | --- | ---
`InputStream`&nbsp;implements<br/>Closeable, Autocloseable | `abstract int read()`| Read byte. There are methods to read into an array. Blocks until read
`OutputStream`&nbsp;implements<br/>Flushable,<br/>Closeable, AutoCloseable | `abstract void write(int b)` | Write byte. Blocks until written
`Reader`&nbsp;implements<br/>Readable,<br/> Closeable, AutoCloseable| `abstract int read()` | Read UTF-16 code unit as uint16
`Writer`&nbsp;implements<br/>Appendable, Flushable,<br/>Closeable, AutoCloseable | `abstract void write(int c)` | Write UTF-16 code unit represented by uint16
`DataInputStream`&nbsp;implements<br/>DataInput,<br/>Closeable, AutoCloseable | `public DataInputStream(InputStream in)` | Read primitive types (@see DataInput interface)
`FileInputStream`&nbsp;implements<br/>Closeable, AutoCloseable | `FileInputStream(File file)`<br/>`FileInputStream(FileDescriptor fdObj)`<br/>`FileInputStream(String name)` | Read from file
`PushbackInputStream`&nbsp;implements<br/>Closeable, AutoCloseable | `unread(int b)`<br/>`PushbackInputStream(InputStream in)`</br>`PushbackInputStream(InputStream in, int size)` | Pushes back byte(s)
