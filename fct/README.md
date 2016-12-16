
# bin directory

# Table of Contents

   * [findcfg](#findcfg)
   * [machinecfg](#machinecfg)
   * [readpwd](#readpwd)
  * [Log](#Log)
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
## Log functions

 Function group Description

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
