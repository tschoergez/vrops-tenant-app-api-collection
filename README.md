
# vRealize Operations Tenant App API collection for Postman


## Overview

vRealize Operations Tenant App provides a REST API for programatic access to pricing policies, bills and raw metrics in the vRealize Operations API.
The API is documented on the Tenant App itself in https://<tenantapp>/tenant-app-api/swagger-ui.html

### Prerequisites

* [Postman Client](https://www.getpostman.com/)
* [vRealize Operations Tenant App 2.4+](https://marketplace.vmware.com/vsx/solutions/management-pack-for-vcloud-director#resources)

### Using the Samples

1. Download the Postman collection file from the Samples folder
2. Import the collection file into Postman
3. Define your vRealize Operations environment.  At a minimum the environment needs to contain:

  * user: *your vRealize Operations user account*
  * pass: *your vRealize Operations user password*
  * tentantapp: *IP or hostname of the vRealize Operations Tenant App*

For example:

```
user : admin
pass : VMware1!
tenantapp : 192.168.1.50
```
Be aware that the user usually is the provider admin user also used for during setup (configured in vRealize Operations)

Additional environment vars will be created by some of the API samples.  There is usually no need to edit those.

Start with the "RUN FIRST - Get vROPS Auth Token" call, to authenticate. The token will be stored in a postman variable and used for subsequent API calls.
Some examples use the "/suite-api" endpoint that allows to retrieve raw data from vRealize Operations. Refer to the [vRealize Operations API Documentation](https://code.vmware.com/apis/364/vrealize-operations) for details.
