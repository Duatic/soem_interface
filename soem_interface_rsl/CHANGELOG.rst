^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package soem_interface_rsl
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.5.0 (2026-11-04)
------------------
* feat: support EtherCAT switches (#5)
* feat: support ROS 2 lyrical (#10)
* feat: build on soem_vendor, with its newer SOEM
* feat: build with ament for ROS 2
* feat: add object dictionary utilities for the SDKs
* feat: set the state of a single slave, with more consistent slave state handling
* feat: abort the wait for all slaves at startup, with parameters for the retries and the size check
* feat: check that the ioMap buffer is large enough
* fix: wait for the highest configured address during discovery (#21)
* fix: ignore EtherCAT switch ports (#14)
* fix: report the right indices in the sdoWrite and sdoRead error case (#17)
* fix: export the CMake target with ament_export_targets
* fix: free the list of network adapters after use
* fix: avoid a segfault when logging a slave's state
* fix: raise the ioMap buffer from 4096 to 16384 bytes
* fix: declare SOEM's ecx_detect_slaves extern "C"
* fix: prevent a deadlock at shutdown when a slave makes low level SOEM calls
* fix: read visible strings correctly
* fix: avoid starting up with fewer slaves than configured
* fix: remove a deadlock on the context mutex
* refactor: hide SOEM's symbols behind a pImpl and export only marked symbols, as a shared library
  that is safe to use beside other SOEM based packages
* refactor: replace the recursive mutex with a mutex and consistent locking
