# Selfhost Dashboard

A dashboard for `selfhost` package from [Cryptoanarchy Debian Repository](https://deb.ln-ask.me).

## About

**WORK IN PROGRESS!!! NOT production-ready!!! Dependencies not reviewed!**

This provides a simple dashboard for users to launch apps.

### Features

* Signup on first open
* Login
* Open app

### TODO

- [ ] frontend
- [ ] icon paths
- [ ] opening dynamic apps
- [ ] logout
- [ ] more tests
- [ ] cleanup (fix clean architecture)
- [ ] more doc
- [ ] integrate into the repository
- [ ] migrate existing apps to use the dashboard

## Testing

### Mocking DB and system paths (recomended for initial development)

`cargo run --features mock_system -- --conf config_example.toml`

Open `http://localhost:9009/dashboard`, enter `admin` as username, pick any password and click submit.
Dashboard should open after registration finishes.
GET `/apps` to see app data (the icon paths are messed up right now)

### Real DB and paths

0. install postgress (`apt install postgresql`)
1. create user `selfhostdashboard` (`sudo -u postgres psql 'CREATE ROLE selfhostdashboard LOGIN PASSWORD 'satoshinakamoto';'`)
2. create database `selfhostdashboard` (`sudo -u postgres psql 'CREATE DATABASE selfhostdashboard OWNER selfhostdashboard;'`)
3. `cargo run -- --conf config_example.toml`

## Contributing

Please don't open issues yet.
There will be frequent chages.
PRs to fix obvious bugs are fine.

## MSRV

`1.41.1` (as present in Debian Buster)