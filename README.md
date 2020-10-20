# smartpbx-api-docs

Ini adalah dokumentasi API smartpbx.

Petunjuk:

```shell
$ sudo apt install python3-virtualenv
$ python3 -m venv ~/.venv/smartpbx-api-docs
$ source ~/.venv/smartpbx-api-docs/bin/activate
$ git clone git@github.com:ofonid/smartpbx-api-docs.git
$ cd smartpbx-api-docs
$ pip install -r requirements.txt
```

Untuk menggenerate content dalam bentuk html

```shell
$ cd docs
$ make html
```

Hasil generate html akan berada di folder `docs/_build`. Halaman utama adalah `index.html`. Dokumentasi ini dibuat menggunakan sphinx dan readthedocs.

Happy documenting!
