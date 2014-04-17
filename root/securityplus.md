Security Plus Notes
======================


Chapter 2 - Control Types and Methods
-----------------------------------------

Control Types:

* Technical - uses technology to reduce vulnerabilities (ex: least privilege, antivirus, etc.)
* Management - administrative (ex: Risk and Vulnerability assessments)
* Operational - (ex: awareness and training, configuration mgmt, cameras, locks, etc.)

Functions:

* Preventative - security guards, change mgmt, hardening, account disablement
* Detective - security audit, video surveillance
* Corrective - intrusion detection systems (IDS), backups and system recovery

Access Control Models

* RBAC - Role/Rule-based access control
    * hierarchy based
    * job, task, or function based
* DAC - Discretionary access control
    * every object (file or folder) has a owner who establishses access (Windows/Unix based)
    * MS NTFS
    * user identified with a SID (security identifier)
    * objects have Discretionary Access Control List (DACL) which consists of Access Control Entries (ACEs)
    * Each ACE is a SID and permission(s) granted
* MAC - Mandatory access control
    * uses labels (sensitivity or security labels) to determine access
    * both subjects and objects are assigned labels. When they match the permissions are granted
    * SEUnix is one of the few OS that use MAC
    * example include US classification model (U, C, TS, etc.)
    * "lattice" describes relationship between sets of labels and defines upper/lower bounds





