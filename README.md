# TeamsScripts
Collection of various Teams PowerShell scripts that perform specialized tasks

## Copy-SfBLISSubnetsToTeams
Migrates SfB Location Information Database (LIS) civic address, location and subnet components to Microsoft Teams. Useful for replicating Emergency Dialing config from SfB to Teams. Only requires an export of the LIS subnet information, which includes everything necessary to build the equivalent setup in Teams.

To load the module, open a PowerShell window and type **. .\SfBLISMigrationTools.ps1** (the 2 dots at the beginning are important).
Then run:
* Get-CsLisSubnet | Copy-SfBLISSubnetsToTeams (directly from a SfB server)
* Import-Csv LISSubnets.csv | Copy-SfBLISSubnetsToTeams (using a CSV file export using Get-CsLisSubnet from another machine)

## Remove-TeamsLISConfig
Wipes out all the civic addresses, locations and subnets from a Teams LIS database. Handy when testing migrations, and you screw something up (not like that would ever happen).

## Reset-TeamsEVToFactory
This will wipe out all Teams Enterprise Voice configuration, except for existing PSTN gateways. Great for testing out new dialplans from places like UCDialplans.com

## Get-TeamsAANumbers
Teams PowerShell doesn't make it easy to obtain a list of Auto-Attendants along with their assigned phone number(s). This little script makes it easy.
