## mongod --help

log mongod --help
Options:

General options:
  -h [ --help ]                         show this usage information
  --version                             show version information
  -f [ --config ] arg                   configuration file specifying
                                        additional options
  -v [ --verbose ] [=arg(=v)]           be more verbose (include multiple times
                                        for more verbosity e.g. -vvvvv)
  --quiet                               quieter output
  --port arg                            specify port number - 27017 by default
  --bind_ip arg                         comma separated list of ip addresses to
                                        listen on - localhost by default
  --bind_ip_all                         bind to all ip addresses
  --ipv6                                enable IPv6 support (disabled by
                                        default)
  --listenBacklog arg (=128)            set socket listen backlog size
  --maxConns arg                        max number of simultaneous connections
                                        - 1000000 by default
  --logpath arg                         log file to send write to instead of
                                        stdout - has to be a file, not
                                        directory
  --syslog                              log to system's syslog facility instead
                                        of file or stdout
  --syslogFacility arg                  syslog facility used for mongodb syslog
                                        message
  --logappend                           append to logpath instead of
                                        over-writing
  --logRotate arg                       set the log rotation behavior
                                        (rename|reopen)
  --timeStampFormat arg                 Desired format for timestamps in log
                                        messages. One of ctime, iso8601-utc or
                                        iso8601-local
  --pidfilepath arg                     full path to pidfile (if not set, no
                                        pidfile is created)
  --timeZoneInfo arg                    full path to time zone info directory,
                                        e.g. /usr/share/zoneinfo
  --keyFile arg                         private key for cluster authentication
  --noauth                              run without security
  --setParameter arg                    Set a configurable parameter
  --transitionToAuth                    For rolling access control upgrade.
                                        Attempt to authenticate over outgoing
                                        connections and proceed regardless of
                                        success. Accept incoming connections
                                        with or without authentication.
  --clusterAuthMode arg                 Authentication mode used for cluster
                                        authentication. Alternatives are
                                        (keyFile|sendKeyFile|sendX509|x509)
  --nounixsocket                        disable listening on unix sockets
  --unixSocketPrefix arg                alternative directory for UNIX domain
                                        sockets (defaults to /tmp)
  --filePermissions arg                 permissions to set on UNIX domain
                                        socket file - 0700 by default
  --fork                                fork server process
  --networkMessageCompressors [=arg(=disabled)] (=snappy)
                                        Comma-separated list of compressors to
                                        use for network messages
  --auth                                run with security
  --clusterIpSourceWhitelist arg        Network CIDR specification of permitted
                                        origin for `__system` access.
  --slowms arg (=100)                   value of slow for profile and console
                                        log
  --slowOpSampleRate arg (=1)           fraction of slow ops to include in the
                                        profile and console log
  --profile arg                         0=off 1=slow, 2=all
  --cpu                                 periodically show cpu and iowait
                                        utilization
  --sysinfo                             print some diagnostic system
                                        information
  --noIndexBuildRetry                   don't retry any index builds that were
                                        interrupted by shutdown
  --noscripting                         disable scripting engine
  --notablescan                         do not allow table scans

Replication options:
  --oplogSize arg                       size to use (in MB) for replication op
                                        log. default is 5% of disk space (i.e.
                                        large is good)

Master/slave options (old; use replica sets instead):
  --master                              master mode
  --slave                               slave mode
  --source arg                          when slave: specify master as
                                        <server:port>
  --only arg                            when slave: specify a single database
                                        to replicate
  --slavedelay arg                      specify delay (in seconds) to be used
                                        when applying master ops to slave
  --autoresync                          automatically resync if slave data is
                                        stale

Replica set options:
  --replSet arg                         arg is <setname>[/<optionalseedhostlist
                                        >]
  --replIndexPrefetch arg               specify index prefetching behavior (if
                                        secondary) [none|_id_only|all]
  --enableMajorityReadConcern [=arg(=1)] (=1)
                                        enables majority readConcern

Sharding options:
  --configsvr                           declare this is a config db of a
                                        cluster; default port 27019; default
                                        dir /data/configdb
  --shardsvr                            declare this is a shard db of a
                                        cluster; default port 27018

SSL options:
  --sslOnNormalPorts                    use ssl on configured ports
  --sslMode arg                         set the SSL operation mode
                                        (disabled|allowSSL|preferSSL|requireSSL
                                        )
  --sslPEMKeyFile arg                   PEM file for ssl
  --sslPEMKeyPassword arg               PEM file password
  --sslClusterFile arg                  Key file for internal SSL
                                        authentication
  --sslClusterPassword arg              Internal authentication key file
                                        password
  --sslCAFile arg                       Certificate Authority file for SSL
  --sslCRLFile arg                      Certificate Revocation List file for
                                        SSL
  --sslDisabledProtocols arg            Comma separated list of TLS protocols
                                        to disable [TLS1_0,TLS1_1,TLS1_2]
  --sslWeakCertificateValidation        allow client to connect without
                                        presenting a certificate
  --sslAllowConnectionsWithoutCertificates
                                        allow client to connect without
                                        presenting a certificate
  --sslAllowInvalidHostnames            Allow server certificates to provide
                                        non-matching hostnames
  --sslAllowInvalidCertificates         allow connections to servers with
                                        invalid certificates
  --sslFIPSMode                         activate FIPS 140-2 mode at startup

Storage options:
  --storageEngine arg                   what storage engine to use - defaults
                                        to wiredTiger if no data files present
  --dbpath arg                          directory for datafiles - defaults to
                                        /data/db
  --directoryperdb                      each database will be stored in a
                                        separate directory
  --noprealloc                          disable data file preallocation - will
                                        often hurt performance
  --nssize arg (=16)                    .ns file size (in MB) for new databases
  --quota                               limits each database to a certain
                                        number of files (8 default)
  --quotaFiles arg                      number of files allowed per db, implies
                                        --quota
  --smallfiles                          use a smaller default file size
  --syncdelay arg (=60)                 seconds between disk syncs (0=never,
                                        but not recommended)
  --upgrade                             upgrade db if needed
  --repair                              run repair on all dbs
  --repairpath arg                      root directory for repair files -
                                        defaults to dbpath
  --journal                             enable journaling
  --nojournal                           disable journaling (journaling is on by
                                        default for 64 bit)
  --journalOptions arg                  journal diagnostic options
  --journalCommitInterval arg           how often to group/batch commit (ms)

WiredTiger options:
  --wiredTigerCacheSizeGB arg           maximum amount of memory to allocate
                                        for cache; defaults to 1/2 of physical
                                        RAM
  --wiredTigerJournalCompressor arg (=snappy)
                                        use a compressor for log records
                                        [none|snappy|zlib]
  --wiredTigerDirectoryForIndexes       Put indexes and data in different
                                        directories
  --wiredTigerCollectionBlockCompressor arg (=snappy)
                                        block compression algorithm for
                                        collection data [none|snappy|zlib]
  --wiredTigerIndexPrefixCompression arg (=1)
                                        use prefix compression on row-store
                                        leaf pages

➜