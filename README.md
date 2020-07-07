
# vRealize Operations Tenant App API collection for Postman


## Overview

vRealize Operations Tenant App provides a REST API for programatic access to pricing policies, bills and raw metrics in the vRealize Operations API.
The API is documented on the Tenant App itself in https://<tenantapp>/tenant-app-api/swagger-ui.html
 
The easiest way to get started is using the Postman Client to try out the APIs.  Postman allows you to export code samples in many scripting and programming languages, so the purpose of this repository is to provide examples in a generic format using Postman.


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
Some examples use the "/suite-api" endpoint that allows to retrieve raw data from vRealize Operations. Refer to the [vRealize Operations API Documentation](https://code.vmware.com/apis/364/vrealize-operations) for details, and check out the [Postman collection for vRealize Operations](https://code.vmware.com/samples/4663/postman-client-collection-for-vrealize-operations-rest-apis)

### Tenant Activation
To publish Tenant App into the VCD tenant portal for an Org, run the "Activate Tenant - Step ..." calls:

1. Create a User Role for VCD Tenant Admin users in vROPS (only has to be done once)
2. Find the org and its IDs (name, UUID, resourceId). When this call succeeds, check the "Visualization" tab in postman's reponse area for a nice table view of all orgs (of the first response page)
3. Delete an existing user for this Org (can always run, even no user yet exists): Add the org URN to the URL
4. Create a new User for the Org to activate access. In the request body, replace username value with Org UUID, password with a random password (vROPS password complexity rules apply), email Address with orgUUID@org-name.org, firstname with orgUUID, last name with org name, and all further occurences of "resourceId" and "resourceIDs" with the org resource Id.
