## Repositories
https://github.com/octoobservo

### Application
laravel-crm https://github.com/octoobservo/laravel-crm. Please follow the instructions in the README.md file to install and run the application on you local machine.

### Code bases for RAG
- https://github.com/octoobservo/laravel-crm
- https://github.com/octoobservo/monolog-loki
- https://github.com/octoobservo/monolog


### RAG code
https://github.com/octoobservo/windbag
- It RAGs the code bases
- It returns a potential fix for an error log


## TODO
### Background service that monitors the logs
We can just monitor the logs from the file system since the demo will be on a local machine. 
This background service also needs to make request to codellama to get a potential fix for the error

### GitHub integrations
We need to be able to create GitHub issues and pull requests

### Fine tune the RAG
We need to fine tune the RAG to improve the accuracy of the potential fix

### Make bugs in the application
We need to create some bugs in the application to test the solution

### AI for QA/Support teams
I think this one is optional. We can take this if we have extra time.
