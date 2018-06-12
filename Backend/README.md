# Backend Developer Hiring Test For Maven Workforce

This test is used as part of the recruitment process for developers looking to join Maven Workforce. 
We would expect this part normally to take between two and four hours to complete, however the time limit for 
the task is 24 Hours.

Your code should be written in a way that shows you have a good understanding of software design patterns 
and development best practices. You will be evaluated on the basis of your code
quality as well as your approach to solve the problem.

To Deploy the server you'll use Heroku and for Database you'll use mLabs

If you believe the test is unclear in anyway or you have any questions please feel free to ask.

# Your Task
Sample API: https://bitbucket.org/VijayPratap123/job-test-api/src/master/

This API handles a list of Jobs. allows you to add | delete the job

* As a User, I want to publish a Job.
    * A Job Title and description can't be empty.
    * A Job Description can't contain more than 500 characters.
    * A Job Poster name can't be empty.

* As a User, I want to view the list of published Jobs.
    * The list must be sorted by publication date in descending order.
     
To pass this test, we expect software that also fulfills the following list of strategic user stories

* As a User, I want to add links to the Job Description text without affecting the 500 character limit.
    * A link is any set of non-whitespace consecutive characters starting with http:// or https:// and finishing with a space.
        * For example, the tweet `Hey http://foogle.co` is 4 characters long, instead of 20.
        
* As a User, I want to add more filters on the basis of which published jobs can be listed.
   * A way sort list by publication date in ascending order.
   * A way to sort list on the basis of a specific word in title such as `for query 'Java'`, it should list all published jobs with 'Java' as a title in them.

* As a User, I want to discard Job Posts.
    * Jobs shall be discarded globally, we don't need user-based discarding.
    * Discarded jobs will not be shown in the published jobs list.
    
* As a User, I want to view a list of discarded Jobs.
    * The list must be sorted by the date it was discarded on in descending order.
    
* As a Developer, You'd want to implement a caching strategy as well.
    

## Technical Requirements

* The application must fulfill all of the acceptance criteria.
* Feel free to refactor old code when adding new user jobs.
* Application test coverage must not decrease.
* Do not use any framework or library not already in the codebase.
* API contracts can't be changed or modified any way.

### APIs

For the two new endpoints, you must accept this API:

* As a User, I want to discard Jobs:
    * POST /discarded
    * Content-Type: application/json
    * `{ "job": "%JOB_ID%" }` 
    
* As a User, I want to view a list of discarded Jobs:
    * GET /discarded
    * The response body format should be identical to the published jobs GET /tweet endpoint.
        * New fields are not allowed.

All other endpoint contracts must not be changed.

## Usage

From the application folder, run
```sh
./gradlew bootRun
```

To get all published jobs
```sh
curl http://localhost:8080/jobs
```

To publish a new job
```sh
curl -XPOST -d '{ "title": "Prospect", "description": "Breaking the law", "publisher": "" }' -H 'Content-Type: application/json' http://localhost:8080/tweet
```

## Test

From the application folder, run
```sh
./gradlew test
```





