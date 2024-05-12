# Users

## About Users

Users represent just that, your users of the system. You can assign multiple devices to a user, put the user in a callflow, and all devices will ring.

#### Schema

## Fetch

> GET /v2/accounts/{ACCOUNT_ID}/users

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users
{
    "auth_token": "{AUTH_TOKEN}",
    "data": [
        {
            "email": "user1@account_realm.com",
            "features": [
                "caller_id",
                "vm_to_email"
            ],
            "first_name": "User",
            "id": "{USER_ID}",
            "last_name": "One",
            "priv_level": "admin",
            "timezone": "America/Los_Angeles",
            "username": "user1@account_realm.com"
        },
        {
            "email": "user2@account_realm.com",
            "features": [
                "caller_id",
                "vm_to_email"
            ],
            "first_name": "User",
            "id": "{USER_ID}",
            "last_name": "Two",
            "priv_level": "user",
            "timezone": "America/Los_Angeles",
            "username": "user2@account_realm.com"
        }
    ],
    "page_size": 2,
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Create a new user

> PUT /v2/accounts/{ACCOUNT_ID}/users

```shell
curl -v -X PUT \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    -H "Content-Type: application/json" \
    -d '{"data":{"first_name":"User", "last_name":"Three"}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": true,
        "first_name": "User",
        "hotdesk": {
            "enabled": false,
            "keep_logged_in_elsewhere": false,
            "require_pin": false
        },
        "id": "{USER_ID}",
        "last_name": "Three",
        "media": {
            "audio": {
                "codecs": [
                    "PCMU"
                ]
            },
            "encryption": {
                "enforce_security": false,
                "methods": []
            },
            "video": {
                "codecs": []
            }
        },
        "music_on_hold": {},
        "priv_level": "user",
        "profile": {},
        "require_password_update": false,
        "ringtones": {},
        "verified": false,
        "vm_to_email_enabled": true
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Remove a user

This request will return the current JSON object of the now-deleted user.

> DELETE /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}

```shell
curl -v -X DELETE \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": false,
        "first_name": "User",
        "hotdesk": {
            "enabled": false,
            "keep_logged_in_elsewhere": false,
            "require_pin": false
        },
        "id": "{USER_ID}",
        "last_name": "Three",
        "media": {
            "audio": {
                "codecs": [
                    "PCMU"
                ]
            },
            "encryption": {
                "enforce_security": false,
                "methods": []
            },
            "video": {
                "codecs": []
            }
        },
        "music_on_hold": {},
        "priv_level": "user",
        "profile": {},
        "require_password_update": false,
        "ringtones": {},
        "verified": false,
        "vm_to_email_enabled": true
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Fetch a user

> GET /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": true,
        "first_name": "User",
        "hotdesk": {
            "enabled": false,
            "keep_logged_in_elsewhere": false,
            "require_pin": false
        },
        "id": "{USER_ID}",
        "last_name": "Three",
        "media": {
            "audio": {
                "codecs": [
                    "PCMU"
                ]
            },
            "encryption": {
                "enforce_security": false,
                "methods": []
            },
            "video": {
                "codecs": []
            }
        },
        "music_on_hold": {},
        "priv_level": "user",
        "profile": {},
        "require_password_update": false,
        "ringtones": {},
        "verified": false,
        "vm_to_email_enabled": true
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Patch a user's doc

> PATCH /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}

```shell
curl -v -X PATCH \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -H "Content-Type: application/json" \
    -d '{"data":{"enabled":false}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": false,
        "first_name": "User",
        "hotdesk": {
            "enabled": false,
            "keep_logged_in_elsewhere": false,
            "require_pin": false
        },
        "id": "{USER_ID}",
        "last_name": "Three",
        "media": {
            "audio": {
                "codecs": [
                    "PCMU"
                ]
            },
            "encryption": {
                "enforce_security": false,
                "methods": []
            },
            "video": {
                "codecs": []
            }
        },
        "music_on_hold": {},
        "priv_level": "user",
        "profile": {},
        "require_password_update": false,
        "ringtones": {},
        "verified": false,
        "vm_to_email_enabled": true
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Change the user doc

This requires posting the full user's document in the request body

**Sync**: See [the documentation on device sync](#sync) for more info on `check-sync`. One can add the field `"sync": true` to the JSON document in order to attempt a `check-sync` on every registered device this user has.

> POST /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}

```shell
curl -v -X POST \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -H "Content-Type: application/json" \
    -d '{"data":{"first_name":"User","last_name":"Three","call_restriction":{},"caller_id":{},"contact_list":{},"dial_plan":{},"enabled":false,"hotdesk":{"enabled":false,"keep_logged_in_elsewhere":false,"require_pin":false},"media":{"audio":{"codecs":["PCMU"]},"encryption":{"enforce_security":false,"methods":[]},"video":{"codecs":[]}},"music_on_hold":{},"priv_level":"user","profile":{},"require_password_update":false,"ringtones":{},"verified":false,"vm_to_email_enabled":true}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": false,
        "first_name": "User",
        "hotdesk": {
            "enabled": false,
            "keep_logged_in_elsewhere": false,
            "require_pin": false
        },
        "id": "{USER_ID}",
        "last_name": "Three",
        "media": {
            "audio": {
                "codecs": [
                    "PCMU"
                ]
            },
            "encryption": {
                "enforce_security": false,
                "methods": []
            },
            "video": {
                "codecs": []
            }
        },
        "music_on_hold": {},
        "priv_level": "user",
        "profile": {},
        "require_password_update": false,
        "ringtones": {},
        "verified": false,
        "vm_to_email_enabled": true
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

## Fetch (or create) a vCard

[vCard](https://en.wikipedia.org/wiki/VCard) is a file format typically used in emails as a form of business card. Kazoo currently generates a 3.0 compatible vCard.

> GET /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/vcard

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    -H "Accept: text/x-vcard"
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/vcard
BEGIN:VCARD
VERSION:3.0
FN:User Three
N:Three;User
END:VCARD
```

## Remove the photo from the user

> DELETE /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo

```shell
curl -v -X DELETE \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo
```

## Fetch the user's photo, if any

Set the `Accept` header to either `application/base64` or `application/octet-stream` to retrieve the picture's contents.

If the result is successful, you will want to pipe the response into a file.

> GET /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo

```shell
curl -v -X GET \
    -H "Accept: application/base64" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo
[binary data]
```

## Create or change the user's photo

Use `application/octet-stream` as the content type.

> POST /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo

```shell
curl -v -X POST \
    -H "Content-Type: application/octet-stream" \
    --data-binary @/path/to/image.jpg \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/photo
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {},
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```
