0.5.0 (2026-11-04)
------------------
* fix: wait for the highest configured address during discovery (#21)
* fix: ignore ethercat switch ports (#14)
* fix: (index) indices in sdoWrite/sdoRead error case (#17)
* try to fix target exports
* small cmake fix
* added support for ROS2 lyrical (#10)
* fix memory leak
* hopefully fix segfault
* just to be sure increase the ioMap size even further
* added check for io map size
* change iomap buffer size to 2*4096
* Enabling the usage of an ethercat switch (#5)
* added extern C to forward declaration from SOEM
* update package to use soem_vendor as base (also updates the soem version)
* prevent deadlock at shutdown in case slave does low_level soem calls (introduced because recursive
  mutex removed.)
* cherry pick changes for updated soem_interface onto ament branch.
* old od utils, not very easy useable. error prone from sdk side.
* adjustments to support all sdks again, bit more consistency in slave state handling.
* - add abort flag for startup, so that waiting till all slaves are ready can be aborted. - better
  handle the waiting till all slaves are ready to hopefully avoid races on the slaves.. - parameter
  for numbers of retries and size check.
* read visible string correctly try to avoid startup with incomplete number of slaves (never kicked
  in during tests with 3 slaves, maybe more required so that more likely.)
* read visible string correctly.
* fixed context mutext deadlock
* - soem_rsl builds with colcon (one subfolder added) - soem_interface_rsl does not expose any
  symbols of SOEM. therefore (hopefully) safe to use with other SOEM based packages like BOTA or
  ANYbotics native stuff.    * pImpl Design Pattern to avoid deps headers in headers.    * only
  export marked symbols and don't inlcude the symbols of the statically linked soem_rsl    *
  soem_interface_rsl exported as shared library.    * replace recursive_mutex with mutex and
  implement (hopefully) consistent locking.
