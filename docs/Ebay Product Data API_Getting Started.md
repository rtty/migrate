## Getting Started
Countdown API is an API to retrieve data from any Ebay domain worldwide in real-time. You can use Countdown API to retrieve [products](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/product), [reviews](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/reviews), [search](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/search), [autocomplete](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/autocomplete) and more from any Ebay [site](https://www.countdownapi.com/docs/ebay-product-data-api/reference/ebay-domains).
Countdown API executes requests in real time and returns clean, structured ```JSON``` or ```CSV```results. You can achieve fine-grained control over your request using the [request parameters](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/common).
:::hint{style=info}
Lookup an EPID by GTIN / ISBN / UPC / EANCountdown API can automatically convert GTIN/ISBN/UPC/EAN codes to Ebay EPIDs and return product data. For details of how to lookup Ebay product details by GTIN/ISBN/UPC/EAN please see refer to the [guide](https://www.countdownapi.com/docs/product-data-api/reference/gtin-upc-ean-to-epid).Note that Countdown API will cache the GTIN-to-EPID mapping for 2 months. To force a new GTIN lookup (for example, if you suspect the existing mapping is stale), use the ``````skip_gtin_cache=true`````` request parameter (note that using ``````skip_gtin_cache=true`````` decrements 2 credits from your balance, instead of 1).
:::

### Retrieving Search Results from Ebay
Getting Ebay data with Countdown API is as simple as making an HTTP ```GET``` ```request``` to the ```request``` endpoint. The only required parameters are```api_key```([sign up](https://app.countdownapi.com/signup) for free to get an API key) and ```type``` (which defines the ```type``` of Ebay data you'd like to retrieve).
For example, to retrieve search results (```type=search```) for the "memory cards" on ```ebay.com``` the Countdown API request would be:
:::::codeblocktabs
```http
```
:::::
        
The results of the Search request are shown below, the search results are within the ```search_results``` array. For full documentation on Search results see the [Search Results](https://www.countdownapi.com/docs/ebay-product-data-api/results/search) docs.
:::::codeblocktabs

:::::
        
:::hint{style=info}
Response Times & ConcurrencyCountdown API gathers data from Ebay in real-time and will typically return a result in 1-6 seconds. Please inspect the [HTTP Response Code](https://www.countdownapi.com/docs/response-codes) and update your app accordingly.If you need to run large volumes of requests consider using the [Collections API](https://www.countdownapi.com/docs/collections-api). Collections allow you to enqueue up to 15,000 requests, run them manually or on a schedule and execute them concurrently on Countdown API's infrastructure.
:::

### Getting Data for an Individual Product
Lets say we want to change our query to request a different type of data - information on a specific [product](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/product), in this case the EPID (Ebay [product](https://www.countdownapi.com/docs/ebay-product-data-api/parameters/product) identifier) ```233599133856``` on ```ebay.com```. Here's the Countdown API request to achieve that:
:::::codeblocktabs
```http
```
:::::
        
The result of the Product request is shown below. For full documentation on Product results see the [Product Results](https://www.countdownapi.com/docs/ebay-product-data-api/results/product) docs.
:::::codeblocktabs

:::::
        
Next Steps