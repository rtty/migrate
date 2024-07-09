## Error Logs API
The Error Logs API allows you to programmatically view failed API requests to understand what is causing them to fail.
Inspecting error logs can be useful to determine whether the cause of an API request failure relates to the API request itself or the host website being down or experiencing technical difficulties.
You can use the Error Logs API in combination with the  [SerpWow Status Page](https://serpwow.statuspage.io/) to inspect any open platform issues. You may also use the [Account API](https://www.serpwow.com/docs/account-api) to view live updates on any open API issues that may be causing requests to fail.
:::hint{style=info}
Which requests are shown in the Error Logs API?Real-time requests to the main API that result in an HTTP 500 [[response code](https://www.serpwow.com/docs/response-codes)](https://www.serpwow.com/docs/response-codes) are shown in the Error Logs API.Requests run via Batches, or requests that result in any other HTTP [[response code](https://www.serpwow.com/docs/response-codes)](https://www.serpwow.com/docs/response-codes) are not. For example, an ```HTTP 400``` that indicates an error in your request parameters, would not be shown in the Error Logs API.
:::

:::hint{style=info}
Error Log RetentionError Logs are retained, and available via the Error Logs API and [SerpWow dashboard](https://app.serpwow.com/errorlogs), for 3 days from the time that they last occurred. If the same request is retried and results in another error then the error log entry will increment its' ```count``` property to show the number of occurrances of that same error and the 3 day timer will reset.
:::

In addition to programmatic access to error logs via the Error Logs API you can also view error logs visually, in the [SerpWow dashboard](https://app.serpwow.com/errorlogs).
You can also request email updates when new error logs occur via the [SerpWow dashboard](https://app.serpwow.com/errorlogs).
Next Steps