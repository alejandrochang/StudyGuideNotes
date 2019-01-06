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