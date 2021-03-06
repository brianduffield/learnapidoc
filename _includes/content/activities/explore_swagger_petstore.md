{: .activity_subtitle}
## <i class="fa fa-user-circle"></i> Activity: Explore Swagger UI through the Petstore Demo
{% if page.permalink == "/workshop.html" %}{:.no_toc}{% endif %}

Let's get some hands-on experience with Swagger UI using the Petstore demo. The Petstore demo provides a good example of how the OpenAPI specification can be rendered visually.

1.  Go to the [Swagger Pet Store Demo](https://petstore.swagger.io/).

    As with most Swagger-based outputs, Swagger UI provides a "Try it out" button. To make it work, you must first authorize Swagger by clicking **Authorize** and entering your API key in the Authorization modal. However, the Petstore authorization modal is just for demo purposes. There isn't any real code authorizing those requests, so you can close the Authorization modal or skip it altogether.

    {% include course_image.html url="http://petstore.swagger.io/" size="medium" filename="swaggerui_authorize" ext_print="png" ext_web="png" alt="Authorization modal in Swagger UI" caption="Authorization modal in Swagger UI" %}

2.  Expand the **<span style="padding: 3px; border-radius: 3px; background-color: #dedede">POST</span> `/pet`** endpoint.

    {% include course_image.html url="http://petstore.swagger.io/" size="large" filename="swaggerui_petendpoint" ext_print="png" ext_web="png" alt="POST /pet endpoint and Try it out button in Swagger UI" caption="POST /pet endpoint and Try it out button in Swagger UI" %}

3.  Click **Try it out**.

    After you click Try it out, the example value in the Request Body field becomes editable.

4.  In the example value, change the first `id` value to a unique (and unlikely to be repeated) whole number (such as `24329`). Change the name `doggie` to a pet name you can remember (e.g., `Bentley`).
5.  Click **Execute**.

    {% include course_image.html url="http://petstore.swagger.io/" size="large" filename="swaggerui_execute" ext_print="png" ext_web="png" alt="Executing a sample Petstore request" caption="Executing a sample Petstore request" %}

    Swagger UI submits the request and shows the [curl]({{site.rooturl}}docapis_make_curl_call.html) that was submitted. For example, here's the curl Swagger UI sent:

    ```curl
    curl -X POST "https://petstore.swagger.io/v2/pet" -H "accept: application/xml" -H "Content-Type: application/json" -d "{ \"id\": 1000, \"category\": { \"id\": 0, \"name\": \"string\" }, \"name\": \"Bentley\", \"photoUrls\": [ \"string\" ], \"tags\": [ { \"id\": 0, \"name\": \"string\" } ], \"status\": \"available\"}"
    ```

    Notice that, with the `-d` (data) parameter, the request body is escaped and added directly into the curl command rather than being loaded from a file (as explained in [Common curl commands related to REST]({{site.rooturl}}docapis_understand_curl.html#common)).

    The Responses section in Swagger UI shows the response from the server. By default, the response returns JSON:

    ```xml
    {
      "id": 1000,
      "category": {
        "id": 0,
        "name": "string"
      },
      "name": "Bentley",
      "photoUrls": [
        "string"
      ],
      "tags": [
        {
          "id": 0,
          "name": "string"
        }
      ],
      "status": "available"
      }
      ```

6.  The Petstore is a functioning API, and you have actually created a pet. For fun, expand the **<span style="padding: 3px; border-radius: 3px; background-color: #dedede">GET</span>/pet/{petId}** endpoint, click **Try it out**, enter the pet `id` you used in the previous operation, and then execute the request. You should see your pet's name returned.

{% if page.workshop_activities == true %}*For more information related to this activity, see [Introduction to the OpenAPI specification]({{site.rooturl}}pubapis_openapi_intro.html).*{% endif %}
