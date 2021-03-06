# RELEASE NOTES

## v0.2.0-release
### Features

* Added job queuing to support many concurrent commits, without breaking AS3.
* Improved error handling.
* Replaced native http calls with GitHub's octokit node_module. 
* Added a 'commit link' which references the origin service-definition commit into the GitHub Issue success/fail response. Clicking this link will take you directly to the commit 'diff'.

### Fixes

* Mega refactor to break down some big functions, and eliminate some callback hell (promisified everything).
* Implemented Queuing to asynchonously hand declarations to AS3.

### Known Issues

* Maximum concurrent unique service definitions committed at one time is unknown. The `queue_length` has not been tested beyond `10`.

---
## v0.1.0-release

With this iControl LX worker, F5 AS3 Service definitions commited to a GitHub Enterprise repository, with a GitHub Webhook destination of this worker `/ghe_listener`, will be deployed/modified/deleted on desired BIG-IP devices (physical or virtual).
This practice is known as Network Infrastructure as Code.

### Features

* F5 AS3 Service definitions commited to GitHub Enterprise repository, with webhook destination of this worker, will be deployed/modified/deleted on desired BIG-IP devices (physical or virtual).
* Upon completion, the iControl LX worker will create a GitHub Issue in the source repository containing the results of the interaction with AS3.

### Fixes

None - first release

### Known Issues

Limited error handling. Just Shit It :)
