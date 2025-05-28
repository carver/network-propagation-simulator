# Network Simulator

Portal is a Kademlia-style network. There is some content that we want to broadcast to every peer. This project simulates different strategies for gossipping.

## How to run
- Open the html file in a browser
- Select the number of peers to simulate
- Click "Setup Network"
- Choose how many peers that each peer should gossip to
- Choose how many peers start with the content
- Select the gossip strategy
- Click "Start Simulation"

You can update the Simulation Configuration fields and rerun the simulation. "Setup Network" runs in n^2 time, but you don't need to set it up before every simulation.

## Limitations

The simulation is simplified. Some limitations:
- Assume every bucket is as full as possible
- Network setup is O(n^2) time complexity, and noticeably slow
- Some strategies have a relatiely small limit of how many peers they can gossip to
- The simulation does not account for network latency or failures

## Strategies

Add a strategy by:
- Adding a function to the Peer class that accepts a number of peers to gossip to, and returns a `Set()` of peer IDs.
- Add an `<option>` to the `gossipStrategy` select element in the HTML file, with the name of the new function as the value.