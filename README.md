# DNS Relay Server

A C-language DNS relay implementation developed for a computer-networks course project.

## Features

- UDP DNS request relay on port 53
- DNS packet parsing and response construction
- A, AAAA, CNAME, MX, NS, and TXT record support
- Threaded request handling
- LRU cache with TTL-aware cleanup
- Local host mapping and configurable upstream DNS server
- Windows Winsock and POSIX socket compatibility

## Build

Compile the files in `src/` with the headers in `include/`. On Windows, link against Winsock (`Ws2_32`). The implementation also uses pthread APIs.

> Binding to port 53 commonly requires administrator privileges. Use only on networks and systems you are authorized to administer.

## Layout

- `src/Server/` — sockets, server lifecycle, and local mappings
- `src/Service/` — packet parsing, query flow, cache, and host operations
- `src/Utils/` — threading, networking, and hash utilities
- `include/` — public headers and DNS protocol definitions
