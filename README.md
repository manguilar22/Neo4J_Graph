# Neo4J_Graph
<img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/neo4j.svg" width="200px" height="200px"/>

Graph Databases are cool ...

### Neo4J on Docker


<img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/docker.svg" width="200px" height="200px"/>
``` bash
mkdir neo4j; mkdir data logs; cd neo4j
sudo docker run --name neo4j_server \
  --publish 4717:4717 \
  -v /data/:/data/ \
  -v /logs/:logs/ \
  neo4j:latest
```
