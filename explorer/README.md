# explorer

Generate static HTML and a JSON API based on a file directory.

## Setup

`Explorer` builds a set of static `html` files from a `source_directory`.
The `source_directory` is a local directory hosted at a `source_url` by a server dedicated to audio, video, and media.

`explorer` does not add or remove files from the local directory. It reflects the
source directory structure with static `html` in a `target_directory` which can be
hosted by a separate server.

## config

Create a config file:

```
{
	"source_directory": "/home/taylor/my_awesome_stuff",
	"target_directory": "/home/taylor/www",
	"source_url": "http://0.0.0.0:3005"
}
```

Descendant directories will be matched onto `file_url`:

```
/home/taylor/my_awesome_stuff/cool_file.txt
http://0.0.0.0:3005/cool_file.txt
```


possible multiple sources:
```
[{
	"source_directory": "/home/taylor/my_awesome_stuff/images",
	"target_directory": "/home/taylor/www/images",
	"file_server_url": "http://0.0.0.0:3005/images"
}, ...]
```

possible cloud integrations:
```
{
	"cloud_url": "http://0.0.0.0:3010",
	"file_url": "http://0.0.0.0:3005"
}
```
But would need to define a "cloud" api. It might not be feasible to represent files in
directories at any sort of scale. Directories could be represented for usability.

Generating previews is a stretch goal and probably best done by a library in the
static directories (or the cloud) itself

## json

```JSON
[{
	"file_name": "...",
	"is_dir": bool,
	"created_at": "...",
	"last_modified": "..."
}, ...]
```


