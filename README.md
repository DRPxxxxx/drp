# D-RPath
# DR-Path

### LUBM queries

#### Q1

```
PREFIX ub: <tju:#>
SELECT ?f ?c  ?p
WHERE {
  ?f ub:teacherOf ?c .
  ?s ub:takesCourse ?c .
  ?s  ub:advisor ?f.
} 
```

#### Q2

```
PREFIX ub: <tju:#>

SELECT ?s ?f ?c  ?p 
WHERE {
  ?f ub:teacherOf ?c .
  ?s ub:takesCourse ?c .
  ?f ub:publication ?p .
}  
```

#### Q3

```
SELECT ?s ?f ?c ?cn ?p
WHERE {
  ?f ub:teacherOf ?c .
  ?c ub:name ?cn .
  ?s ub:takesCourse ?c .
  ?s ub:memberOf ?d .
  ?f ub:memberOf ?d .
  ?f ub:publication ?p
}
```

#### Q4

```
PREFIX ub: <tju:#>

SELECT ?s ?f ?c ?cn ?p ?pt
WHERE {
  ?f ub:teacherOf ?c .
  ?s ub:takesCourse ?c .
  ?s ub:memberOf ?d .
  ?f ub:publication ?p .
  ?p ub:title ?pt .
}
```

#### Q5

```
PREFIX ub: <tju:#>

SELECT ?s ?f ?c ?cn ?d ?p ?pt
WHERE {
  ?f ub:teacherOf ?c .
  ?c ub:name ?cn .
  ?s ub:takesCourse ?c .
  ?s ub:memberOf ?d .
  ?f ub:memberOf ?d .
  ?f ub:publication ?p .
  ?p ub:title ?pt .
}
```

#### Q6

```
PREFIX ub: <tju:#>

SELECT ?s ?f ?c ?c1 ?cn ?p ?pt ?r
WHERE {
  ?f ub:teacherOf ?c .
  ?f ub:teacherOf ?c1 .
  ?c ub:name ?cn .
  ?s ub:takesCourse ?c .
  ?s ub:memberOf ?d .
  ?f ub:memberOf ?d .
  ?f ub:publication ?p .
  ?p ub:title ?pt .
  ?f ub:researchInterest ?r
}
```

## DBpedia queries

#### Q1

```
select ?a ?d ?f where {
?a      <http://dbpedia.org/ontology/spouse>    ?d.
?f      <http://dbpedia.org/ontology/director>  ?d.
?f      <http://dbpedia.org/ontology/starring>  ?a.
```

#### Q2

```
select ?a ?d  ?f2 ?n2 where {
?f2 <http://xmlns.com/foaf/0.1/name> ?n2.
?f2 <http://dbpedia.org/ontology/director> ?d.
?d <http://dbpedia.org/ontology/spouse> ?a.
}
```

#### Q3

```
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT * WHERE {
        ?x rdf:type dbo:Athlete.
    ?z rdf:type dbo:Settlement.
    ?A rdf:type dbo:Movie.
    ?x dbo:occupation ?y.
    ?x dbo:deathPlace ?z.
    ?A dbo:director ?x.
}
```

#### Q4

```
select ?a ?d ?f1 ?f2 ?n1 ?n2 where {
?d      <http://dbpedia.org/ontology/spouse>    ?a.
?f2     <http://dbpedia.org/ontology/director>  ?d.
?f2     <http://xmlns.com/foaf/0.1/name>        ?n2.
?f1     <http://dbpedia.org/ontology/starring>  ?a.
?f1     <http://xmlns.com/foaf/0.1/name>        ?n1.
```

#### Q5

```
select ?a ?d ?f1 ?f2 ?n1 ?n2 ?e where {
?d      <http://dbpedia.org/ontology/spouse>    ?a.
?f2     <http://dbpedia.org/ontology/director>  ?d.
?f2     <http://xmlns.com/foaf/0.1/name>        ?n2.
?f1     <http://dbpedia.org/ontology/starring>  ?a.
?f1     <http://xmlns.com/foaf/0.1/name>        ?n1.
?f2     <http://dbpedia.org/ontology/writer>    ?e.
}
```

#### Q6

```
select ?a ?d ?f1 ?f2 ?n1 ?n2 ?e ?e1where {
?d      <http://dbpedia.org/ontology/spouse>    ?a.
?f2     <http://dbpedia.org/ontology/director>  ?d.
?f2     <http://xmlns.com/foaf/0.1/name>        ?n2.
?f1     <http://dbpedia.org/ontology/starring>  ?a.
?f1     <http://xmlns.com/foaf/0.1/name>        ?n1.
?f2     <http://dbpedia.org/ontology/writer>    ?e.
?f1     <http://dbpedia.org/ontology/writer>    ?e1.
}
```

