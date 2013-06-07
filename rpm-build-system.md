Dead-Simple RPM Build System
=============================

- dead simple RPM build system with minimal overhead/dependencies but good
  features
- written in Python or Perl, something that's powerful, interpreted, and
  likely to be everywhere, even on disparate distros or older systems (think,
  we want to build for RHEL 5.0)
- based on a message queue (celery?) passing around job information
- shared (NFS, or something similar) storage OR a http API for getting
  SRPMs/specs/etc. and returning built packages
- web UI, CLI and API for build jobs/status, etc.
- easy way to add a successful build to a yum repo
- build slaves have metadata stored including a list of tags
- build jobs set with a list of tags, can be required or ORed together
- job is put in the new jobs queue
- "ping" is sent for a build node that meets the specified tags (distro, arch,
  etc.). if none is found in X seconds, DB is queried, virtualization library
  is used to turn one on or create one (vagrant)
