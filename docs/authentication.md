# Authentication

Hampir seluruh akses terhadap SmartPBX API membutuhkan akun credentials. Untuk itu, dibutuhkan langkah autentikasi sehingga mendapatkan token yang bisa digunakan untuk melakukan akses terhadap resource-resource smartpbx ofon.

## User Authentication

Langkah mudah untuk melakukan autentikasi dan mendapatkan token adalah sebagai berikut:

Sebagai persiapan, anda harus mempunyai username, password, dan account name yang digunakan untuk login ke dalam portal smartpbx. Selanjutnya, anda perlu mengubah username dan password anda menjadi credentials yang berupa MD5/SHA1 hash. Sebagai contoh, jika username anda adalah john@example.com dan password anda adalah `m32c6NfqYEt` maka credentials anda adalah hash dari `john@example.com:m32c6NfqYEt` (tanda : sebagai pemisah antara username dan password) yaitu: `82a2dc91686ec828a67152d45a5c5ef7`.

Cara melakukan generate MD5 hash di terminal linux maupun MacOS seperti berikut:

```
    $ echo -n 'john@example.com:m32c6NfqYEt' | md5sum
    82a2dc91686ec828a67152d45a5c5ef7  -
```

Jika menggunakan SHA1, maka terminal command yang digunakan yaitu `shasum`.

Setelah mendapatkan creadentials, maka bisa menggunakan `user_auth` API untuk mendapatkan token.

```
    $ curl -v -X PUT \
      -H "Content-Type: application/json" \
      -d '{"data":{"credentials":"82a2dc91686ec828a67152d45a5c5ef7", "account_name":"{ACCOUNT_NAME}", "method":[md5|sha1]}' \
      https://api.ofon.io:8443/v2/user_auth
```

Jika berhasil, maka akan mendapatkan respon berikut:

```
    {
        "auth_token": "{AUTH_TOKEN}",
        "data": {
            "account_id": "{ACCOUNT_ID}",
            "apps": [],
            "is_reseller": true,
            "language": "en-US",
            "owner_id": "{OWNER_ID}",
            "reseller_id": "{RESELLER_ID}"
        },
        "node": "{API_NODE}",
        "request_id": "{REQUEST_ID}",
        "revision": "{REVISION}",
        "status": "success",
        "timestamp": "{TIMESTAMP}",
        "version": "{VERSION}",
    }
```

{AUTH_TOKEN} adalah token yang berupa list karakter yang bisa digunakan untuk mengakses API-API lain.

