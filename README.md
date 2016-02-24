# Random Topology Generator

This python tool generates random network topologies consisting of routers, clients, and servers. Input parameters can be specified in a configuration file. The generated topologies are written into JSON output files and optionally plotted in PDF format.

## Running topo-gen

To run `topo-gen` use the following command:

```
$ ./topo-gen.py -c <configFile> -o <outputFile>
```

where `<configFile>` is the configuration file path and `<outputFile>` is the output file name without the extension. `topo-gen` will create two output files: `<outputFile>.json` and `<outputFile>.pdf`, if requested.

## Configuration

The following is a sample configuration file:

```
{
	"topologies": "number of generated topologoes",
	"plot": "True/False, plot topology to pdf",
	"dimensions": "e.g. 10x10",
	"routers": "number of routers",
	"router-links": "routers links, e.g. 2 or 1-2",
	"clients": "number of clients",
	"client-links": "number of each client links, e.g. 2 or 1-2",
	"servers": "number of producers",
	"server-links": "number of each server links, e.g. 2 or 1-2",
	"channels": "number of channels",
	"channel-rates": "list of channel rate, e.g. 10,100,1000"
}
```

All parameters are required and explained below:

* `topologies` -- the number of topologies to be generated. The output files are appended with the topology index. For instance, `<outputFile>_1.json`, `<outputFile>_2.json`, etc.
* `plot` -- `True` to plot the generated topologies into PDF files, `False` otherwise.
* `dimensions` -- the dimensions of the topology area.
* `routers` -- the number of routers in the topology.
* `router-links` -- the number of links each router can have when connecting to neighboring routers. This parameter can specify an exact number of link or a range of the format `min-max`, e.g., `2-5`.
* `clients` -- the number of clients in the topology.
* `client-links` -- the number of links each client can have when connecting to neighboring routers. This parameter can specify an exact number of link or a range of the format `min-max`, e.g., `2-5`.
* `servers` -- the number of servers in the topology.
* `server-links` -- the number of links each server can have when connecting to neighboring routers. This parameter can specify an exact number of link or a range of the format `min-max`, e.g., `2-5`.
* `channels` -- the number of channels used to connect the topology nodes. Each channel can have a different data rate.
* `channel-rates` -- a list of channel rates. The size of this list should match the value of the `channel` parameter.

## Acknowledgement

This tool was implemented as part of the [ICNSimulator](https://github.com/chris-wood/ICNSimulator) project, a work done with the collaboration of [Christopher Wood](https://github.com/chris-wood/).
