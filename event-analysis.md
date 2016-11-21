#Event structure

##Generic event structure:

###Data sent:
- applicationKey
- eventType
- subject/profileId (optional)
- object/targetItem

###Data received:
- generated

##Web Page view event:

###Data sent:
(generic event properties)
- referrer : String
- pageId : String
- pageName : String
- pagePath : String
- language : String
- tags : [String]
- interests : [String]

##Generic Form submission event:
###Data sent:
(generic event properties)
- formFields : [ { key, value, metadata { identifier, propertyMapping }]

##Contact request form submission event:
###Data sent:
(generic event properties)
- email: String!
- firstName: String
- lastName: String
- message: String!

##Purchase order event:
###Data sent:
(generic event properties)
- cartItems : [{itemId: String, price: Float, count: Integer, label: String}]
- shippingMethod : [String]
- shippingAddress : Address
- billingAddress : Address
- currency : String
- discounts : [String]
- tax : float
- importFees : float
