
# fct directory

# Table of Contents

  * [functions.cfg](#functions.cfg)
   * [findcfg](#findcfg)
   * [machinecfg](#machinecfg)
  * [functions.divers](#functions.divers)
   * [rmifexists](#rmifexists)
   * [fatalcheckenv](#fatalcheckenv)
   * [exectoreport](#exectoreport)
   * [factory_id](#factory_id)
   * [runit](#runit)
   * [fatalrunit](#fatalrunit)
   * [fatalfilenotexist](#fatalfilenotexist)
   * [fatalcheckid](#fatalcheckid)
   * [fatalcheckgroup](#fatalcheckgroup)
   * [fatalcheckplatform](#fatalcheckplatform)
   * [add_temp_files](#add_temp_files)
   * [add_audit_files](#add_audit_files)
   * [remove_temp_files](#remove_temp_files)
   * [isVirtualMachine](#isVirtualMachine)
   * [yorn](#yorn)
   * [nok_ok](#nok_ok)
   * [set_prop_file](#set_prop_file)
   * [list_to_line](#list_to_line)
   * [test_notnum](#test_notnum)
   * [genpwd](#genpwd)
   * [readpwd](#readpwd)
   * [addcronjobs](#addcronjobs)
   * [detect_screen_size](#detect_screen_size)
   * [set_screen_size](#set_screen_size)
   * [convertsize](#convertsize)
   * [whorun](#whorun)
  * [functions.logs](#functions.logs)
   * [setlogenv](#setlogenv)
   * [msgprefix](#msgprefix)
   * [loginfo](#loginfo)
   * [logtolog](#logtolog)
   * [logfromfile](#logfromfile)
   * [logwarn](#logwarn)
   * [logerror](#logerror)
   * [logdebug](#logdebug)
   * [fatalerror](#fatalerror)

---


## functions.cfg

 Set of functions to manage configuration files

---
### findcfg

 Output, in order,  the list of Confguration

#### Input:

 * -M			Config is based on machine configuration
 * -U			Config is based on user configuration 
 * -m hostname	Config is based on hostname arg
 * -u username	Config is based on username arg
 * -r 		Reverse order of the Config

#### Ouput:

 * List of Config

#### Retur code:

 *  0:                        Ok

---
### machinecfg

 Descritpion

	Order of criteria for configuration file search
	$MACHINE
	-$FACTORY_ROLE$FACTORY_LOCATION$FACTORY_CATEGORY
	--$FACTORY_ROLE$FACTORY_LOCATION$FACTORY_ENV
	---$FACTORY_ROLE$FACTORY_CATEGORY
	----$FACTORY_ROLE$FACTORY_ENV
	-----$FACTORY_ROLE$FACTORY_LOCATION
	------$FACTORY_ROLE
	-------$FACTORY_MW$FACTORY_CATEGORY
	--------$FACTORY_MW$FACTORY_ENV
	---------$FACTORY_MW
	----------$FACTORY_LOCATION$FACTORY_DATACENTER$FACTORY_CATEGORY
	-----------$FACTORY_LOCATION$FACTORY_DATACENTER$FACTORY_ENV
	------------$FACTORY_LOCATION$FACTORY_ARCH$FACTORY_CATEGORY
	-------------$FACTORY_LOCATION$FACTORY_ARCH$FACTORY_ENV
	--------------$FACTORY_LOCATION$FACTORY_CATEGORY
	---------------$FACTORY_LOCATION$FACTORY_ENV
	----------------$FACTORY_ARCH$FACTORY_LOCATION$FACTORY_DATACENTER
	-----------------$FACTORY_ARCH$FACTORY_LOCATION
	------------------$FACTORY_LOCATION$FACTORY_DATACENTER
	-------------------$FACTORY_LOCATION 
	--------------------$FACTORY_ARCH$FACTORY_CATEGORY
	---------------------$FACTORY_ARCH$FACTORY_ENV
	----------------------$FACTORY_ARCH
	-----------------------$FACTORY_CATEGORY
	------------------------$FACTORY_ENV
	-------------------------default

#### Input:

 * Machine_Name

#### Ouput:

 * output

#### Return code:

 *  0:                        Ok
 *  other:                  Error

---
## functions.divers

 Set of miscellaneous functions

---
### rmifexists

 Remove file or several files if the file existes. 
 It also remove directory

#### Input:

 * files to remove

---
### fatalcheckenv

 Check the environnment if environnment is not setted

#### Input:

 * Env variable

#### Output:

 * fatal error output will be displayed, if not set.

---
### exectoreport

 Execute and make report

---
### factory_id

 Print real and effective user and group IDs

#### Input:

 User
 
---
### runit

 Run a programm and log it

#### Input:

 Programm

---
### fatalrunit

 Run a programm, log it and exit if error

#### Input:

 Programm

#### Output:

 exit if error

---
### fatalfilenotexist

 If a file does not exist make fatal error and exit

#### Input:

 file

---
### fatalcheckid

 Check if this program is launch from this user

#### Input:

 id to check

#### Output:

 Exit if not this user

---
### fatalcheckgroup

 Check if this program is launch from user with this group

#### Input:

 group to check

#### Output:

 Exit if not in this group

---
### fatalcheckplatform

 Check if this program is launch on this platform 

#### Input:

 platform to check

#### Output:

 Exit if not this platform

---
### add_temp_files

 Create a temporary file

#### Input:

 Name 

#### Output:

 Name of the temporary file

---
### add_audit_files

 Create an audit file

#### Input:

 Name

#### Output:

 Name of the audit file

---
### remove_temp_files

 Remove temporary file that was created

---
### isVirtualMachine

  Checking if the machine (only in Linux OS) is a virtual machine (VMWare)

#### Output:

 * 0: virtual	
 * 1: physical

---
### yorn

  YES or NO reponse in 3 languages English,French and German

---
### nok_ok

 Display message action complete successful or action failed depend of param 1 that is the RC number.

#### Input:

 * number to check

---
### set_prop_file

 Change rights, user owner and group owner of a file.

#### Input:

 * $1 file_mod
 * $2 file_owner
 * $3 file_group
 * $4 file_name

---
### list_to_line

 Simple function to convert entries on list mode to a single line separate by space (replace all CR by a SPACE)
 Sort input before put in line.

---
### test_notnum

 function used to test if a value is numeric or not.
 can test positve, negative or both possibility.

#### Output:
 
 * 0:  value is numeric
 * 22: value is not numeric

---
### genpwd

 Generate random password and output on standard output

#### Input:

 * -l:  Minimum password leng
 * -n:  Minimum numeric in password 
 * -a:  Minimum alpha in password 

---
### readpwd

 This function ask the user to enter a password

 If $DIALOG is set, semi-graphical menu will be use.

#### Input:

 * Text to be display

#### Ouput:

 * The variable PASSWD will be set with the passord entered

#### Retur code:

 *  0:                        Ok
 *  other:                  Error

---
### addcronjobs

 Used to add cron job defined in configuration file(s) (add as parameter)

 files should have the following :
 name;user;script;schedule_min;schedule_hour;schedule_dayofmounth;schedule_mounth;schedule_weekday

#### Input:

 * file

---
### detect_screen_size

 Detect screen geometry
   Set variable for Colums and Lines
   Set variable for select command in function  of screen lines number

---
### set_screen_size

 Set variables for tty

---
### convertsize

 Convert a size in Bytes or other scale to another scale

#### Input:

 option mandatory
	* s size with unit (100MB, 1.04TB, 100348965392B, 2039GB)
	* c unit (B, KB, MB, GB, TB, PB, EX, ZB, YB)
 option not mandatory
      * r to display automatic scaled human readable size

#### Output:
	
 Ex:	
	0.32TB:335544MB:327.67GB
	32GB:0TB:32.00GB
	32GB:32768MB:32.00GB
	0.3243GB:332MB:332.08MB	
	
---
### whorun

 Return muid:fuller conencted to teh server

---
## functions.logs

 Set of functions to manage miscellaneous logs

---
### setlogenv

 Setting the log environment variables.
 This function is called in the init part.

#### Input:

 The following variable will change the contenent of the output variables
 * $FACTORY_AUDIT
 * FACTORY_LOGFILEXT (if set to "FULLDATE"

#### Ouput:

 * FACTORY_LOGDIR
 * FACTORY_LOGFILE

---
### msgprefix

 Output format messages depending of the varible setting (see input)

#### Input:

 * $FACTORY_NOMSGPREFIX
 * $FACTORY_LOGFULLDATE
 * $FACTORY_LOGPROGNAME
 * $FACTORY_LOGPID
 * $FACTORY_LOGHOSTNAME
 * $FACTORY_LOGUSER

#### Ouput:

 * 

---
### loginfo

 Activate the log information in VARFACTORY_LOG (/var/factory/log) and on the screen 

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the I: prefix

#### Exemple:

 *  I: 12:46:58 Starting Centreon Core

---
### logtolog

 Activate the log information in VARFACTORY_LOG (/var/factory/log)

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the I: prefix

#### Exemple:

 *  L: 12:46:58 Starting Centreon Core

---
### logfromfile

  Append log contents followed the informations level E as Error, I as Info, W as Warning, D as Debug function: logfromfile to the factory log (/var/factory/log)

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the I: prefix

---
### logwarn

 Transform any log line in level warning W

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the W: prefix

#### Exemple:

 *  W: 12:46:58 Centreon Core is already started

---
### logerror

 Transform any log line in level error E

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the E: prefix

#### Exemple:

 *  E: 12:46:58 Centreon Core is not running

---
### logdebug

 Transform any log line in level debug D

#### Input:

 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the D: prefix

#### Exemple:

 *  D: 12:46:58 Centreon Core is started

---
### fatalerror

 Transform any log line in level error E and exit

#### Input:

 * exit code
 * Comment to be written in the log

#### Ouput:

 * Entry is added in $FACTORY_LOGFILE with the E: prefix
 * exit $1

#### Exemple:

 *  E: 12:46:58 Failed to start Centreon

---
