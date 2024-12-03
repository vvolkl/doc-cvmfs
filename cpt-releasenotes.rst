

Release Notes for CernVM-FS 2.12.0
==================================

CernVM-FS 2.12.0 is a sizeable feature release with new features, bug fixes and performance improvements, 

Highlights are:

* Support for FUSE-T on MacOS, allowing for easy installation without security tweaks

* Refcounted Cache Manager now the default

* Fully-featured Streaming Cache Manager for data / files that should not be cached

* Support for Metalink server discovery

* Several fixes in the fuse internals, for example the page cache tracker


As with previous releases, upgrading clients should be seamless just by
installing the new package from the repository. As usual, we recommend updating only a few worker nodes first and gradually ramp up once the new version proves
to work correctly. Please take special care when upgrading a cvmfs client in NFS mode.

For Stratum 1 servers, there should be no running snapshots during the upgrade.
For publisher and gateway nodes, all transactions must be closed; no active leases must be present before upgrading.

Packages are available for both the x86_64 and aarch64 architectures, for current debian- and rhel-based distros.




Bug fixes
---------

  * [client] Add "cache limit set <MB>" function to cvmfs_talk (#3623) 
  * [client] Fix replacement of stale inodes (#3507)
  * [client] Print correct timezone in logbuffer (#3679)
  * [client] log NOTFOUND in tracefile when lookup unsuccessful (#3704)
  * [client] Close page cache tracker entry if cvmfs_open() fails (#3588)
  * [client] Remove unnecessary remount fence in forget callback (#3591)
  * [client] Move getxattr check of valid return value closer to its request (#3516)
  * [client] Improve error logging in inode tracker (#3502)
  * [client] Fix a few Log2Histogram bugs (#3511)
  * [client] Reduce write lock contention in catalog mgr (#3476)
  * [client] Log JobInfo object id and its respective CURL requests (#3492)
  * [client] Avoid possible race in mount helper (#3475)
  * [server] Ingest Tarball now with modifiyable ownership (#3362)
  * [server] Fixes and improvements to concurrency in SessionContext (#3546)
  * [server] Fix race when publishing to a gateway (#3546)
  * [server] Consistently use 64bit ints for catalog revision (#3478)
  * [server] Create scratch dir with consistent permissions (#3660)
  * [rpm] Fix externals for RISC-V build (#3446)
  * [service container] use all env vars in config (#3677)





Improvements and changes
------------------------

  * [client] Better logging for host/proxies (#3617)
  * [client] FUSE-T support for macOS (#3587)
  * [server] Add metalink support (#3683)
  * Add support for high-precision timestamps (#3513)
  * [client] Turn CVMFS_CACHE_REFCOUNT on by default (#3684)
  * [client] Add memory buffer to streaming cache manager (#3632)
  * [client] Add "cache limit set <MB>" function to cvmfs_talk (#3623)
  * [client] add eio.emfile counter for  open() operations (#3625)
  * [server] mkfs: do not overwrite existing manifest in s3 bucket (#3693) 
  * [server] allow absolute paths for ingest --base_dir and --to_delete (#3695)
  * [ducc] Enable syncronous GC on webhook (#3646)
  * [gw] Cache catalogs for cvmfs_receiver (#3431)
  * [rpm] Run post-install reload in a unit (#3707) 
  * [client] Support for the new CVMFS_FUSE3_IDLE_THREADS and CVMFS_FUSE3_MAX_THREADS parameters (#3505)
  * [client] Add paging to xattr (#3355)
