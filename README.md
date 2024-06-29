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

#### 
[root@0d4278336e9a D-RPath]# git init
Reinitialized existing Git repository in /home/D-RPath/.git/
[root@0d4278336e9a D-RPath]# git add README.md 
[root@0d4278336e9a D-RPath]# git commit -m "提交查询" 

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'root@0d4278336e9a.(none)')
[root@0d4278336e9a D-RPath]# git config --global user.email "1760566914@qq.com"
[root@0d4278336e9a D-RPath]# git config --global user.name "lcg223566"
[root@0d4278336e9a D-RPath]# git commit -m "提交查询" 
[master (root-commit) 6250499] 提交查询
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
[root@0d4278336e9a D-RPath]# git branch -M main 
[root@0d4278336e9a D-RPath]# git remote add origin https://github.com/lcg223566/D-RPath.git
fatal: remote origin already exists.
[root@0d4278336e9a D-RPath]# git push -u origin main
fatal: unable to access 'https://github.com/lcg223566/D-RPath.git/': Encountered end of file
[root@0d4278336e9a D-RPath]# git push -u origin main
Counting objects: 3, done.
Writing objects: 100% (3/3), 231 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote: To https://github.com/lcg223566/D-RPath.git
 * [new branch]      main -> main
Branch main set up to track remote branch main from origin.
[root@0d4278336e9a D-RPath]# cat D-RPath 
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

#### 
[root@0d4278336e9a D-RPath]# ls
D-RPath  README.md
[root@0d4278336e9a D-RPath]# cat README.md 
# D-RPath
[root@0d4278336e9a D-RPath]# cat D-RPath 
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

#### 
