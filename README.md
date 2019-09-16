# API Project Timestam
​
### User stories :
​
1. The API endpoint is `GET [project_url]/api/timestamp/:date_string?`
2. A date string is valid if can be successfully parsed by `new Date(date_string)` (JS) . Note that the unix timestamp needs to be an **integer** (not a string) specifying **milliseconds**. In our test we will use date strings compliant with ISO-8601 (e.g. `"2016-11-20"`) because this will ensure an UTC timestamp.
3. If the date string is **empty** it should be equivalent to trigger `new Date()`, i.e. the service uses the current timestamp.
4. If the date string is **valid** the api returns a JSON having the structure 
`{"unix": <date.getTime()>, "utc" : <date.toUTCString()> }`
e.g. `{"unix":1665273600000,"utc":"Sun, 09 Oct 2022 00:00:00 GMT"}`.
5. If the date string is **invalid** the api returns a JSON having the structure `{"unix": null, "utc" : "Invalid Date" }`. It is what you get from the date manipulation functions used above.
​
#### Example usage:
* http://localhost:3000/api/timestamp/2019-01-23
* http://localhost:3000/api/timestamp/1548201600000
​
#### Example output:
* {"unix":1548201600000,"utc":"Wed, 23 Jan 2019 00:00:00 GMT"}
​
