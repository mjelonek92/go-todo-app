# Simple Go Todo REST APP
RESTful API for simple todo application written in Go.

## Project structure
```
├── app
│   ├── app.go
│   ├── handlers     
│   │   ├── common.go
│   │   └── tasks.go
│   └── models
│       ├── sql
│       │   └── init.sql
│       ├── db.gp
│       └── todo.go
├── config
│   └── config.go
└── main.go
```

## Instalatation
Download this project
```bash
go get github.com/mjelonek92/go-todo-app
cd $GOPATH/github.com/mjelonek92/go-todo-app
```

Install requirements using [glide](https://github.com/Masterminds/glide)
```
glide install
```

Create user and database
```bash
psql -c "CREATE USER tododb WITH PASSWORD `tododb`"
psql -c "ALTER USER tododb CREATEDB"
psql -c "CREATE DATABASE tododb WITH OWNER tododb"
```

Run SQL to create tables and relations.
```bash
psql -U tododb -f app/models/sql/*
```

Build and run
```bash
go build
./go-todo-app
```