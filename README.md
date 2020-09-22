<div align="center">

## connecting to SqlServer using ADO\.Net


</div>

### Description

Using Sqlconnection connecting to SqlServer with easy tips
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Bheemasena Rao\.Y](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bheemasena-rao-y.md)
**Level**          |Beginner
**User Rating**    |3.3 (46 globes from 14 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Databases](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/databases__10-5.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bheemasena-rao-y-connecting-to-sqlserver-using-ado-net__10-236/archive/master.zip)





### Source Code

Category: DataBase <br>
Level: Beginnner <br>
Description: Using Sqlconnection connecting to SqlServer with easy tips <br>
Compatibility : VB.Net /ASP.Net<br>
<br>
<br><br>
Namespaces to be included <br>
Imports ADODB <br>
Imports System.Data.SqlClient <br>
Imports System.Data.SqlClient.SqlDataAdapter<br>
 <br><br>
Sqlconnection object has to be instantiated .<br>
The parameters are <br>
data source = sql server name<br>
initial catalog = database name<br>
user id and password <br>
workstation id=YBRAO2000 <br>
SqlCommand object has to be instantiated to execute the Sql statement.<br>
 <br><br>
SqlAdapter object has to be instantiated to fill the data into DataSet.<br>
 <br>
Data set must be instantiated.<br>
Dim objConn As SqlConnection = New SqlConnection("data source=YBRAO2000;initial catalog=pubs;persist security info=False;user id=sa;workstation id=YBRAO2000;packet size=4096")<br><br>
Dim become As New SqlCommand()<br>
Dim JobsDA As SqlDataAdapter = New SqlDataAdapter()<br>
Dim JobsDS As DataSet = New DataSet()<br>
 <br>
<br>
Now the commandobject has to be created with CreateCommand method.<br>
objcomm = objConn.CreateCommand()<br>
Now Specify the SQL Statement.<br>
objcomm.CommandText = "SELECT * FROM JOBS"<br>
Now open the connection <br><br>
objConn.Open()<br>
 <br>
Now Assign the command object to Sql Adapter.<br>
JobsDA.SelectCommand = objcomm<br>
<br>
Now Fill the Dataset with SqlAdapter<br>
JobsDA.Fill(JobsDS, "jobs")<br>
 <br>
 <br>
Now using DataRow we can retrive all the values from the table as given below from the dataset.<br>
Dim pRow As DataRow<br>
For Each pRow In JobsDS.Tables("Jobs").Rows <br>
system.Console.WriteLine (pRow("job_id").ToString()) <br>
Next <br>
 <br>
Now Close the connection <br>
objConn.Close() <br>
Let me explain about the SqlDataAdapter class .<br>
SqlDataAdapter Class : <br>
------------------------<br>
Name space Required is System.Data.SqlClient<br>
SqlDataAdapter Class Represents a set of data commands and a database connection that are used<br> to fill the dataset and update a SQL Server database and this class can not be <br>inherited.<br>
The SqlDataAdapter, serves as a bridge between a <br>dataset and SQL Server for retrieving and saving data.<br>
SqlDataAdapter is used in conjunction with SqlConnection and SqlCommand to increase <br>performance when connecting to a Microsoft SQL Server database. <br><br>
The SqlDataAdapter also includes the SelectCommand ,InsertCommand ,DeleteCommand ,UpdateCommand , <br>and TableMappings properties to facilitate the loading and updating of data.<br>
Below I am giving some sample examples through which you can understand how exactly this object works .<br><br>
JobsDA.SelectCommand = New sqlCommand( "SELECT JobID,JobName FROM Jobs" , objConn)<br>
JobsDA.InsertCommand = New sqlCommand( "Insert Into Jobs values (1,'Marketing')" , objConn)<br>
JobsDA.UpdateCommand = New sqlCommand( "Update Jobs Set JobName ='Financial" Where JobID =1 " , objConn)<br>
JobsDA.DeleteCommand = New sqlCommand( "Delete From Jobs Where JobID =1 " , objConn)<br>
I hope now you are able to get the core Concepts of the SqlDataAdapter class and its behaviour.<br><br>
Bye for Now<br>

