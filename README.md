## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
1. protocal - the http or https (secure)
2. domain - it makes IP address 'human-readable'. So we can use it to locat servers. 
3. port - port for server, usually do not show on url if it is default setting.   
4. path - the path to access contain on server. 
5. query string - list of arguments that add on your request.  
6. anchor tag - it's a marke that we can jump to the specific location of the pase.  
```

* Name the pieces of the following urls:
	* `https://www.google.com/`
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367` 
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy` 
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error` 

```
1. protal + domain
2. protal + domain + path
3. protal + domain + port + path + query string + anchor tag
4. protal + domain + path + anchor tag  

```

* Can a server use more than 1 port?  

```
Yes! We can set different ports to deal with different requests.  
```

* Why is https different than http?

```
HTTPS stand for "HyperText Transfer Protocol Secure". Data tranmission between local with server is SSL encrypt that need a "key" to read them. So it is safer.
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

```
The query string starts from '?'. The equal sign is where we specifiy parameter and value. 'puppies' is the parameter with value of 'fido'. The '&' adds up other query condition.

The same key 'puppies' appear 3 times. It creates 'or' condition on server to query puppies with name 'fido' or 'max' or 'moxie'. 
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
"GET", "POST", "PUT", "DELETE"
```

* What is each verb useful for in your own words

```
1. GET : To send request to get data from server. 
2. POST : To send info/data from our side to server. 
3. PUT : To modify the existing data on server
4. DELETE : To send a request to delete data on server.
```

* What does idempotent mean?

```
Idempotent means certain operation (requests or calls) that does not modify or change the original status. for example, in GET requests, we can send requests for many times, but it doesn't change any state on the server.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1. 1XX : loading...
2. 2XX : successful/ okay
3. 3XX : re-direct to somewhere else.
4. 4XX : error from client side.
5. 5XX : error from server side.
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
code range of 300 is something about 'redirect'. The code 301 means "Moved Permanently". The location is the current location of the stuff we are looking for. The browser will then take us to the new site.

```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	* Content-type
	* User-agent
	* Set-cookies
	* Cache-control
	* Cookie

```
1. Accept : request
2. Content-type : both request & response
3. User-agent : request
4. Set-cookies : response
5. Cache-control : both request & response
6. Cookie : request
```

* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
It's a response from "GET" request.
```



```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

```
It's a "DELETE" request.
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JASON -  JavaScript Object Notation.

It is a data exchange formate which wrap our data/info into a 'string'. Then we send/ exchange these information through internet. One we or service recieve these data, it parse JSON back into JavaScript or HTML or whatever it supposes to be.
```


* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
var companyArr = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');

console.log(companyArr.age]); 
```


* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var companyArr = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories":"Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}')

companyArr.Companies.forEach(function(e){
  console.log(e.company)
})

--> ["Github", "Airbnb", "Square", "Dropbox"]
```



* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
var toJSON = JSON.stringify(myObj)
console.log(toJSON)

--> {"company":"Galvanize","age":3,"categories":"Education"}
```



__MISC__

* Describe what DNS is.

```
DNS: Domain Name System. This system helps us match the readable 'domain name' to actual 'IP Address'. When broswer query a domain name, it goes to 'root domain' to locate where the TLD (Top-Level-Domain) server is. Then, TLD tells us where the ANS (Authoritative Name Server), the server store the IP address we are looking for. 
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v: --verbose A  line starting  with  '>'  means "header data" sent by curl, '<' means
              "header data" received by curl that is hidden in  normal  cases,
              and  a  line starting with '*' means additional info provided by
              curl.

-X: --request <command> (HTTP) Specifies a custom request method to use when communicat-
              ing  with the HTTP server.  The specified request method will be
              used instead of the method otherwise  used  (which  defaults  to
              GET).

```

* What is TCP/IP?  How does it interact with HTTP?

```
TCP & IP are lower-level internet Protocol. TCP (Transmission Control Protocol) is a protocal or standard of how to break application data into packets that networks can deliver, sends packets to and assemble packets from the network. But when deliver, TCP needs IP address to know where it should link to.

TCP is a  connection-oriented protocol, they establish 'connection'. HTTP (Hypertext Transfer Protocol) is a higher level Protocol. So when a web server send an HTML file, it uses HTTP protocal. The HTTP defines set of rules for transferring files like text, graphic images, sound, video, and other multimedia files. And it uses lower level protocol, TCP/IP, to break them into packages and assemble at the other end.
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, TPC/IP does that. 
```

