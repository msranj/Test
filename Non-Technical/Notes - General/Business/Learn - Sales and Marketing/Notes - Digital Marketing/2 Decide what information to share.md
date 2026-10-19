# Decide what information to share
Reference :
- https://www.facebookblueprint.com/student/path/219717/activity/210125#/page/5febcff32910d9784c99da6a


    - Decide what information to share and how to share it using the Conversions API
    - learn how to share data responsibly by hashing contact information and removing prohibited and sensitive data.

## Matching events and customers
The Conversions API creates a direct connection between your marketing data and Meta. Examples of marketing data include 
- Website events, 
- App events, 
- Offline conversions and 
- Messaging events

    Matching these events with customers helps with:

    **Attribution**: Matching helps attribute more of your conversions and reduce your cost per result. 
    
    **Ad delivery**: Matching helps improve the delivery of ads to people who are more likely to take your desired action and attribute those actions back to your ads.



    ### Types of parameters
    There are two categories of data that the Conversions API enables you to share directly from your server.
    1. Server event parameters
    2. Customer information parameters

    #### Server event parameters
    These parameters contain information about actions that people take on your website, app, through messaging or in store. 
    
    Some examples include:
    
        Event_name : A standard event or custom event name that's used to deduplicate events.

        Event_time: A unix timestamp, indicated in seconds, that states when the actual event occurred.
        
        Action_source: A parameter that indicates where the conversion occurred.
        
        Client_user_agent: The user agent for the browser that corresponds to the event  

    Customer information parameters:

    these are a set of user identifiers to help match actions to accounts across Meta technologies
    
    Some examples include:

        em : Hashed email address

        client_ip_address: A valid IPV4 or IPV6 address of the browser corresponding to the event

        ph : Hashed phone number

        Other hashed contact information: Such as gender, birthdate, last name, first name, city, state, ZIP code and country


---
mapmap:
    colorfreezelevel:







