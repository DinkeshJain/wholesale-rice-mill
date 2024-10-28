# wholesale-rice-mill

# Creating Apex Classes :

Apex classes are modeled on their counterparts in Java. You’ll define, instantiate, and extend classes, and you’ll work with interfaces, Apex class versions, properties, and other related class concepts.

Class:
As in Java, you can create classes in Apex. A class is a template or blueprint from which objects are created. An object is an instance of a class.

Object:
Object is an instance of a class, where it can access all the properties that are present in a class i.e, variables and methods.


# Apex Class:
Here, this Apex class is used to automate the sending of email notifications to a list of consumers for encouraging further engagement with personalized messaging.

We take a List with 'consumer__c' object datatype named 'con' which contains the list of all the consumers.

The steps of email creation are:
1. Creates a new SingleEmailMessage instance.
2. Sets the ToAddresses to the consumer’s email (c.email__c).
3. Sets the subject of the email to "Welcome to our company".
4. Constructs a personalized welcome message in the PlainTextBody of the email, encouraging the consumer to shop more with the company and highlighting the benefits of being a valuable customer.

The message is sent through email to every consumer by 'Messaging.sendEmail'

# Apex Triggers:
Apex Triggers in this case are used to automatically send a welcome email to consumers right after they have been inserted into the system, ensuring immediate engagement with the new customers.

The trigger is set to execute only after the insert operation on 'consumer__c'. The 'if' conditions exist to check whether the trigger runs only in 'after insert' context.

As soon as an insert operation occurs, the trigger calls the 'sendEmailNotification' method from 'ConsumerRecord' class, passing 'trigger.new' as an argument (list of new consumer records) which sends them the welcome message written in the ConsumerRecord class.