# Devices

Devices atau perangkat merupakan sebuah endpoint yang dimiliki oleh account. Devices adalah perangkat seperti mesin fax, SIP phone, softphone clients, dan cellphones(menggunakan fitur call forwarding).

#### Schema

#### API Verbs

## Mendapatkan daftar devices

> GET /v2/accounts/{ACCOUNT_ID}/device

```shell
curl -v -X GET \
    -X "X-Auth-Token: {AUTH_TOKEN} \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices
```

Hasilnya:

```json
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

## Membuat device baru

> PUT /v2/accounts/{ACCOUNT_ID}/devices

```shell
curl -v -X PUT \
    -H "X-Auth-Token: {AUTH_TOKEN} \
    -H "Content-Type: application/json" \
    -d '{"data":{"name":"New Device"}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices
```

Hasilnya:

```json
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
        "codecs": ["PCMU"]
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

## Menghapus device

> DELETE /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}

```shell
curl -v -X DELETE \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}
```

```json
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
        "codecs": ["PCMU"]
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

## Fetch a device

> GET /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}
```

```json
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
        "codecs": ["PCMU"]
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

## Change a device doc

Including `"sync":true` in the "data" will attempt to reboot the phone. See the sync section below.

> POST /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}

```shell
curl -v -X POST \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -H "Content-Type: application/json" \
    -d '{"data":{
        "name": "new device",
        "call_restriction": {},
        "caller_id": {},
        "contact_list": {},
        "dial_plan": {},
        "enabled": true,
        "exclude_from_queues": false,
        "media": {
            "audio": {"codecs": ["PCMU"]},
            "encryption": {"enforce_security": false, "methods": []},
            "video": {"codecs": []}
        },
        "music_on_hold": {},
        "mwi_unsolicited_updates": true,
        "register_overwrite_notify": false,
        "ringtones": {},
        "sip": {
            "invite_format": "username",
            "method": "password",
            "registration_expiration": 300
        },
        "suppress_unregister_notifications": false,
        "id": "4f3330e78e664bb57f8fb23fbaac2429"
        }}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}
```

```json
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
        "codecs": ["PCMU"]
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
    "name": "new device",
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

## Patch a device

> PATCH /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}

```shell
curl -v -X PATCH \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -d '{"data":{"presence_id":"dis_my_device"}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}
```

```json
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
        "codecs": ["PCMU"]
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
    "name": "new device",
    "presence_id": "dis_my_device",
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

## Send a SIP NOTIFY to a device

Kazoo will generate the NOTIFY packet if the device is registered.

PUT body options:

| Key          | Type       | Description                                        |
| ------------ | ---------- | -------------------------------------------------- |
| `action`     | `'notify'` | Perform the 'notify' action                        |
| `data.event` | `string()` | The value of the Event header in the NOTIFY packet |
| `data`       | `object()` | Parameters for the action                          |

> PUT /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}

```shell
curl -v -X POST \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -H "Content-Type: application/json" \
    -d '{"action": "notify",
         "data": {
           "event": "event"
         }
        }' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}/notify
```

## Fetch registration statuses of all devices

This will fetch the current registrations of any devices. If no devices are registered, an empty list will be returned.

> GET /v2/accounts/{ACCOUNT_ID}/devices/status

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/status
```

```json
{
  "auth_token": "{AUTH_TOKEN}",
  "data": [
    {
      "device_id": "{DEVICE_ID}",
      "registered": true
    }
  ],
  "request_id": "{REQUEST_ID}",
  "revision": "{REVISION}",
  "status": "success"
}
```

## Reboot a device

Some devices support receiving SIP NOTIFY packets with `event` = `check-sync`. This is typically used to reboot the phone if the configuration has changed. Kazoo will generate the NOTIFY packet if the device is registered.

> POST /v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}/sync

```shell
curl -v -X POST \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices/{DEVICE_ID}/sync
```

```json
{
  "auth_token": "{AUTH_TOKEN}",
  "data": "sync request sent",
  "request_id": "{REQUEST_ID}",
  "revision": "{REVISION}",
  "status": "success"
}
```

## Adding Ringtones

You can setup internal and external ringtones by adding this:

```json
{
  "name": "Device with custom ringtones",
  "ringtones": {
    "internal": "alert info SIP header",
    "external": "alert info SIP header"
  }
}
```

See, for instance, the [Polycom example](https://freeswitch.org/confluence/display/FREESWITCH/Polycom+Internal+Ring)

## Load a user's devices

Often you'll want to see what devices belong to a user, or devices that a user has hot-desked into.

Notice that the first device, `{DEVICE_ID_1}` is owned by `{USER_ID}` but the second device, `{DEVICE_ID_2}`, is owned by `{OWNER_ID}` **and** is currently hotdesked to `{USER_ID}` (see the `"hotdesked":true` attribute).

> GET /v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/devices

```shell
curl -v -X GET \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/users/{USER_ID}/devices
```

```json
{
  "auth_token": "{AUTH_TOKEN}",
  "data": [
    {
      "device_type": "sip_device",
      "enabled": true,
      "hotdesked": false,
      "id": "{DEVICE_ID_1}",
      "mac_address": "",
      "name": "USER_ID_DEVICE",
      "owner_id": "{USER_ID}"
    },
    {
      "device_type": "sip_device",
      "enabled": true,
      "hotdesked": true,
      "id": "{DEVICE_ID_2}",
      "mac_address": "",
      "name": "OWNER_ID_DEVICE",
      "owner_id": "{OWNER_ID}"
    }
  ],
  "request_id": "{REQUEST_ID}",
  "revision": "{REVISION}",
  "status": "success"
}
```

## Create an Authn-By-IP Device

Here is a minimal API request that creates a device that will authenticate by IP address instead of username/password

> PUT /v2/accounts/{ACCOUNT_ID}/devices

```shell
    curl -v -X PUT \
    -H "X-Auth-Token: {AUTH_TOKEN}" \
    -H "Content-Type: application/json" \
    -d '{"data":{"enabled":true,"name":"authn_by_ip","sip":{"invite_format":"e164", "ip":"{IP_ADDRESS}","method":"ip"}}}' \
    https://api.ofon.biz/v2/accounts/{ACCOUNT_ID}/devices
```

```json
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
        "codecs": ["PCMU"]
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
    "name": "authn_by_ip",
    "register_overwrite_notify": false,
    "ringtones": {},
    "sip": {
      "invite_format": "e164",
      "ip": "{IP_ADDRESS}",
      "method": "ip",
      "registration_expiration": 300
    },
    "suppress_unregister_notifications": false
  },
  "request_id": "{REQUEST_ID}",
  "revision": "{REVISION}",
  "status": "success"
}
```
