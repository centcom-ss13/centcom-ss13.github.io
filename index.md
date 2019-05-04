# CentCom
### *The SS13 Management Service*

[Demo Site](http://centcom.ddmers.com) - [Github Organization](https://github.com/centcom-ss13) - [Service Homepage](https://centcom.services) (coming soon!)

## Goal

Created for the Yogstation Space Station 13 community, CentCom is a suite of tools is designed to provide an all-in-one management suite of the "technical" aspects of a SS13 community.

### What this is intended to be

 - A panel to manage different aspects of the SS13 server and community, including:
   - Users
   - Groups
   - Permissions
   - Books
   - Bans
   - Community configuration
   - Donations
   - Jobs list (for job bans)
 - With eventual plans to include:
   - Admin stat tracking
   - Player stat tracking
   - Player lookups, with quick accessibility on the ban panel
   - A customizable splash page
   - Round statistics
   - Server status
   - User themes
   - Complete audit logs
   - Module visibility customization
 - Community and codebase agnostic (we want anybody to be able to use it)
 - Built from the ground up to be configurable and modular

### What this is *not* intended to do
 - Run BYOND Servers - All deployment and management of SS13 code is left up to the implementer
 - Manage code, issues, player requests, forums, etc. - there are other tools for much of this, and we are not looking to recreate the wheel

## FAQ

**But why even attempt this sort of thing?**

Read the rest of this FAQ.  And because it's fun.

**How do you use this service?**

Currently, it is required to build the service yourself as there are no releases.  The main service consists of the [front end](https://github.com/centcom-ss13/centcom-ui) and [back end](https://github.com/centcom-ss13/centcom-server) repositories.

Both repositories (will eventually) contain their own build and deployment instructions.

**How much work will it take to use this?  How will I integrate things like bans with my own server?**

In line with a goal of this service to be "community and codebase agnostic", there is a necessity to be able to work with any codebase to integrate services like bans and server group permissions.  Some current options for this include:
 - Migrate the existing server db to the CentCom schema - modifying your codebase's schema to match, and use, the CentCom database, will allow immediate integration.  This will require moderate knowledge of SQL to modify your codebase to match the existing schema.
 - Create views to merge your existing schema with CentCom's - then, use the views in your SS13 database configuration (rather than the original tables)
 - Create cron jobs to merge the CentCom and server information - this option works best if you plan to keep the CentCom and server databases on different dbs or servers.  I plan on eventually providing examples of how this would work, and potentially adding it to [centcom-core](https://github.com/centcom-ss13/centcom-core)

Lastly, this service does not *require* any SS13 server interactions, and many features can be used without it.  Please contact me for any questions, concerns, or help with migration - I'm happy to assist.

**Are you planning to offer any paid services or hosting of your own?**

No.  I am happy to help *you* set up a server with all of the assets though!

**This all seems really complicated.**

Not a question, but yeah, it is.  I'm planning to simplify it in the future, but in an alpha state the best I can hope to do is provide clear and concise documentation.


## Building

Please refer to both the [front end](https://github.com/centcom-ss13/centcom-ui) and [back end](https://github.com/centcom-ss13/centcom-server) repositories for build instructions.  [Service documentation](https://centcom-ss13.github.io) ~~is also~~ will soon be available.
The following services are required:
 - A static web hosting service (front-end resources only consist of a few static html,js,etc. files)
 - Node.js(8+) for running the back end and compiling both codebases - I recommend [nvm](https://github.com/coreybutler/nvm-windows) for installing npm+node if you do not already have it
 - A MySQL database (MariaDB works fine) - the schema and migrations are contained within the back end repo

## Contributing

Issues and PRs are welcomed on all codebases - feel free to contact me personally with any questions!