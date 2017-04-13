---
title: "Ejemplos de c&#243;digo de ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Ejemplos de c&#243;digo de ADO.NET
Los listados de código de este tema muestran cómo recuperar datos de una base de datos utilizando las tecnologías ADO.NET siguientes:  
  
-   Proveedores de datos ADO.NET:  
  
    -   [SqlClient](#_SqlClient) (`System.Data.SqlClient`)  
  
    -   [OleDb](#_OleDb) (`System.Data.OleDb`)  
  
    -   [Odbc](#_Odbc) (`System.Data.Odbc`)  
  
    -   [OracleClient](#_OracleClient) (`System.Data.OracleClient`)  
  
-   ADO.NET Entity Framework:  
  
    -   [LINQ to Entities](#_LINQ)  
  
    -   [ObjectQuery con tipo](#_QBM)  
  
    -   [EntityClient](#_EntityClient) (`System.Data.EntityClient`)  
  
-   [LINQ to SQL](#_LINQ2SQL)  
  
## <a name="adonet-data-provider-examples"></a>Ejemplos del proveedor de datos ADO.NET  
 En los listados de código siguientes se muestra cómo recuperar datos de una base de datos usando proveedores de datos ADO.NET. Los datos se devuelven en `DataReader`. Para obtener más información, consulte [recuperar datos mediante DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).  
  
<a name="_SqlClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 En el código de este ejemplo se supone que puede conectarse a la base de datos de ejemplo `Northwind` en Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]. El código crea un <xref:System.Data.SqlClient.SqlCommand> para seleccionar las filas de la tabla Products, agregar un <xref:System.Data.SqlClient.SqlParameter> para restringir los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. El <xref:System.Data.SqlClient.SqlConnection> se abre dentro de un `using` bloque, lo que garantiza que los recursos se cierran y se eliminan cuando el código sale. El código ejecuta el comando mediante una <xref:System.Data.SqlClient.SqlDataReader>y muestra los resultados en la ventana de consola.  
  
  [DataWorks SampleApp.SqlClient#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient#1)]  
  
 [[Inicio]](#_TOP)  
  
<a name="_OleDb"></a>   
### <a name="oledb"></a>OleDb  
 En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access. El código crea un <xref:System.Data.OleDb.OleDbCommand> para seleccionar las filas de la tabla Products, agregar un <xref:System.Data.OleDb.OleDbParameter> para restringir los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. El <xref:System.Data.OleDb.OleDbConnection> se abre dentro de un `using` bloque, lo que garantiza que los recursos se cierran y se eliminan cuando el código sale. El código ejecuta el comando mediante una <xref:System.Data.OleDb.OleDbDataReader>y muestra los resultados en la ventana de consola.  
  
  [DataWorks SampleApp.OleDb#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb#1)]  
  
 [[Inicio]](#_TOP)  
  
<a name="_Odbc"></a>   
### <a name="odbc"></a>Odbc  
 En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access. El código crea un <xref:System.Data.Odbc.OdbcCommand> para seleccionar las filas de la tabla Products, agregar un <xref:System.Data.Odbc.OdbcParameter> para restringir los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. El <xref:System.Data.Odbc.OdbcConnection> se abre dentro de un `using` bloque, lo que garantiza que los recursos se cierran y se eliminan cuando el código sale. La ejecuta el comando mediante una <xref:System.Data.Odbc.OdbcDataReader>y muestra los resultados en la ventana de consola.  
  
<!-- TODO: review snippet reference  [!CODE [DataWorksSampleApp.Odbc#1](DataWorksSampleApp.Odbc#1)]  -->  
  
 [[Inicio]](#_TOP)  
  
<a name="_OracleClient"></a>   
### <a name="oracleclient"></a>OracleClient  
 En el código de este ejemplo se presupone una conexión a DEMO.CUSTOMER en un servidor Oracle. También debe agregarse una referencia a System.Data.OracleClient.dll. El código devuelve los datos en un <xref:System.Data.OracleClient.OracleDataReader>.  
  
  [DataWorks SampleApp.Oracle#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle#1)]  
  
 [[Inicio]](#_TOP)  
  
## <a name="entity-framework-examples"></a>Ejemplos de Entity Framework  
 En los listados de código siguientes se muestra cómo recuperar los datos de un origen de datos consultando las entidades de un Entity Data Model (EDM). Estos ejemplos utilizan la [modelo de Northwind](http://msdn.microsoft.com/es-es/74521f8c-e974-48cb-8858-c08deff52638). Para obtener más información, consulte [Introducción a Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
<a name="_LINQ"></a>   
### <a name="linq-to-entities"></a>LINQ to Entities  
 El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName. Para obtener más información, consulte [LINQ to Entities información general sobre](http://msdn.microsoft.com/es-es/86d87a27-c17a-45ac-b28d-72c8500333c6).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Linq  
Imports System.Data.Objects  
Imports NorthwindModel  
  
Class LinqSample  
    Public Shared Sub ExecuteQuery()  
        Using context As NorthwindEntities = New NorthwindEntities()  
            Try  
                Dim query = From category In context.Categories _  
                            Select New With _  
                            { _  
                                .categoryID = category.CategoryID, _  
                                .categoryName = category.CategoryName _  
                            }  
  
                For Each categoryInfo In query  
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                        categoryInfo.categoryID, categoryInfo.categoryName)  
                Next  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
        End Using  
    End Sub  
End Class  
```  
  
 En C#:  
  
```  
using System;  
using System.Linq;  
using System.Data.Objects;  
using NorthwindModel;  
  
class LinqSample  
{  
    public static void ExecuteQuery()  
    {  
        using (NorthwindEntities context = new NorthwindEntities())  
        {  
            try  
            {  
                var query = from category in context.Categories  
                            select new  
                            {  
                                categoryID = category.CategoryID,  
                                categoryName = category.CategoryName  
                            };  
  
                foreach (var categoryInfo in query)  
                {  
                    Console.WriteLine("\t{0}\t{1}",  
                        categoryInfo.categoryID, categoryInfo.categoryName);  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
 [[Inicio]](#_TOP)  
  
<a name="_QBM"></a>   
### <a name="typed-objectquery"></a>ObjectQuery con establecimiento de tipos  
 El código de este ejemplo utiliza un <xref:System.Data.Objects.ObjectQuery%601> para devolver datos como objetos Categories. Para obtener más información, consulte [consultas de objeto](http://msdn.microsoft.com/es-es/0768033c-876f-471d-85d5-264884349276).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Objects  
Imports NorthwindModel  
  
Class ObjectQuerySample  
    Public Shared Sub ExecuteQuery()  
        Using context As NorthwindEntities = New NorthwindEntities()  
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories  
  
            For Each category As Categories In _  
                categoryQuery.Execute(MergeOption.AppendOnly)  
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                    category.CategoryID, category.CategoryName)  
            Next  
        End Using  
    End Sub  
End Class  
```  
  
 En C#:  
  
```  
using System;  
using System.Data.Objects;  
using NorthwindModel;  
  
class ObjectQuerySample  
{  
    public static void ExecuteQuery()  
    {  
        using (NorthwindEntities context = new NorthwindEntities())  
        {  
            ObjectQuery<Categories> categoryQuery = context.Categories;  
  
            foreach (Categories category in   
                categoryQuery.Execute(MergeOption.AppendOnly))  
            {  
                Console.WriteLine("\t{0}\t{1}",  
                    category.CategoryID, category.CategoryName);  
            }  
        }  
    }  
}  
```  
  
 [[Inicio]](#_TOP)  
  
<a name="_EntityClient"></a>   
### <a name="entityclient"></a>EntityClient  
 El código de este ejemplo utiliza un <xref:System.Data.EntityClient.EntityCommand> para ejecutar una consulta de Entity SQL. Esta consulta devuelve una lista de registros que representan instancias del tipo de entidad Categories. Un <xref:System.Data.EntityClient.EntityDataReader> se utiliza para tener acceso a registros de datos en el conjunto de resultados. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data  
Imports System.Data.Common  
Imports System.Data.EntityClient  
Imports NorthwindModel  
  
Class EntityClientSample  
    Public Shared Sub ExecuteQuery()  
        Dim queryString As String = _  
            "SELECT c.CategoryID, c.CategoryName " & _  
                "FROM NorthwindEntities.Categories AS c"  
  
        Using conn As EntityConnection = _  
            New EntityConnection("name=NorthwindEntities")  
  
            Try  
                conn.Open()  
                Using query As EntityCommand = _  
                New EntityCommand(queryString, conn)  
                    Using rdr As DbDataReader = _  
                        query.ExecuteReader(CommandBehavior.SequentialAccess)  
                        While rdr.Read()  
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                                              rdr(0), rdr(1))  
                        End While  
                    End Using  
                End Using  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
        End Using   
    End Sub  
End Class  
```  
  
 En C#"  
  
```  
using System;  
using System.Data;  
using System.Data.Common;  
using System.Data.EntityClient;  
using NorthwindModel;  
  
class EntityClientSample  
{  
    public static void ExecuteQuery()  
    {  
        string queryString =  
            @"SELECT c.CategoryID, c.CategoryName   
                FROM NorthwindEntities.Categories AS c";  
  
        using (EntityConnection conn =  
            new EntityConnection("name=NorthwindEntities"))  
        {  
            try  
            {  
                conn.Open();  
                using (EntityCommand query = new EntityCommand(queryString, conn))  
                {  
                    using (DbDataReader rdr =   
                        query.ExecuteReader(CommandBehavior.SequentialAccess))  
                    {  
                        while (rdr.Read())  
                        {  
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);  
                        }  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
 [[Inicio]](#_TOP)  
  
<a name="_LINQ2SQL"></a>   
## <a name="linq-to-sql"></a>LINQ to SQL  
 El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName. Este ejemplo se basa en el contexto de datos Northwind. Para obtener más información, consulte [Introducción](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports Northwind  
  
Class LinqSqlSample  
    Public Shared Sub ExecuteQuery()  
        Using db As NorthwindDataContext = New NorthwindDataContext()  
            Try  
                Dim query = From category In db.Categories _  
                                Select New With _  
                                { _  
                                    .categoryID = category.CategoryID, _  
                                    .categoryName = category.CategoryName _  
                                }  
  
                For Each categoryInfo In query  
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                            categoryInfo.categoryID, categoryInfo.categoryName)  
                Next  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
            End Using   
    End Sub  
End Class  
```  
  
 En C#:  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Northwind;  
  
    class LinqSqlSample  
    {  
        public static void ExecuteQuery()  
        {  
            using (NorthwindDataContext db = new NorthwindDataContext())  
            {  
                try  
                {  
                    var query = from category in db.Categories  
                                select new  
                                {  
                                    categoryID = category.CategoryID,  
                                    categoryName = category.CategoryName  
                                };  
  
                    foreach (var categoryInfo in query)  
                    {  
                        Console.WriteLine("vbTab {0} vbTab {1}",  
                            categoryInfo.categoryID, categoryInfo.categoryName);  
                    }  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex.Message);  
                }  
            }  
        }  
    }  
```  
  
 [[Inicio]](#_TOP)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Crear aplicaciones de datos](../Topic/Creating%20Data%20Applications.md)   
 [Consultar un Entity Data Model (tareas de Entity Framework)](http://msdn.microsoft.com/es-es/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)   
 [Cómo: ejecutar una consulta que devuelve objetos de tipo anónimo](http://msdn.microsoft.com/es-es/3b264025-e911-4d73-90ce-992d2b9d189d)   
 [Centro de desarrolladores de conjunto de datos y proveedores administrados de ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)