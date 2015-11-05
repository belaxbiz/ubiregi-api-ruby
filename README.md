# 1. Prepare API Token

    See http://ubiregiinc.github.io/ubiregi-api/#authentication-token

# 2. Load UbiregiAPI library

    require "ubiregi_api"

Make sure library search path is configured properly.

# 3. Instantiate Client

    client = UbiregiAPI::Client.new(token)

'token' is that you created at #1

# 4. Send GET request

    client._get('customers')

# 5. Send POST request

    client._post('customers', post_data)

`post_data` must be a JSON transformable value (`Hash` or `Array`).

# 6. Retrieve Whole Collection

    client._index('customers', 'customers')

`_index` method can be used to retrieve all data included in a collection.
It understands `next-url` field included in the response, and send GET request again.

