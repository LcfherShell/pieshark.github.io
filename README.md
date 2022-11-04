<p align="center">
	<img src="https://github.com/LcfherShell/PieShark/raw/main/pieshark.png" width=200px height=200px>
</p>
<h2>PieShark</h2> is a small framework for creating secure APIs and is recommended using python 3.4^.

What you get from this framework:

- Cryptography

- NodeJS

- Fast HTTP Requests

- Javascript CDN

## Installation steps:
```console
$ pip install pieshark
```
## Simple Code:
```Python hl_lines="4  9-12  25-27"

from PieShark import pieshark, read_file, SESSION, Cookie, Templates, system, parser_url, nodejs, error_repport, cdn

error_res = error_repport()
app = pieshark()
app.config.update(dict(
	secret_key = 'qxn203jsj02',
	session_permanent=True,
	url_dbase='base://sqlite3:static'
	)
	)
session = SESSION(app=app, by=1)
cookie = Cookie(salt="tJHnN5b1i6wvXMwzYMRk128", app=app)

@app.route("/")
def home(request, response):
	session.insert['log'] = '222kkknk'
	cookie._Cookie__enc('data=nanda')
	templates = """
	<html>
	<head>
	    <link rel="stylesheet" href="static/example.css">
	</head>
	<body>
		Hello from the HOME {{ hello }}
	"""
	"""
		<script>
		{ obfusc_js }
		alert('sss');
		{ endobfusc_js }
		</script>
	"""

	cookie.crt(max_age=True, expires=True)
	cookie(response)
	response.headers['X-Frame-Options'] = 'SAMEORIGIN'
	response.headers['Content-Type'] = 'text/html'
	response.body = Templates(templates, hello="papa")#, jquery=deJS.script)


@app.route("/hello/{name}")
def greeting(request, response, name):
    response.text = f"Hello, {name}"
    
@app.route("/about")
def about(request, response):
	if 'log' in session.base and session.base:
		print(session.base['log'])

	if app.request.method == 'POST':
		print(app.form.tex)
		
	print(cookie.base(request).get('data'))
	
	response.headers['X-Frame-Options'] = 'SAMEORIGIN'
	response.headers['Content-Type'] = 'text/html'
	response.body = Templates('example.shark')

@app.route("/static/{name}")
def static(request, response, name):
	try:
		types, encoding = app.loads_files(name)
		stat = system.stat(name)
		text = read_file(name)
		response.headers['Content-Length'] = str(stat.st_size) 
		response.headers['Last-Modified'] = str(stat.st_mtime)
		response.headers['Content-Type'] =  types
		response.headers['Content-Encoding'] = encoding
		response.headers['Accept-Ranges'] = 'bytes'
	except:
		error_res.get_error()
		text = str('error_res')
		response.headers['Content-Type'] = 'text/plain'
	response.text = text



if __name__=='__main__':
	app.run()
```
