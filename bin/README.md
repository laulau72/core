
# bin directory

# Table of Contents

   * [attributes.create.file](#attributes.create.file)
   * [configuremultiplefile](#configuremultiplefile)
   * [core.post_i](#core.post_i)
   * [create.README](#create.README)

---


### attributes.create.file

 attributes.create.file -a Arch -e Env -r Role -i Desc -s Site_loc -u Server [-d Site_dc] [-m MidleWare] [-c Cat] [-f] [-h]

 This script is use to automaticaly create the attributes.hostname file

#### Option:

	-a Arch         Architecture Information sould be Linux, AIX or SunOs
	-e Env          Environment parameter should be p (production), v (validation), t (test) or d (development)
	-r Role         Role of the server (ex: lamp, ecomm ...)
	-u Server       Name of the server
	-m MidleWare    Midleware parameter is optional and is use to specifie midleware information( ex: oracle, mysql
	-i Desc         Description of the server
	-s Site_loc     Site location, where the server is installed gs, ......
	-d Site_dc      Site Datacenter, datacenter name where the server is located DC1, DC2 ...
	-c Cat          Server Category, defined the server category A, B or C
	-f              Force overwriting existing attributes.hostname file

	-h              This Help!

 This will set the follwing variables:

	FACTORY_ROLE
	FACTORY_ENV
	FACTORY_ARCH
	FACTORY_LOCATION
	FACTORY_DATACENTER
	FACTORY_CATEGORY
	FACTORY_MW
	BANNER_DESC

#### Return code:

 * 0    Successful
 * 22   usage

---
### configuremultiplefile

 Modify multiple file based on description file that contain changes.

#### Option:

	-h      Simple help
	-H      This help, include configuratin file syntax.
	-f      Name of file that contain data & description of changes.

---
### core.post_i

 core.post_i

 This script will setup directory and env variable after installing the core factoy

---
###  create.README

  create.README -d factory_dir

 This script will Generate README.md file

#### Option:

 * -d factory_dir       Directory base to genereate READMEmd files.

#### Return code:

 * 0    Successful
 * 22   usage

---
