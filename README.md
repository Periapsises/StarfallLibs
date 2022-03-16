# StarfallLibs
Libraries for use in [**Starfall Ex**](https://github.com/thegrb93/StarfallEx)

They don't do anything on their own but rather provide functions and variables to use so you don't have to rewrite it everytime.

## Index

- [Async](#async)
- [Zip](#zip)

## Async


```lua
require( "async.txt" )
```
Implements a few functions which brings Lua's `coroutines` closer to `async` and `await` in other languages.
It also creates extra functions to facilitate the use with threads such as async http functions.

---

```cs
thread: async( function: func )
```
Converts a function into a thread that runs asynchroneously.
- _function_: **func** - The function to convert into a thread
- _thread_: **return** - Returns the newly create thread

```cs
any: await( thread: thread )
```
Stops the execution of the current thread until the specified thread has finished it's own execution.
- _thread_: **thread** - The thread to wait for
- _any_: **return** - The value(s) returned by the thread upon finishing

```cs
nil: quota( number: percent )
```
Yields from the current thread if the cpu usage is above the specified percentage.
- _number_: **percent** - A number between `0` and `1` representing the percentage

```cs
thread: http.getAsync( string: url, [table: headers = {}] )
```
Creates a thread that performs an Http GET request to a url and returns the response
- _string_: **url** - The url to send the request to
- Optional _table_: **headers** - A list of headers to send with the request
- _thread_: **return** - A thread you can await for

```cs
thread: http.postAsync( string: url, [string: payload = ""], [table: headers = {}] )
```
Creates a thread that performs an Http POST request to a url and returns the response
- _string_: **url** - The url to send the request to
- Optional _string_: **payload** - The payload to send along with the request
- Optional _table_: **headers** - A list of headers to send with the request
- _thread_: **return** - A thread you can await for

## Zip

```lua
local zip = require( "zip.txt" )
```
Provides access to unzipping functions for either uncompressed or deflated data.

---

```cs
table: zip.unzipString( string: str, [bool: threaded = false] )
```
Unzips the given string
- _string_: **str** - The string to unzip
- Optional _bool_: **threaded** - Whether to yield before reaching max quota or not
- _table_: **return** - A list of files that were unzipped

```cs
table: zip.unzipFile( string: path, [bool: threaded = false] )
```
Unzips the contents of a file under `sf_filedata`
- _string_: **path** - The path to the file
- Optional _bool_: **threaded** - Whether to yield before reaching max quota or not
- _table_: **return** - A list of files that were unzipped
