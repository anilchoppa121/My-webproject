
**EXAMPLE FORM PAGE**
       
**Benefits of using JSONPowerDB**

JsonPowerDB is a Database Server with Developer friendly REST API services. 
It's a High Performance,Light Weight, Ajax Enabled, Serverless, Simple to Use, Real-time Database. 
Easy and fast to develop database applications without using any server side programming without installing any kind of database.

**Uses**

1.Any software aplication that needs a backend database.

2.Live working Html templates.

3.best suited for real time application for data analysis.

4.Best suited as backend Database for IoT.

5.Existing Database applications to improve their reporting / analytics performance.

**Features**
1.JsonPowerDB (JPDB) is a High Performance, Light Weight, Ajax Enabled, Serverless, Simple to Use, Real-time Database.

2.Easy and fast to develop database applications without using any server side programming / scripting or without installing any kind of database.

3.Multi mode database.

4.webservices API.

5.Multiple security layers.

6.Schema free and easy to maintain.

7.Nimble, Simple to use, In Memory, Real-time DBMS.

8.Enriched by a pluggable API Framework - A developer can develop a pluggable API and plugin into any of our cloud JPDB instance.

9.In-built support to query on multiple JPDB databases.

10.DBMS with built in web / application server and embedded caching makes the performance lightning fast.

11.Server side Native NoSQL - best query performance.

**Release History**

**v0.3.2.20201008.2427 beta**

**0.3.2 / 2021-04-10**
* Added : New type "REMOVE" in Set API for delete operations, in compliance with RDBMS constraints.
* Added : New response headers that display time taken by the JPDB server to serve request.
* Added : ForeignKeys functionality in SET and SET_ALL API to provide complete support for the soft implementation of RDBMS.
* Added : Started Reporting of All Unhandled Exceptions via email.
* Added : A new version of jpdb-commons.js 0.0.4 added with SET & SET_ALL methods and help for all commands
* Improved : Parsing time for request now reduced.
* Improved : Response message for syntax error in case of empty body in request.
* Improved : Known exception handling.
* Improved : Help Documentation.
* Improved : jUnit Test Cases.
* Various bug fixes.

**v0.3.2.20201008.2215 beta**

***0.3.2 / 2020-10-08***

* Added : Added Plugin API Framework in JsonPowerDB.
* Added : Added a new class APISyntaxValidator to check syntax of request json.
* Added : Added a new APIs for column operation and implement it using pluggable framework:
             Copy Column - It will copy column in database.
             Rename Column - It will rename column in database.
             RemoveColumn - It will remove column in database.
             Change Column type - It will change type of column in database.
* Improved : In Geospatial distance API to pick create time column (sorted in ascending) as time range 
             (by default it should pick the record creation time from the JPDB system file internal 
             recorded time) defined in request fromTime to toTime.
* Fixed : Fixed important bugs.  

**v0.3.2.20200715.2092 beta**

**0.3.2 / 2020-07-15**
* Added : Added two new APIs in jsonPowerDB for serving both PUT and UPDATE with soft-unique-key 
          implementation.
        1. SET (for one record)
        2. SET_ALL (for multiple records)
* Added : Support added for plugin services by call to 
        - PluginService.enablePluginService();
* Added : Added a big counter API in JPDB that will take in a capacity and return the previous value 
          of the counter or incremented value or initialize it(negative value is also allowed here). 
          It contains three commands :
        1. INIT: It will initialize the counter by given incValue or if incValue not present then
                 initialize with zero.
        2. GET: It will return the value of counter or increment counter if incValue is present.
        3. INC: It will return incremented value of counter if incValue present, if not present then
                it will increment counter by one.
* Added : Added new GEO_SPATIAL APIs
        1.GEO_DISTANCE
            - Now we can find distance, angle, record number, coordinates by using fromTime to toTime
              from database.
        2.AREA_CIRCLE 
            - It will give all coordinates, angles, distance from given position record number within
              the given radius of the circle.
        3.AREA_OUTER_SQUARE
            - It will give all coordinates, angles, distance from given position and record number 
              within the given radius of the outer square of the circle.
        4.AREA_INNER_SQUARE
            - It will give all coordinates, angles, distance from given position and record  number 
              within given radius of inner square of circle.
* Improved : Modified the UPDATE API, so that it works for multiple records.
* Fixed : Fixed important bugs.

**v0.3.2.20200208.1924 beta**

**0.3.2 / 2020-02-08**
* Added : New releases JPDBObject.js, JPDBRelObject.js, jpdb-commons.js are done.
            - JPDBObject.js allows client application to keep the most used data in clients local 
             storage to improve the performance of application and to reduce the network usage also 
             reduces development cost considerably.
            - jpdb-commons.js allows the usage of jpdb more efficiently.
* Added : Add createTime  and updateTime in request and response of below given commands so that if 
          createTime and updateTime set to true its value come in response otherwise not. Relations 
          updateTime() is corrected for the relations (old version data) having 0 as updateTime.
            - GET_BY_KEY/GET, GET_BY_RECORD/GET_RECORD, GET_ALL, FIND_ALL_RECORD/FIND_RECORD, 
              FIRST_RECORD, LAST_RECORD, NEXT_RECORD, PREVIOUS_RECORD, SYNC_DB.
* Added : Added two 'isl' commands in NoSQL.
* Added : Added support for maintaining relation size. This results in improvement of performance of 
          client application.
* Improved : "PUT" and "PUTALL" commands have been improved by adding rec_no array in response.
* Improved : "http" is changed to "https" to be a more secured repository.
* Improved : Some of syntaxes are changed for better usage.
* Fixed : Fixed some important bugs.

**v0.3.2.20200101.1822 beta**

**0.3.2 / 2020-01-01**
* Added : New API SYNC_DB is added for getting all updated records after a given timestamp for all 
          the specified relations, with their timestamp, record_count, deleted_count.
* Added : Added two new APIs for Load all details of EMC setting and save all details of EMC setting,
          also added a flag to enable / disable EMC facility. The APIs are:
	      - "/load_company_emc_settings"
	      - "/save_company_emc_settings"
* Added : Added a method to get deleted record count in a given relation in irl command GET_RELATION_SIZE.
              - getFileDeletedCount(String fullRelationName)
* Added : Added a post method for getting file size.
* Improved : Earlier it will give 200 status for both data found or data not found, but now it will 
             give 400 status for data not found and status code for Invalid Token is 401.
* Improved : Improved error messages by adding constants.
              - public final static String COMMAND_NOT_PRESENT = "Command No Present";
              - public static final String ERROR_MSG_NO_RECORDS_FOUND= "No Records Found";
* Improved : Improved the GETALLREL command for giving better response that has all relation names 
             with their timestamp, record_count, deleted_count.
* Improved : Improved syntaxes of command names to be in the same format(Exampl: GET_ALL_DB) which 
             ease the usage of Jpdb.
* Fixed : Fixed some important bugs.

**v0.3.2.20191114.1804 beta**

**0.3.2 / 2019-11-14**
* Added : Added UI page for individual user's request and response size limit in a given period 
          (10 seconds to 5 minutes).
* Added : New private method for common execution, this returns array of records of the given keys 
          with dependent relations data inside primary relation record.
* Added : Some new features are added to profile page, so that user can enter their contact 
          information, edit their information and also change their profile pictures.
* Improved : If timestamp < 0 it will ignore timestamp and return the first page with default number rows.
* Improved : Improved NoSQL to perform operation like JOIN in sql query
            - Added functionality to  relate multiple relations and return combined data with only 
             specified col name of all this relation from the given fromKey to toKey with offset and 
             noOfRecs restriction.
* Improved : Removed the check of null as we need to send the records that are removed.
* Changed : Corrected index.remove() call to take individual record numbers for removal instead of the array of record numbers.
* Changed : Changes are done in the Admin Dashboard to make it more user friendly.
* Fixed : Fixed some important bugs.  

**v0.3.2.20190827.1796 beta**

**0.3.2 / 2019-08-27**
* Added : UI on admin dashboard for user limit settings.
* Added : CRUD time for row  and relation object.
* Added : Commands in the api for checking whether database and relation exist and getting their size.
          (end point url : /api/irl)
          - IS_RELATION_EXISTS, IS_DATABASE_EXISTS, GET_RELATION_SIZE
* Added : Two new APIs for getting and updating user limit settings are added:
          - "/company/load_user_limits_settings"
          - "/company/update_user_limits_settings"
* Added : Added timestamp feature which manages all CRUD time at row and relation level.
* Improved : NoSQL can perform operation like JOIN in sql query
          - Added functionality to relate multiple relations and return combined data with only specified col name of all this relation from the given fromKey to toKey with offset and noOfRecs restriction.
* Improved : In JSON SQL Query, complex conditions can be now processed in where clause with multiple AND, OR operation.
* Improved : GETALL command is improved
          -  Either pagesize|pageNumber will work or timestamp.                       
          -  New input parameter columns added which takes column name in JSONArray and returns only those columns in the output.
* Improved : REMOVE command functioning extended (now we can delete multiple records at a time).
* Fixed : Important bugs.

**v0.3.2.20190205.1721 beta**

**0.3.2 / 2019-02-05**
* Added: New implementation of Small Token for newly generated connection token.
    - Using Small-token, KVPDB request size will be reduced.
    - Fast Execution of KVPDB operation.
 * Added: JPDB Help in UI of User Dashboard, Now User can directly go to JPDB Help Docs for any API help. 
 * Improved: User can now add the description of the connection-token, in which application user is using connection-token,
    - Easy To understand which connection-token is used where.
 * Improved: Limit Functionality in JsonPower SQL Query.
 * Improved: UI of Company User Management Webpage in Company Dashboard and User Tools Webpage in User Dashboard.
 * Changed: User SMTP settings Webpage moved to User Tools Webpage.
 * Fixed: Important bugs.
                                
***v0.3.2.20181127 beta***

***0.3.2 / 2018-11-27***
* Added: New implementation of JsonPower SQL Query using HTTP REST API.
    - User can now query their data using JsonPower SQL Query which is :
       - Easy To understand.
       - Fast.
 * Added: Added support to generate a new connection-token.
    - To use it directly in any application to access JPDB IML, IRL, IDL, ISL and serverless api.
    - Increase security of data as user does not need to provide his user-id and password. 
 * Added: Added support for creating new column in UPDATE command.
 * Added: Added support to get workspace name and workpspace ID of a given workspace in key-value DB.
 * Added: Added support to set or change the time limit for user-token.
 * Improved: Improved the performance of Backup, PUT and PUTALL command, Commit and Recovery.
 * Changed: UI of "User Tools" & "Company-Settings".
 * Fixed: Important bugs.
 
**v0.3.2.20181004 beta**
 
**0.3.2 / 2018-10-04**
* Added: New implementation of Key-Value data structures and supported HTTP REST API.
    - Multiple data structure in one Workspace.
        - Each Workspace will have one default data structure and multiple 'named' HashMap data structures.
        - All Workspace allows key-value pair data to be stored.
        - Expire of individual key-value pair can be configured through API.
    - Multiple Workspace can exist in Workspace_Pool.
    - Separate API for default data structure and HashMap data structures.
 * Added: Backup, Download, Upload, Restore and Delete JPDB backups.
 * Added: Commit and Recovery with User level controls only if organization / company admin allow.
 * Added: Added support for creating the structure of relation without inserting any data.
 * Added: Added favicon on all dashboard and in Help documentation.
 * Changed: API improved for serverless features.
 * Fixed: Important bugs.
 
**v0.3.2.20180615 beta**
 
**0.3.2 / 2018-06-15**
* Added: Help / Documentation site is created. Check http://login2explore.com/jpdb/
  - jpdb-common-reference.js: Helper jar Java developers to easy use of JPDB API from java. 
  - CRUD examples added for JPDB user / developers. 
  - API reference 
  - NoSQL reference (2018-06-22)
  - NoSQL examples (2018-06-22)
 * Added: Added support for automatic indexing of new Columns in request.
 * Added: New command API added for 'IS_COLUMN_INDEXED' and 'IS_COLUMN_EXIST'.
 * Added: Limits data size per user in request and response for a specfied duration. 
 * Added: Auto registration of new user in help / support email lists.
 * Added: JPDBUtils.jar: Helper jar Java developers to easy use of JPDB API from java. 
 * Added: Added basic infrastructure for JPDB installations monitoring through JSSM server.
 * Fixed: Various Bug fixes and improvements.

**v0.3.2.20180507 beta**

**0.3.2 / 2018-05-07**
 * Added: Security Layers for API access.
 * Added: Serverless support for client’s session management.
 * Added: Serverless support of SMTP Settings for user for sending emails.
 * Added: Support for system properties like database access limits or restrictions, and status related controls, JPDB and JSSM host details.
 * Added: Support for company to create and modify email template for sending emails.
 * Added: Java utility class JPDBUtils.java to help developers to ease development.
 * Added: Release version is now displayed on user and company dashboard.
 * Changed: Display warning message on Company Dashboard, if SMTP is not set.
 * Changed: UI of "Add Index" & 'Unindex Column". 
 * Fixed: Heartbeat interval.
 * Fixed: JSSM status admin removed in user management table of JPDB Company.
 * Fixed: Same JPDB instance can now be both JPDB and JSSM.
 * Fixed: After User licence limit exceed, a warning message displayed to user who is trying to register.
 * Fixed: Ambiguity of intallation id resolved.
 * Fixed: After adding 5 user, if SMTP of company is not set new user will not be able to login to JPDB user dashboard. 

**v0.2.7.20170919 alpha**

**0.2.7 / 2017-09-19**
 * Added: Developer dashboard more easy to use, by which developer can insert, remove, update records easily.
 * Added: NoSQL, using this feature developer can write their own query script in native (java) language and execute that script on JsonPowerDB server.
 * Added: NoSQL is designed using QueryService interface which contains some ready to use high performance, easy to use query support methods.
 * Added: NoSQL also has support for passing parameters to the QueryService interface’s execute methods.
 * Added: User can add new index and remove existing index into/from JsonPowerDB.
 * Fixed: Restricted indexing on Boolean columns.
 * Fixed: Method which give accurate file size by deducting deleted record count.

**v0.2.5.20170810 alpha**

**0.2.5 / 2017-08-10**
 * Added: Any Json row if inserted by default it will store in JsonPowerDB.
 * Added: User have facility to remove database.
 * Added: User can add new index or column in JsonPowerDB.
 * Added: User can remove single column in JsonPowerDB.
 * Fixed: If Column is not added(indexed) in PowerIndex then Error Message returned to the Client.

**v0.2.5.20170718 alpha**

**0.2.5 / 2017-07-18**
 * DBaaS - A Database SAAS: Available as shared environment or as independent server on Internet / Intranet / Extranet / Cloud.
 * A Single Instance - Million Indexes: Can support over a million indexed columns in a single instance spread across users and databases.
 * Querying Multiple Databases: Allows querying multiple databases which is as simple and fast as querying on single database.
 * Serverless Architecture Support: Minimum learning curves, builds faster, cuts time to market, reduces the development cost.
 * NoSQL: Native Server Side NoSQL, suitable for high performance real-time data processing.
 * REST-API Webservice: Schema-free, Simple to use, Nimble and In-Memory database.
 * Developer - Dashboard: Helps developers in faster coding, in-turn reduces development cost.
 * PowerIndeX Energized: JsonPowerDB is built on top of one of the fastest and real-time data indexing engine - PowerIndeX.




