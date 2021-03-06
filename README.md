# nodebook ![](https://travis-ci.com/netgusto/nodebook.svg?branch=master)

Nodebook - Minimalist Node REPL with web UI

## What is it?

It's an in-browser REPL for Node.

Code's on the left, Console on the right. Click "Run" or press <kbd>Ctrl</kbd>+<kbd>Enter</kbd> or <kbd>Cmd</kbd>+<kbd>Enter</kbd> to run your code.
The code is automatically persisted on the file system.

![nodebook](https://user-images.githubusercontent.com/4974818/45084039-8f2b6380-b0fd-11e8-94d4-dadcab34c7f6.png)

The home lists the available notebooks. A notebook is a folder containing an `index.js` file.

![home](https://user-images.githubusercontent.com/4974818/45084276-3c9e7700-b0fe-11e8-9ed0-d2b7cb5b7bb3.png)

## Installation

```bash
$ git clone https://github.com/netgusto/nodebook
$ cd nodebook
$ npm install --production
```

## Usage

### Create a Notebook

In a directory where your notebooks will be stored, simply create a folder containing a file named `index.js`.
The dir name will be the notebook name.

### Run the REPL

```bash
# Default usage; local execution, bound to 127.0.0.1:8000
$ node . --notebooks path/to/notebooks
# open http://127.0.0.1:8000 in a browser
```

```bash
# Set bindaddress and port
$ node . --notebooks path/to/notebooks --bindaddress 0.0.0.0 -port 12000
```

```bash
# Execute code in disposable docker containers (node:alpine)
$ node . --notebooks path/to/notebooks --docker
```

#### Command line options

* **--notebooks**: path to notebook folders; required
* **--bindaddress**: IP address the http server should bind to; defaults to `127.0.0.1`
* **--port**: Port used by the application; defaults to `8000`
* **--docker**: Execute code in disposable docker containers instead of local system's Node; defaults to `false`

## ⚠️ A bit of warning ⚠️

Do not run this on a port open to public traffic! Doing so would allow remote code execution on your machine.

By default, the server binds to `127.0.0.1`, which allows connexion from the localhost only. You can override the bind address using `--bindaddress`, but do it only if you know what you're doing.

## Develop

To iterate on the code:

```bash
$ npm install
$ NOTEBOOKS=path/to/notebooks npm run dev
```

To build:

```bash
$ npm run build
```

To test:

```bash
$ npm test
```
