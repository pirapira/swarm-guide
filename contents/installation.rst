*************************
Installation and Updates
*************************

Installation
=======================
Swarm is part of the Ethereum stack, the reference implementation is currently at POC (proof of concept) version 0.2.

The source code is found on github: https://github.com/ethereum/go-ethereum/tree/master/

Supported Platforms
=========================

Geth runs on all major platforms (linux, MacOSX, Windows, also raspberry pi, android OS, iOS).

..  note::
  This package has not been tested on platforms other than linux and OSX.

Prerequisites
================

building the swarm daemon :command:`bzzd` requires the following packages:

* go: https://golang.org
* git: http://git.org


Grab the relevant prerequisites and build from source.

On linux (ubuntu/debian variants) use ``apt`` to install go and git

.. code-block:: none

  sudo apt install golang git

while on Mac OSX you'd use :command:`brew`

.. code-block:: none

    brew install go git

Then you must prepare your go environment as follows

.. code-block:: none

  mkdir ~/go
  export GOPATH="$HOME/go"
  echo 'export GOPATH="$HOME/go"' >> ~/.profile

Installing from source
=======================

Once all prerequisites are met, download the go-ethereum source code

.. code-block:: none

  mkdir -p $GOPATH/src/github.com/ethereum
  cd $GOPATH/src/github.com/ethereum
  git clone https://github.com/ethereum/go-ethereum
  cd go-ethereum
  git checkout master
  go get github.com/ethereum/go-ethereum

and finally compile the swarm daemon ``bzzd`` and the main go-ethereum client ``geth`` and (optionally) the bzz uploader ``bzzup`` and bzzhash calculator ``bzzhash``

.. code-block:: none

  go build ./cmd/bzzd
  go build ./cmd/geth
  go build ./cmd/bzzup
  go build ./cmd/bzzhash


You can now run :command:`./bzzd` to start your swarm node.


Updating your client
=====================

To update your client simply download the newest source code and recompile.

.. code-block:: none

  cd $GOPATH/src/github.com/ethereum/go-ethereum
  git checkout master
  git pull
  go build ./cmd/geth ./cmd/bzzd ./cmd/bzzup