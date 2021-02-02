## Getting Started
Before you start, make sure you already have redis-cli and redis-server at your terminal.

In this example, I was using `redis v5.0.4`.

Ready ? Let's start!

## Steps to start redis cluster:
1. Open six different terminals. (I recommend using split pane by iTerms! :) )
![first_img](https://github.com/dickywijayaa/redis-cluster-local/blob/master/docs/six_terminal_before.png?raw=true)

2. Each terminal opening each folder from 7000-7005.

3. Start redis-server for each folder, by executing this command:
```
redis-server redis.conf
```
![second_img](https://github.com/dickywijayaa/redis-cluster-local/blob/master/docs/six_terminal_after_init_redis.png?raw=true)

4. After that you will notice that each port is creating nodes.conf file.

5. Finally you can start the redis cluster by executing this command:
```
redis-cli --cluster create 127.0.0.1:7000 127.0.0.1:7001 \
127.0.0.1:7002 127.0.0.1:7003 127.0.0.1:7004 127.0.0.1:7005 \
--cluster-replicas 1
```

6. After there is message like this, it means the creation process is successfuly executed:
```
[OK] All 16384 slots covered
```
![third_img](https://github.com/dickywijayaa/redis-cluster-local/blob/master/docs/create_cluster.png?raw=true)

To check is the redis-cluster run or not, simply execute this function:
```
redis-cli -c -p 7000 ping
```
And the server will response with:
```
PONG
```

Well, that's it! Now you have redis cluster in your local environment that can be connecct with your application!
If you want to know more details about redis cluster, check the official docs [here](https://redis.io/topics/cluster-tutorial). 

## Contributor
<p>
  <a href="https://github.com/dickywijayaa">
    <img width="50" src="https://avatars.githubusercontent.com/u/34730861?s=460&v=4" alt="Dicky Wijaya">
  </a>
</p>