# Neo4J Graph <img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/neo4j.svg" width="150px" height="100px"/>


* __Nodes__ Entity Information 
* __Relationships__ Connect one node to another
* __Properties__ Nodes & Relationships are **containers** for properties
* __Labels__ to make subgraphs

---

> * Extract entities by looking at the __nouns__ of the description. 
> * Extract the properties by looking at the __adjectives__ of the description. 
> * Extract the relationship by looking at the __verbs__ in the description. 

##### Graph 

<img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/Example_Of_Graph.svg" width="" height=""/>

```
MATCH(person:Person)-[r:ACTED_IN]->(movie:Movie) 
WHERE person.name = "Al Pacino" 
RETURN person,r,movie
```

##### Graph

<img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/Find_Tom_Hanks.svg" width="" height=""/> 

```
MATCH(person:Person)-[r:ACTED_IN | WROTE]->(movie:Movie)
WHERE person.name="Tom Hanks" AND r.earnings > 10000 AND movie.released > 2000
RETURN person,r,movie
```

### Neo4J on Docker

<img src="https://github.com/manguilar22/Neo4J_Graph/blob/master/images/docker.svg" width="150px" height="100px"/>

``` bash
mkdir neo4j; mkdir -p neo4j/data neo4j/logs; cd neo4j
sudo docker run --name neo4j_server \
  --publish 7474:7474 \
  --publish 7687:7687 \
  -v /data/:/data/ \
  -v /logs/:logs/ \
  neo4j:latest
```
