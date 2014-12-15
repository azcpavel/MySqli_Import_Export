MySqli_Import_Export
====================

####Develop By
#####Ahsan Zahid Chowdhury
######azc.pavel@gmail.com
######+880-1534-302690
######+880-1677-533818

```

/**
 * @author awan < http://www.nawa.me >
 * @edited By Ahsan Zahid Chowdhury < http://itszahid.info >
 * @date 2014-12-10
 * @Description To enable custome tables selection during export.
 * Fixed import & export format & errors
 * Converted to Object
 */


$dbmanager = New dbmanager;

$config = array(
	'db_host' => db_host,
	'db_uname' => db_uname,
	'db_pass' => db_pass,
	'db_name' => db_name,
	'filename' => 'Backup_'.date('Y_m_d')			
	);

if(!$dbmanager->exportMysqlDb($config) === true);			
	echo $dbmanager->errors;


$config = array(
	'db_host' => db_host,
	'db_uname' => db_uname,
	'db_pass' => db_pass,
	'db_name' => db_name,
	'dir' => DOCUMENT_ROOT.BASEDIR,
	'filename' => 'exceptio_db.sql'			
	);
if($this->dbmanager->importMysqlDb($config) === true)
	echo 'complete import database';
else
	echo $this->dbmanager->errors;


```