# Devices

Devices atau perangkat merupakan sebuah endpoint yang dimiliki oleh account. Devices adalah perangkat seperti mesin fax, SIP phone, softphone clients, dan cellphones(menggunakan fitur call forwarding).

## Schema

## API Verbs

### Mendapatkan daftar devices

    GET /v2/accounts/{ACCOUNT_ID}/device

```
curl -v -X GET \
    -X "X-Auth-Token: {AUTH_TOKEN} \
    http://{SERVER}:8000/v2/accounts/{ACCOUNT_ID}/devices
```

Hasilnya:

```
{
    "auth_token": "{AUTH_TOKEN}",
    "data": [
        {
            "device_type": "sip_device",
            "enabled": false,
            "id": "{DEVICE_ID}",
            "mac_address": "00:04:f2:ab:7e:fd",
            "name": "MyPolycom"
        }
    ],
    "page_size": 1,
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```

### Membuat device baru

    PUT /v2/accounts/{ACCOUNT_ID}/devices

```
curl -v -X PUT \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    -H "Content-Type: application/json" \
    -d '{"data":{"name":"New Device"}}' \
    http://{SERVER}:8000/v2/accounts/{ACCOUNT_ID}/devices
```

Hasilnya:

```
{
    "auth_token": "{AUTH_TOKEN}",
    "data": {
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": true,
        "exclude_from_queues": false,
        "id": "{DEVICE_ID}",
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
        "mwi_unsolicited_updates": true,
        "name": "New Device",
        "register_overwrite_notify": false,
        "ringtones": {},
        "sip": {
            "invite_format": "username",
            "method": "password",
            "registration_expiration": 300
        },
        "suppress_unregister_notifications": false
    },
    "request_id": "{REQUEST_ID}",
    "revision": "{REVISION}",
    "status": "success"
}
```
