## Locations API Overview
The SerpWow Locations API allows you to search for SerpWow supported Google & Bing search ```location```s. You can supply the```full_name```returned by the Locations API as the```location```parameter in a [Search API](https://www.serpwow.com/docs/search-api) query to retrieve search results localized to that ```location```.
:::hint{style=info}
The Locations API is Free of ChargeThere is no charge for usage of the Locations API and requests to it will not decrement your monthly search credits. However, to guarantee quality of service to all customers, we do apply a rate limit of 120 requests per minute.
:::

To search for the location```london```the SerpWow Locations API request would be:
:::::codeblocktabs
```http
```
:::::
        
Here are the results from the re```q```uest above, note that the```locations```array contains the SerpWow supported ```locations``` matching the ```q```uery supplied in the```q```parameter.
:::::codeblocktabs

:::::
        
Lets say we want to refine our location query to search for locations matching```london```that are cities within Great Britain. To do that we use the```type```and```country_code```parameters:
:::::codeblocktabs
```http
```
:::::
        
Note that the results now reflect just cities within the GB country code.
:::::codeblocktabs

:::::
        
### Running a Search Specifying a Location
You can pass the fully qualified (``````full_name``````) Location name into the``````location``````parameter of a Search API request to retrieve search results from that ``````location``````. In the example below we are passing the Location of```Greater London,England,United Kingdom```, as retrieved from the``````full_name``````property in the Locations API response, in the Search API``````location``````parameter:
:::::codeblocktabs
```http
```
:::::
        