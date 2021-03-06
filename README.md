[![CleverTap Logo](http://staging.support.wizrocket.com.s3-website-eu-west-1.amazonaws.com/images/CleverTap_logo.png)](http:www.clevertap.com)


CleverTap is the next generation app engagement platform. It enables marketers to identify, engage and retain users and provides developers with unprecedented code-level access to build dynamic app experiences for multiple user groups. CleverTap includes out-of-the-box prescriptive campaigns, omni-channel messaging, uninstall data and the industry's largest FREE messaging tier.

For more information check out our [website](https://clevertap.com "CleverTap") and [documentation](http://support.clevertap.com "CleverTap Technical Documentation").

To get started with CleverTap, [sign up](https://clevertap.com/sign-up) for a free account.  

# CleverTap Server API

The CleverTap Server API is a REST API that supports various endpoints to record or return user profiles and actions.

Server API requests must be over HTTPS and must include your CleverTap Account ID and CleverTap Passcode. These are available in your Dashboard -> Settings -> Integration -> Account ID, SDKs.

For more information please see our [Server API documentation](https://support.clevertap.com/server/overview/).

# Examples

## Python

A basic example Python class that wraps the Server API is included [here](https://github.com/CleverTap/clevertap-server-api-examples/blob/master/python/api_v1/clevertap.py).

To use this example class, manually install it in your project's python path and import accordingly.

### Example Python Wrapper Class Usage

    from clevertap import CleverTap

    clevertap = CleverTap(YOUR_CT_ACCOUNT_ID, YOUR_CT_ACCOUNT_PASSCODE)

    # upload an array of user profiles and/or user action events
    res = clevertap.upload(data)

    # download user profiles based on a JSON query
    res = clevertap.profiles(query)

    # download user action events based on a JSON query
    res = clevertap.events(query)

You can find more on example usage in the included unit tests [here](https://github.com/CleverTap/clevertap-server-api-examples/blob/master/python/api_v1/tests.py).

#### Push Notification Targets API Usage

    from clevertap import CleverTap

    clevertap = CleverTap(YOUR_CT_ACCOUNT_ID, YOUR_CT_ACCOUNT_PASSCODE)

    # create a new push notification target
    res = clevertap.targets(clevertap.TargetActions.CREATE, payload)

    # estimate reach on a potential target (returns an estimate, doesn't create)
    res = clevertap.targets(clevertap.TargetActions.ESTIMATE, payload)

    # list created targets
    res = clevertap.targets(clevertap.TargetActions.LIST, payload)

    # stop a running target
    res = clevertap.targets(clevertap.TargetActions.STOP, payload)

    # get the results of a target
    res = clevertap.targets(clevertap.TargetActions.RESULT, payload)

You can find more on example push targets usage in the included unit tests [here](https://github.com/CleverTap/clevertap-server-api-examples/blob/master/python/api_v1/push_target_tests.py).

