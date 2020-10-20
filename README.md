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
Jika menemui error, misal seperti berikut:
```
ERROR: Command errored out with exit status 1:
   command: ~/.venv/smartpbx-api-docs/bin/python3 -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-bs9fauvq/rstcheck/setup.py'"'"'; file='"'"'/tmp/pip-install-bs9fauvq/rstcheck/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(file);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, file, '"'"'exec'"'"'))' bdist_wheel -d /tmp/pip-wheel-90t0kac5
       cwd: /tmp/pip-install-bs9fauvq/rstcheck/
  Complete output (6 lines):
  usage: setup.py [global_opts] cmd1 [cmd1_opts] [cmd2 [cmd2_opts] ...]
     or: setup.py --help [cmd1 cmd2 ...]
     or: setup.py --help-commands
     or: setup.py cmd --help

  error: invalid command 'bdist_wheel'
  ----------------------------------------
  ERROR: Failed building wheel for rstcheck
  ```
  
  install [italic]Wheel[/italic] dengan cara:
  ```
  pip install wheel
  ```
  
Selanjutnya ntuk menggenerate content dalam bentuk html

```shell
$ cd docs
$ make html
```

Hasil generate html akan berada di folder `docs/_build`. Halaman utama adalah `index.html`. Dokumentasi ini dibuat menggunakan sphinx dan readthedocs.

Happy documenting!
