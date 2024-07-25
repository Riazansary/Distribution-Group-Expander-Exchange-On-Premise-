# Distribution-Group-Expander-Exchange-On-Premise-
This script is a Module that Expands any distribution list to its last nested layer including expanding any Dynamic DLs that might be nested within. The Module is now fully integrated to work from Exchange Online by authenticating to exchange online upon importing the module, It also has the ability to avoid expanding Nested Distributions Lists  or Dynamic Distributions Lists that are already expanded by marking them on screen as 'Already Expanded'

The script uses three Parameter -Identity , ExpandDynamics , Report

-Identity (Mandatory): This Parameter you specifying the exact name of email address of the Distribution List you want to expand

-ExpandDynamics (Optional): This Parameter is a switch parameter and can be called only, if you want to expand any Dynamic Distribution Lists directly or the ones that might be nested within the Distributoin List you are expanding.

-Report (Optional): This Parameter can be used if you would like to export reports of the expansion to a path (Local or network) you desire. there are two types of report that will be exported by using this parameter. there is a path validation encoded with this parameter meaning if the path you provide here is invalid you will get an error saying path was not validated. You get the following two types of reports:

A txt file of the expansion in a Tree View of the expansion.
A full CVS report of all users of the expansion. this can include members of the Dynamic Distribution Lists (If used the -ExpandDynamics Switch) and members of the regular Distribution Lists.


Examples
Open a regular PowerShell session and import the module from Module Path on your computer

Import-Module <Module Path>
Example bellow will expand "Distribution Group" without expanding the last nested dynamic layer. it will just expand the hierarchy 

Expand-DistributionList "Distribution Group"
Example Bellow will expand "Distribution Group" as well as expanding any nested Dynamic Distribution Group and will export two versions of the report ( as explained above)

Expand-DistributionList "Distribution Group" -ExpandDynamics -Report C:\Documents\



