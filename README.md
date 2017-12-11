# node-red-contrib-actionflows
Provides nodes to enable an extendable design pattern for flows. ActionFlows
can streamline the appearance of flows in a similar way that Node-RED's native
subflows work or the link nodes' "virtual wires"; invoking flow segments located
elsewhere. Unlike link nodes or subflows, flows that use the actionflows node do
NOT need to be aware of existing segments or have them pre-defined. Instead,
segments are invoked by a named prefix schema; allowing an arbitrary number of
flow segments to added or imported later (such as when using flowman or flow
dispatcher) without modifying the original flow. ActionFlows' segments are
invoked sequentially with their order determined by the segment's author (see
priority description below).

Inspired by WordPress' core actions and filters API (but faster) that inarguably
enabled one of the world's largest and most prolific plugin communities. This
implementation leverages jump tables and indexed objects to ensure the fastest
execution of flow segments. Like WordPress' actions & filters, actionflows
allow flow segments to have a priority property with values of 1 to 100 (with a
default of 50; a higher resolution than WordPress'). The priority property determines
earlier or later execution order of a flow segment. These features can make
flows extendable and allows flows to furnish an expandable, "plugin-able" API.

## Examples

#### Basic Example


![ActionFlows Basic Example](/actionflows/demo/basic.jpg?raw=true "Basic use")

Description to follow...
* Place the `action` node between nodes in a given flow to make the flow extensible.
* Give the `action` node a unique and short name that describes the action.
* Use the `action in` and `action out` nodes to create a flow segment.
* Name `action in` and `action out` nodes with a prefix that matches an existing action.

#### Another Example
Description with flow below...

```
[
    {
    }
]
```
## Installation
Run the following command in your Node-RED user directory (typically ~/.node-red):

    npm install node-red-contrib-actionflows

The actionflows' nodes are will appear in the palette under the advanced group as
the nodes `action`, `action in`, and `action out`.