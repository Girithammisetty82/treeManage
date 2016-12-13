# treeManage
Application to manage  tree using Spring boot ,data and JDK 1.8


# Highlights of application include
JDK 1.8
Spring Data Rest
Custom Spring Controllers for API
JPA2
Custom Spring Boot configuration classes
Embedded database configuartion (HSQL)
	

### To run this app

 mvn clean package
 mvn spring-boot:run
 
 

1)Add Root Node
http://localhost:8080/tree/node/addRoot
http:POST
Content-Type: application/json;charset=UTF-8
{"parentNode":{"name":"Root","description":"Root description"}}
2)Add child node
http://localhost:8080/tree/node/add
http:POST
Content-Type: application/json;charset=UTF-8
{"parentNode":{"name":"Root"},"node":{"name":"Child1","description":"Child1 description"}}
{"parentNode":{"name":"Root"},"node":{"name":"Child2","description":"Child2 description"}}
{"parentNode":{"name":"Child1"},"node":{"name":"Child11","description":"Child11 description"}}
{"parentNode":{"name":"Child1"},"node":{"name":"Child12","description":"Child12 description"}}

3) Add child node at given position
http://localhost:8080/tree/node/add
http:POST
Content-Type: application/json;charset=UTF-8
{"parentNode":{"name":"Root"},"node":{"name":"Child3","description":"Child1 description"},"position":5}
{"parentNode":{"name":"Child2"},"node":{"name":"Child21","description":"Child21 description"},"position":2}


4) Retrieve a single node
http://localhost:8080/tree/node/find
http:POST
Content-Type: application/json;charset=UTF-8
{"node":{"name":"Child2"}}

5) Retrieve all descendants of a node 
http://localhost:8080/tree/node/findAllChildren
http:POST
Content-Type: application/json;charset=UTF-8
{"node":{"name":"Root"}}

6)Remove a node from the tree (also removes all of its children)
http://localhost:8080/tree/node/remove
http:POST
Content-Type: application/json;charset=UTF-8
{"node":{"name":"Child3"}}
