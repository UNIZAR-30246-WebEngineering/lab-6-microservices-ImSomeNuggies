# Lab report

**###Forked repository**
```
https://github.com/ImSomeNuggies/lab6-microservices-config-repo
```

## Two service screenshots
### Web Service:
![First service](/docs/images/LogWeb1.jpg)

![First service](/docs/images/LogWeb2.jpg)

### Account Service:

![Second service](/docs/images/LogAccount1.jpg)

![Second service](/docs/images/LogAccount2.jpg)

![Second service](/docs/images/LogAccount3.jpg)

![Second service](/docs/images/LogAccount4.jpg)


### Eureka dashboard

![Dashboard](/docs/images/EurekaDashboard.jpg)

## Commit: account service now uses port 1111 instead of 2222 (originally used 3333, and changed it to 2222, but 2222 was somehow in use)

```
https://github.com/ImSomeNuggies/lab6-microservices-config-repo/commit/74d0a93d6af6856fbae326f8c7baf4d8209a7210
```

## Running second instance of the accounts service with new configuration

We begin by running a single instance of the accounts service, the Eureka dashboard looking like this:

![Pre Double up](/docs/images/doubleAcc1.jpg)

After we run the second instance of the accounts service, Eureka discovers this new instance of accounts and increases the numbers realted to the amount of instances from one to two

![Pre Double up](/docs/images/doubleAcc2.jpg)


## Sending request to web after killing the accounts service

If we attempt to do a request in the web to fetch an account by normal means, we can recieve the information of said account

![Pre Kill Web](/docs/images/accSearch1.jpg)
![Pre Kill Account](/docs/images/accSearch2.jpg)

But if we attempt to do so after killing the accounts service, although the web service will continue to work and attempt our request, we won't be able to access said information, ending up with a blank screen

![Post Kill Account](/docs/images/accSearch3.jpg)

If we check the Eureka dashboard we can confirm that the web service is still standing, but the account service has gone down

![Post Kill Dashboard](/docs/images/accSearch4.jpg)

## Can the web service provide information about the accounts again?

As of now, the web service can no longer provide us information about the accounts again, however, if we were to restart the accounts service, we'd be able to access information about the acounts again without the need to restart everything

![Post reset dashboard](/docs/images/reset1.jpg)

Once reset, we obtain this if we attempt again to get account information through the web service

![Eureka dashboard](/docs/images/reset2.jpg)