#Event structure analysis and examples

This document contains an exploration of different event types and their structure, in order to analyze the requirements for event type definitions.

##Generic event structure

###Data sent
- applicationKey
- eventType
- subject/profileId (optional)
- object/targetItem

###Data received
- generated

##Web Page view event

###Data sent
(generic event properties)
- referrer : String
- pageId : String
- pageName : String
- pagePath : String
- language : String
- tags : [String]
- interests : [String]

##Generic Form submission event

A generic form may be either a statically or dynamically generated form, so the form fields may vary from one form to another.

###Data sent
(generic event properties)
- formFields : [ { key, value, metadata { identifier, propertyMapping }]

##Contact request form submission event

A specific form, which will require a custom event type. This event type, if generic enough, could be used by multiple systems that have the notion of contact requests.

###Data sent
(generic event properties)
- email: String!
- firstName: String
- lastName: String
- message: String!

##E-commerce order event

In the case of a e-commerce order, the purchased products (cart items) may be very different, and therefore the structure of the items may need to be defined as more or less complex sub-structures. 

###Data sent
(generic event properties)
- cartItems : [{itemId: String, price: Float, count: Integer, label: String}]
- shippingMethod : [String]
- shippingAddress : Address
- billingAddress : Address
- currency : String
- discounts : [String]
- tax : float
- importFees : float
