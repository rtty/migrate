## Pagination
Requesting paginated results across multiple pages is one of the most common use-cases in Countdown API.
For certain types of requests Countdown API allows you to return data across multiple pages automatically.
You can request a single page per-request, or have Countdown API automatically retrieve data from multiple pages and concatenate the results into one response.
:::hint{style=info}
API Credits and ```max_page```Each successfully retrieved page incurs an API credit.If the request yields fewer pages than specified, only credits for the actual number of returned pages are charged. For example, for a request with ```max_page```=5 that only yields 3 pages (because only 3 pages are available), then only 3 API credits are charged.
:::

### Single Pages
To request a single ```page``` of results you should use the ```page``` parameter. For example, making a request with ```page```=5 will return data from ```page``` 5.
To find the total number of pages, and determine whether a next page is available, inspect the ```pagination``` object in the result JSON.
:::hint{style=info}
Infinate Scrolling PaginationRequest types that implement infinate-scrolling pagination use a ```next_page_token``` parameter to request the next page of results. In these cases starting pagination from an explicit page number is not possible.
:::

### Multiple Pages
Countdown API provides the ```max_page``` parameter to retrieve mutliple pages of results and concatenate them into one response - automating workloads such as "get the first 5 pages of results, if they exist".
When running a request with ```max_page``` set, the main array property of the response contains a concatenation of the array values from all requested pages.
When using ``````max_page`````` Countdown API will retrieve the number of pages (if available) specified in the ``````max_page`````` parameter. Results from subsequent pages will be concatenated into the main array property of the response. For example, the following request would yield data from pages 1, 2, 3, 4 and 5:
The main array property of a request made with ```max_page``` will have the following properties added, making it easy to determine which physical page the current result came from:
Set the ```page``` to start the multiple-```page``` concatenation from by using the ```page``` and max_```page``` parameters together. For example, the following request would yield data from ```page```s 2, 3 & 4:
Set the ```page``` to start the multiple-```page``` concatenation from by using the ```page``` and max_```page``` parameters together. For example, the following request would yield data from ```page```s 2, 3 & 4: