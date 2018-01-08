# Web Engineering 2017-2018 / Microservices
## Brief report

In these two first screenshots we can see the microservices **accounts** and **web** running:

---

![Web terminal log](/Screenshots/web_log.png "Web terminal log")
*Web terminal log*

---

![Account terminal log](/Screenshots/accounts_log.png "Account terminal log")
*Account terminal log*

---

Also we can see in the **register** log the moment when the two previous microservices were added:

---

![Register terminal log](/Screenshots/register_log.png "Register terminal log")
*Register terminal log*

---

And in the dashboard:

![First dashboard](/Screenshots/dashboard_two_ms.png "First dashboard")
*First dashboard*

---

Now a third microservice is added, but this one is a little special because it's a copy of the **accounts**
microservice, displayed on a different port (4444).

---

![AccountBkup terminal log](/Screenshots/account2_log.png "AccountBkup terminal log")
*AccountBkup terminal log*

---

![Second dashboard](/Screenshots/dashboard_three_ms.png "Second dashboard")
*Second dashboard*

---

### The microservice on port 2222 is down.Can the web service provide information about the accounts?
Since the **account** microservice is duplicated, the **web** microservice can communicate with both copies,
depending on wich one the Eureka registration services provides. Until Eureka is fully aware that one of the two
copies of the **account** microservice is offline, it will continue to provide the port 2222 microservice
to **web**, resulting in some failed requests.
