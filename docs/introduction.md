# Introduction

SmartPBX menyediakan API supaya kita semua bisa mengembangkan unified telecom application. API dari SmartPBX menggunakan simple HTTP requests REST API.

Beberapa hal yang bisa dilakukan menggunakan SmartPBX REST API:

- Akses terhadap account dan sub-account. Menambahkan dan menghapus parameter.
- Mendapatkan daftar devices, users, dll. Menambahkan dan menghapus parameternya.
- Membuat Callflow untuk devices dan nomor telepon.
- Mengelola IVR, setting Jam Buka, membuat Menu, dan mengelola Voicemail Boxex.

## Langkah Awal

Setelah mendaftar Ofon paket SmartPBX, anda akan mendapatkan account dengan default setting dan nomor telepon. Akun tersebut sudah siap untuk digunakan dan dilengkapi dengan akses terhadap API maupun melalui portal SmartPBX. Berikut data yang akan anda dapatkan setelah mendaftar:

- Portal URL: `https://smartpbx.ofon.biz`
- API URL: `https://api.ofon.io:8443/v2/`
- username (berupa alamat email). contoh: john@example.com
- password
- account (merupakan nama organisasi atau company milik anda). contoh: JAYA LESTARI

## Akses REST API

API resource mempunyai parameter berikut tersedia di URL:

```
    https://api.ofon.io:8443/{VERSION}/accounts/{ACCOUNT_ID}/resources/{RESOURCE_ID}
```

- {VERSION}: saat ini menggunakan versi 2, yaitu v2
- {ACCOUNT_ID}: adalah id dari organisasi anda
- {RESOURCE_ID}: adalah id dari resource (devices, users, callflow, dll.)

Untuk melakukan API request, contoh mudahnya adalah menggunakan `curl`:

```
    $ curl -X GET \
     -H "X-Auth-Token: {AUTH_TOKEN}" \
     'https://api.ofon.io:8443/v2/accounts/{ACCOUNT_ID}
```

Penjelasan singkat:

- `-X GET` adalah perintah curl untuk melakukan HTTP GET Requests.
- `-H "X-Auth-Token: {AUTH_TOKEN}"` menambahkan header di HTTP Requests. Di sini menggunakan auth token untuk autentikasi.
- `https://api.ofon.io:8443/v2/` adalah URL dari API SmartPBX
- `v2` adalah versi API

Dengan menjalankan perintah di atas, akan didapatkan:

```
{
  "data": {
    "timezone": "Asia/Jakarta",
    "reseller_id": "{RESELLER_ID}",
    "realm": "{ACCOUNT_REALM}",
    "name": "{ACCOUNT_NAME}",
    "language": "en-US",
    "is_reseller": false,
    "descendants_count": 0,
    "created": 63636183145,
    "caller_id": {
      "internal": {
        "name": "My Awesome Office"
      },
      "external": {
        "name": "My Awesome Office"
      },
      "emergency": {
        "name": "My Awesome Office"
      }
    },
    "blacklists": [],
    "available_apps": [],
    "id": "{ACCOUNT_ID}",
    "knm_allow_additions": false,
    "superduper_admin": false,
    "enabled": true
  },
  "timestamp": "{TIMESTAMP}",
  "version": "{VERSION}",
  "node": "{API_NODE}",
  "request_id": "{REQUEST_ID}",
  "status": "success",
  "auth_token": "{AUTH_TOKEN}"
}
```

Response di atas akan berbeda tergantung dari setting account, dan resource apa yang diakses.
