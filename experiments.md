- Do a patch version upgrade from a PostgreSQL version. This is probably possible only in very old versions, where patch versions (3rd version number in semver) existed. For example, v9.6.18 to v9.6.19. Do this in
    - standalone server
    - Highly Aavailable (HA) system with primary and standby servers. Do it for all servers with a strategy
    - Sharded system with multiple servers and shareded data. Do it for all servers with a strategy

- Do a minor version upgrade from a PostgreSQL version. For example, v15 to v15.1. Do this in
    - standalone server
    - Highly Aavailable (HA) system with primary and standby servers. Do it for all servers with a strategy
    - Sharded system with multiple servers and shareded data. Do it for all servers with a strategy

- Do a major version upgrade from a PostgreSQL version. For example, v14.6 to v15.1. Do this in
    - standalone server
    - Highly Aavailable (HA) system with primary and standby servers. Do it for all servers with a strategy
    - Sharded system with multiple servers and shareded data. Do it for all servers with a strategy

- Ship WAL logs from a primary server to standby server
    - where Major version of Primary = Major version of Standby
        - Minor version of Primary = Minor version of Standby. And Patch version of Primary = Patch version of Standby, if patch version exists (like in old versions)
        - Minor version of Primary = Minor version of Standby. And Patch version of Primary != Patch version of Standby. This is probably possible only in very old versions, where patch versions (3rd version number in semver) existed. For example, v9.6.18 to v9.6.19.
        - Minor version of Primary != Minor version of Standby
            - Minor version of Primary < Minor version of Standby
            - Minor version of Primary > Minor version of Standby
    - where primary server's postgres version is not the same as standby server. That is, Major version of Primary != Major version of Standby
        - Major version of Primary < Major version of Standby
        - Major version of Primary > Major version of Standby
    
