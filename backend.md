### Backend Overall Information and Misc. 

# What is Firebase Google?
Firebase is backend and infrastructure provided by google that gives you functionality like analytics, databases, messaging and crash reporting so you can move quickly. It is great for even big applications as it scales automatically. Overall it is a mobile and web application develoment platform. 

Essentially, it helps you host your own backend without writing too much server-side code. 

# What are Cloud Functions in Firebase?
Cloud functions are serverless event-driven code. Code runs upon certain events. It means that there is predictable executions, no idle time(cloud functions only run when we need them too, and we only pay when they do run - cost efficient) and the code environment only exist when needed. 

# Events on Firebase:
Firestore            -> onCreate, onUpdate, onDelete, onWrite           -> e.g. validate or transform data
Realtime Database    -> onCreate, onUpdate, onDelete, onWrite           -> e.g. validate or transform data
Authentication       -> onCreate, onDelete                              -> e.g. send welcome email
Google Analytics     -> onAnalyticsEvents                               -> e.g. write to database send notification
Crashlytics          -> onCrash or Issue detected                       -> e.g. write to database send notification
Cloud Storage        -> onChange [onObjects]                            -> e.g. image optimization
Pub Sub              -> onPublish                                       -> e.g. image optimization
HTTP                 -> onRequest                                       -> e.g. create REST endpoint (RESTFUL endpoints)

# What is Serverless?
Means you don't have to manage any code even thought there are still servers involved. It means as a developer you don't have to worry about updates, security (of server), it provides infinite scalability and separation of concerns. 


# What are the main differences between API and web service?
 
API and Web Services serve as a means of communication. The only difference is that a Web Servie facilitates interaction between two machines over a network. An API acts as an interface between two different applications so that they can communicate with each other. All Web Services are API's, but not all API's are Web Services. Web Services might not perform all the operations that an API would perform. A Web Service only uses three style of use SOAP, REST and XML_RPC, whereas an API can use any style of communication. A Web Service always needs a network for it's operation whereas an API doesn't. A Web Service is merely an API wrapped in HTTP.

# Is there any difference between PUT and POST operations?

Both PUT and POST can be used for creating. However, when deciding which one to use you have to ask yourtself "what are you performing the action to?". Better is to choose between PUT and POST based on idempotence of the action. 

PUT implies putting a resource - completely replacing whatever is available at the given URL with a different thing. By definition, PUT IS idempotent. You can do it as many times as you like and the result is always the same. YOU can PUT a resource whether it previously exist or not (eg. to Create or Update). POST updates a resource, adds a su resource or causes a change. A POST is NOT idempotent. 

PUT is for creating when you know the URL of the thing you will create. POST can be used to create when you know the URL of the "factory" of the category of things you're going to create. 

PUT /expense-report/45262

POST /expense-report

Idempotence: Is the property of certain operations whereby they can be applied multiple times without changing the result beyond the initial application. 