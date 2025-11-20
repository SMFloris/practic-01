# Practic 01 - unit + integration testing

Un schelet simplu de aplicatie pentru testare.

## Necesar

Java 21 (LTS)
VsCode sau orice alt editor modern cu suport Gradle

## Cum rulam testele?

In terminal putem rula:
```
gradle test
```

Sau direct din IDE, putem da click pe `Run test`.

## Challenge-uri

Fa-ti un fork din acest repo.
In fork-ul tau, creeaza-ti un nou branch.
Dupa ce termini challenge-urile (sau cate poti sa faci), fa un PR catre branch-ul `main` din acest repo.

### 01 - Fibbonaci

Scrie o functie numita `fib` care accepta ca si parametru un numar natural `n` - functia trebuie sa returneze al n-lea numar din sirul lui Fibbonaci.
Scrie un test unitar care testeaza rezultatul pentru n = 10.

### 02 - Fibbonaci table-driven

Pentru aceeasi functie `fib` scrie un test care ia un tabel de date de intrare/iesire.
Tabelul trebuie sa fie un fisier `csv`.

### 03 - Fibbonaci refactor in stil TDD

Daca la 01 ai folosit recursivitate, la acest pas foloseste alta metoda. Daca nu, foloseste recursivitatea pentru a calcula al n-lea numar din sirul Fibbonaci.

Numeste noua functie `fib2`, foloseste aceleasi date de intrare de la testele anterioare si pentru a testa aceasta functie.

### 04 - Integration testing by mocking

In acest challenge, vom simula o integrare cu o platforma externa via Mocking. Testele ar trebui sa fie deterministe, din aceasta cauza nu ar trebui sa atinga alte servicii externe la care nu ai controlul niciodata.
Un serviciu extern introduce provocari intr-o testare automatizata, cum ar fi: latenta aleatorie, accesul la serviciul extern imposibil datorat firewall-urilor din mediul de testare, etc.
Din aceste cauze, vom prefera folosirea unui asa numit Mock.

Vei folosi API-ul de la url-ul acesta: `https://jsonplaceholder.typicode.com/users`, respectiv `https://jsonplaceholder.typicode.com/posts?userId={userId}`

Vei crea o interfata numita `UserClientInterface` si o clasa numita `UserClient` cu care vei face un http call la acea ruta.

In clasa principala a aplicatiei:
- vei creea o functie numita `getUsers` care ia ca si parametru un `UserClientInterface`
- vei creea o functie numita `getUserPosts` care ia ca si parametru un `UserClientInterface` si un userId

In main:
- vei lua userii de la ruta
- vei afisa id-ul si numele utilizatorului
- vei intreba utilizatorul aplicatiei tale pentru ce id de user doreste sa vada postarile
- vei lua postarile cu userId-ul selectat
- vei afisa postarile userului in terminal

Pentru a completa acest challenge:

Creaza un test care testeaza `getUsers` cu o clasa numita `MockUserClient` (care implementeaza `UserClientInterface`)

Creaza un test care testeaza atunci cand utilizatorul selecteaza userul cu id-ul 2.

## Resurse utile

https://www.baeldung.com/parameterized-tests-junit-5
