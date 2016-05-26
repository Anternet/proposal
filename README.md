# proposal

```js
const Anternet = require('anternet');
const anternet = Anternet();
anternet.bind(12345);


const Channel = require('anternet-channel');
const channel = new Channel(anternet, id);

channel.listen(data => {
 console.log(data);
});



const Broadcast = require('anternet-broadcast');
const broadcast = new Broadcast(anternet, id, data);

broadcast.send(rinfo);
broadcast.send(group);



const Group = require('anternet-group');
const group = new Group(anternet, id);

group.add(peer);
group.ask(rinfo, (err, peers) => {
  console.log(peers);
});

group.lookup(rinfo, limit);



const Server = require('anternet-server');
const server = new Server(anternet);

server.serve(id, buffer);
server.serve(id, fd);



const Client = require('anternet-client');
const client = new Client(anternet);

server.get(id, peer)
	.pipe(fd);



const DHT = require('anternet-dht');
const client = new DHT(anternet);

server.lookup(id, (err, peers) => {
});

server.register(id);



const SharedVar = require('anternet-shared-var');
const sharedVar = new SharedVar(anternet, id);
const sharedVar = new SharedVar(anternet, id, secret, value);
const sharedVar = SharedVar.generate(anternet, value);

sharedVar.once('update', timestamp => {
  console.log(sharedVar.value);
});

sharedVar.set(value);
```
