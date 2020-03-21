---
title: Ejemplos de código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 6e0c34e1db50030c78db295f26fcc25b431d3dde
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111808"
---
# <a name="adonet-code-examples"></a>ejemplos de código ADO.NET

Los listados de código de esta página muestran cómo recuperar datos de una base de datos mediante las siguientes tecnologías de ADO.NET:

- Proveedores de datos ADO.NET:

  - [SqlClient](#sqlclient) `System.Data.SqlClient`( )

  - [OleDb](#oledb) `System.Data.OleDb`( )

  - [Odbc](#odbc) `System.Data.Odbc`( )

  - [OracleClient](#oracleclient) `System.Data.OracleClient`( )

- ADO.NET Entity Framework:

  - [LINQ to Entities](#linq-to-entities)

  - [ObjectQuery con establecimiento de tipos](#typed-objectquery)

  - [EntityClient](#entityclient) `System.Data.EntityClient`( )

- [LINQ a SQL](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a>ejemplos de ADO.NET proveedores de datos
En los listados de código siguientes se muestra cómo recuperar datos de una base de datos usando proveedores de datos ADO.NET. Los datos se devuelven en `DataReader`. Para obtener más información, consulte [Recuperación de datos mediante un DataReader](retrieving-data-using-a-datareader.md).

### <a name="sqlclient"></a>SqlClient
El código de este ejemplo supone que `Northwind` puede conectarse a la base de datos de ejemplo en Microsoft SQL Server. El código crea <xref:System.Data.SqlClient.SqlCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.SqlClient.SqlParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. Se <xref:System.Data.SqlClient.SqlConnection> abre dentro `using` de un bloque, lo que garantiza que los recursos se cierran y se eliminan cuando se cierra el código. El código ejecuta el comando utilizando <xref:System.Data.SqlClient.SqlDataReader> y muestra los resultados en la ventana de la consola.

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a>OleDb
En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access. El código crea <xref:System.Data.OleDb.OleDbCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.OleDb.OleDbParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. <xref:System.Data.OleDb.OleDbConnection> se abre dentro de un bloque `using`, que garantiza que los recursos se cierran y se eliminan cuando termina la ejecución del código. El código ejecuta el comando utilizando <xref:System.Data.OleDb.OleDbDataReader> y muestra los resultados en la ventana de la consola.

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a>Odbc
En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access. El código crea <xref:System.Data.Odbc.OdbcCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.Odbc.OdbcParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5. Se <xref:System.Data.Odbc.OdbcConnection> abre dentro `using` de un bloque, lo que garantiza que los recursos se cierran y se eliminan cuando se cierra el código. El código ejecuta el comando utilizando <xref:System.Data.Odbc.OdbcDataReader> y muestra los resultados en la ventana de la consola.

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a>OracleClient
En el código de este ejemplo se presupone una conexión a DEMO.CUSTOMER en un servidor Oracle. También debe agregarse una referencia a System.Data.OracleClient.dll. El código devuelve los datos en <xref:System.Data.OracleClient.OracleDataReader>.

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a>Ejemplos de Entity Framework
En los listados de código siguientes se muestra cómo recuperar los datos de un origen de datos consultando las entidades de un Entity Data Model (EDM). Estos ejemplos utilizan un modelo basado en la base de datos de ejemplo Northwind. Para obtener más información acerca de Entity Framework, vea Información general de [Entity Framework](./ef/overview.md).

### <a name="linq-to-entities"></a>LINQ to Entities
El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName. Para obtener más información, vea Información general sobre [LINQ to Entities](./ef/language-reference/linq-to-entities.md).

```csharp
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

```vb
Option Explicit On
Option Strict On

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

### <a name="typed-objectquery"></a>ObjectQuery con establecimiento de tipos
En el código de este ejemplo se utiliza <xref:System.Data.Objects.ObjectQuery%601> para devolver los datos como objetos Categories. Para obtener más información, consulte Consultas de [objetos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).

```csharp
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

```vb
Option Explicit On
Option Strict On

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

### <a name="entityclient"></a>EntityClient
El código de este ejemplo usa <xref:System.Data.EntityClient.EntityCommand> para ejecutar una consulta Entity SQL. Esta consulta devuelve una lista de registros que representan instancias del tipo de entidad Categories. Se usa <xref:System.Data.EntityClient.EntityDataReader> para obtener acceso a los registros de datos del conjunto de resultados. Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).

```csharp
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

```vb
Option Explicit On
Option Strict On

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

## <a name="linq-to-sql"></a>LINQ a SQL
El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName. Este ejemplo se basa en el contexto de datos Northwind. Para obtener más información, consulte [Introducción](./sql/linq/getting-started.md).

```csharp
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

```vb
Option Explicit On
Option Strict On

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

## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](ado-net-overview.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Crear aplicaciones de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))
- [Consultar un Entity Data Model (tareas de Entity Framework)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))
- [Cómo: Ejecutar una consulta que devuelve objetos de tipos anónimos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))
