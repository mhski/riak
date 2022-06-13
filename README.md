zadanie 1

// Umieść w bazie (nazwa bucketa ma być Twoim numerem indeksu poprzedzonym literą „s”) 5 wartości, gdzie każda z nich ma być dokumentem json mającym 4 pola co najmniej dwóch różnych typów.

curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Jan", "Last name": "Kowalski", "salary": 1000, "isRealKowalski": false}' http://localhost:8098/buckets/s16585/keys/jan

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:14:18 GMT
Content-Type: application/json
Content-Length: 0


curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Jurek", "Last name": "Kowalski", "salary": 1000, "isRealKowalski": false}' http://localhost:8098/buckets/s16585/keys/jurek

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:21:43 GMT
Content-Type: application/json
Content-Length: 0


curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Marek", "Last name": "Kowalski", "salary": 1200, "isRealKowalski": false}' http://localhost:8098/buckets/s16585/keys/marek

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:24:33 GMT
Content-Type: application/json
Content-Length: 0


curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Marian", "Last name": "Kowalski", "salary": 15000, "isRealKowalski": true}' http://localhost:8098/buckets/s16585/keys/marian

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:26:12 GMT
Content-Type: application/json
Content-Length: 0


curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Karol", "Last name": "Kowalski", "salary": 1000, "isRealKowalski": false}' http://localhost:8098/buckets/s16585/keys/karol

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:54:46 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 2

// Pobierz z bazy jedną z dodanych przez Ciebie wartości.

curl -i -XGET http://localhost:8098/buckets/s16585/keys/marian

HTTP/1.1 200 OK
X-Riak-Vclock: a85hYGBgzGDKBVI8ypz/firf3vgKIpTImMfKYMInfYcvCwA=
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Link: </buckets/s16585>; rel="up"
Last-Modified: Mon, 13 Jun 2022 01:26:12 GMT
ETag: "2exHBYXG5lqg8vAiv7kGz4"
Date: Mon, 13 Jun 2022 01:27:11 GMT
Content-Type: application/json
Content-Length: 84

{"name": "Marian", "Last name": "Kowalski", "salary": 15000, "isRealKowalski": true}\

--------------------------------------

zadanie 3

// Zmodyfikuj jedną z wartości – dodając dodatkowe pole do dokumentu.

curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Marian", "Last name": "Kowalski", "salary": 15000, "premia": 150, "isRealKowalski": true}' http://localhost:8098/buckets/s16585/keys/marian

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:30:32 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 4

// Zmodyfikuj jedną z wartości – usuwając jedną pole z wybranego dokumentu.

curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Marek", "Last name": "Kowalski", "salary": 1200}' http://localhost:8098/buckets/s16585/keys/marek

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:32:34 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 5

// Zmodyfikuj jedną z wartości – zmieniając wartość jednego z pól.

curl -i -XPUT -H "Content-Type: application/json" -d '{"name": "Andrzej", "Last name": "Kowalski", "salary": 1000, "isRealKowalski": false}' http://localhost:8098/buckets/s16585/keys/jurek

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:34:34 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 6

// Usuń jeden z dokumentów z bazy.

curl -i -XDELETE http://localhost:8098/buckets/s16585/keys/jan

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:37:12 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 7

// Spróbuj pobrać z bazy wartość, która nie istnieje w tej bazie.

curl -i -XGET http://localhost:8098/buckets/s16585/keys/jan

HTTP/1.1 404 Object Not Found
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:38:06 GMT
Content-Type: text/plain
Content-Length: 10

not found

--------------------------------------

zadanie 8

// Dodaj do bazy 1 dokument json (zawierający 1 pole), ale nie specyfikuj klucza.

curl -i -XPOST -H "Content-Type: application/json" -d '{"name": "Andrzej", "Last name": "Piaseczny"}' http://localhost:8098/buckets/s16585/keys

HTTP/1.1 201 Created
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Location: /buckets/s16585/keys/KQ5xBFfqfguiTIjo8GsZvPDpOHs
Date: Mon, 13 Jun 2022 01:48:11 GMT
Content-Type: application/json
Content-Length: 0

--------------------------------------

zadanie 9

// Pobierz z bazy element z zadania 8.

curl -i -XGET http://localhost:8098/buckets/s16585/keys/KQ5xBFfqfguiTIjo8GsZvPDpOHs

HTTP/1.1 200 OK
X-Riak-Vclock: a85hYGBgzGDKBVI8ypz/firfnisHZDNlMCUy5rEyRAtL3+HLAgA=
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Link: </buckets/s16585>; rel="up"
Last-Modified: Mon, 13 Jun 2022 01:48:11 GMT
ETag: "STOEThoDNpQOAPBjLg8Jf"
Date: Mon, 13 Jun 2022 01:49:21 GMT
Content-Type: application/json
Content-Length: 45

{"name": "Andrzej", "Last name": "Piaseczny"}

--------------------------------------

zadanie 10

// Usuń z bazy element z zadania 8.

curl -i -XDELETE http://localhost:8098/buckets/s16585/keys/KQ5xBFfqfguiTIjo8GsZvPDpOHs

HTTP/1.1 204 No Content
Vary: Accept-Encoding
Server: MochiWeb/1.1 WebMachine/1.10.9 (cafe not found)
Date: Mon, 13 Jun 2022 01:50:39 GMT
Content-Type: application/json
Content-Length: 0
