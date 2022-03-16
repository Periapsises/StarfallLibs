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

```cs
thread: async( function: func )
```


```cs
any: await( thread: thread )
```


```cs
what: quota( number: percent )
```


```cs
thread: http.getAsync( string: url, [table: headers = {}] )
```


```cs
thread: http.postAsync( string: url, [string: payload = ""], [table: headers = {}] )
```

## Zip


```lua
local zip = require( "zip.txt" )
```

```cs
table: zip.unzipString( string: str, [bool: threaded = false] )
```


```cs
table: zip.unzipFile( string: path, [bool: threaded = false] )
```
