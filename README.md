# Create a High-score Service

Create a RESTful service, written in PHP, that would allow a game to post a user's score for ranking on a leaderboard. Your code should be written from scratch and must not make use of any 3rd party frameworks (Laravel, Zend Framework, Symfony, Cake, etc). Assume the player of the game will be coming from a Facebook application, so you will be passed a Facebook `signed_request` variable (see the Reference Data section below) containing the information about the user. In addition, assume you will be passed the user's score as `user_score`. Decode the `signed_request` to get the user's unique ID.  Design a MySQL schema for storing the data for the player and the score information.

# Generate Test Data for Your Service

Build a tool to populate the database tables with 1,000,000 rows of sample data.

# Create a Reporting Tool for Your Service

Build a report that efficiently answers the following questions. The report should be consumable as an endpoint of your RESTful service:

- How many total players are there?

- How many people played the game today?

- List the top 10 players (by score)

- List the top 10 players who improved their score over the course of the week (the difference between the high score they posted last week and their high score this week). You can assume the week ends Sunday at midnight.

# Reference Data

You can use the following Facebook application data and signed request for a user:

```
appId:
126767144061773

secret:
21db65a65e204cca7b5afcbad91fea59

signed_request:
cjv1NZlSRCthYq9rAyWEidD7QE98p0PKZvVwpQ7gPwg.eyJhbGdvcml0aG0iOiJITUFDLVNIQTI1NiIsImV4cGlyZXMiOjEzMjI4NTYwMDAsImlzc3VlZF9hdCI6MTMyMjg1MDc1NCwib2F1dGhfdG9rZW4iOiJBQUFCelMwYVhTMDBCQUlob0I1bmhrYnZJU0xLSGpNb3ZIN2ZTTmMzWkFxbnVNT2NvYmpJUHoxNGFmWXV1dzBkbkZzeVpBV2JHU2MycXZBakdjRzZUQ1RWZzBLOUVGUWJ5WkJwNTU0ZXE5M2FTWkFXZXpVeEYiLCJ1c2VyIjp7ImNvdW50cnkiOiJ1cyIsImxvY2FsZSI6ImVuX1VTIiwiYWdlIjp7Im1pbiI6MjF9fSwidXNlcl9pZCI6IjEwMDAwMzI5MTY2MTkwOSJ9
```

The encoded signed_request above contains the following data:

```
{
	"algorithm": "HMAC-SHA256",
	"expires": 1322856000,
	"issued_at": 1322850754,
	"oauth_token": "AAABzS0aXS00BAIhoB5nhkbvISLKHjMovH7fSNc3ZAqnuMOcobjIPz14afYuuw0dnFsyZAWbGSc2qvAjGcG6TCTVg0K9EFQbyZBp554eq93aSZAWezUxF",
	"user": {
		"country": "us",
		"locale": "en_US",
		"age": {
			"min": 21
		}
	}
	"user_id": "100003291661909"
}
```

# Other requirements

- The code should live somewhere online and able to process requests from the web. 
- Requests should spend no more than 1 second in processing a data set of 1 million users. 
- Do not to use anything other than PHP, MySQL, and a web engine such as Apache or Nginx (i.e. no PHP frameworks, no Redis, memcache or other in-memory stores, no 3rd party libraries beyond those included in PHP 5.).
