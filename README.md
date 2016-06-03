# proposal

```js
const Anternet = require('anternet');
const anternet = Anternet();
anternet.bind(12345);


const Channel = require('anternet-channel');
const channel = new Channel(publicKey);

channel.listen(anternet, data => {
 console.log(data);
});


const Broadcast = require('anternet-broadcast');
const broadcast = new Broadcast(privateKey);
const broadcast = Broadcast.generate();

const msg = broadcast.sign(anternet, data);
msg.send(port, address);
msg.send(group);


const Group = require('anternet-group');
const group = new Group(anternet, id);

group.add(port, address);
group.ask(port, address, (err, peers) => {
  console.log(peers);
});

group.lookup(port, address, limit);


const Server = require('anternet-server');
const server = new Server(anternet);

server.serve(id, buffer);
server.serve(id, fd);


const Client = require('anternet-client');
const client = new Client(anternet);

server.get(id, port, address)
	.pipe(fd);


const SharedVar = require('anternet-shared-var');
const sharedVar = new SharedVar(anternet, id);
const sharedVar = new SharedVar(anternet, id, secret, value);
const sharedVar = SharedVar.generate(anternet, value);

sharedVar.once('update', timestamp => {
  console.log(sharedVar.value);
});

sharedVar.set(value);


const DHT = require('anternet-dht');
const client = new DHT(anternet);

server.lookup(id, (err, peers) => {
});

server.register(id);
```
