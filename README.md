### **GitHub Docs CRUD Operations**



This is project is all about performing the API Testing on the GitHub repositories.



1. Firstly create your GitHub account personal access token (classic).

`github.com/SETTINGS/PROFILE` > `Developer settings` > `Personal access tokens \[Tokens (classic)]` > `Generate new token \[classic]`

check the required scopes (`\[repo, delete\_repo]` for this project)



2\. list the requests (listing, creating, getting newly created, updating, deleting)

* listening

```bash

curl -L \\

&#x20; -H "Accept: application/vnd.github+json" \\

&#x20; -H "Authorization: Bearer {{token}}" \\

&#x20; -H "X-GitHub-Api-Version: 2026-03-10" \\

&#x20; https://api.github.com/users/{{user}}/repos

```



* creating

```bash

curl -L \\

&#x20; -X POST \\

&#x20; -H "Accept: application/vnd.github+json" \\

&#x20; -H "Authorization: Bearer {{token}}" \\

&#x20; -H "X-GitHub-Api-Version: 2026-03-10" \\

&#x20; https://api.github.com/user/repos \\

&#x20; -d '{"name":"Hello-World","description":"This is your first repository","homepage":"https://github.com","private":false,"has\_issues":true,"has\_projects":true,"has\_wiki":true}'

```



* getting newly created

```bash

curl -L \\

&#x20; -H "Accept: application/vnd.github+json" \\

&#x20; -H "Authorization: Bearer {{toekn}}" \\

&#x20; -H "X-GitHub-Api-Version: 2026-03-10" \\

&#x20; https://api.github.com/repos/{{user}}/{{repo}}

```



* updating

```bash

curl -L \\

&#x20; -X PATCH \\

&#x20; -H "Accept: application/vnd.github+json" \\

&#x20; -H "Authorization: Bearer {{token}}" \\

&#x20; -H "X-GitHub-Api-Version: 2026-03-10" \\

&#x20; https://api.github.com/repos/{{user}}/{{repo}} \\

&#x20; -d '{"description":"API Updated description."}'

```



* deleting

```bash

curl -L \\

&#x20; -X DELETE \\

&#x20; -H "Accept: application/vnd.github+json" \\

&#x20; -H "Authorization: Bearer {{token}}" \\

&#x20; -H "X-GitHub-Api-Version: 2026-03-10" \\

&#x20; https://api.github.com/repos/{{user}}/{{repo}}

```



2\. Create the testing environment

|**Variable**|**Value**|
|-|-|
|url|https://api.github.com|
|user|YOUR\_GITHUB\_AC|
|repo|YOUR\_REPO|
|token|YOUR\_GIHTUB\_AC\_ACCESSTOKEN|



3\. Examine and analyse the Test Plan, Test Scenarios, Test Cases and test scripts. 

4\. Run the postman collection using `newman`

&#x09;`newman run collection.json -e environment.json`



5\. If there are mistakes, re-write the scripts, requests, and test cases and run again.

