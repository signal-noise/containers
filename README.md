> Docker images for use in CI

Based on Alpine distros, with tooling for compatibility with CircleCI and GCP as well as
AWS.

Note that this repo will autobuild to the GCP GCR public container repository, which can
be used in your CI scripts - e.g. at `eu.gcr.io/signalnoise/base:14`

Different top level folders on this repo represent different Docker Hub 'Repositories',
while folders represent version numbers, exposed as tags within the docker repo system. 
Branches and tags in Git / Github are not used.

Note that the `base` container repo/folder is built on the official *NodeJS* container.