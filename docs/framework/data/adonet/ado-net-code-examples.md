---
title: Ejemplos de código ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: aa91646a46807f26053b3d0df28c412bcc5a2f21
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825906"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="de77b-102">Ejemplos de código ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de77b-102">ADO.NET code examples</span></span>
<span data-ttu-id="de77b-103">Los listados de código de este tema muestran cómo recuperar datos de una base de datos utilizando las tecnologías ADO.NET siguientes:</span><span class="sxs-lookup"><span data-stu-id="de77b-103">The code listings in this topic demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="de77b-104">Proveedores de datos ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="de77b-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="de77b-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="de77b-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="de77b-106">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="de77b-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="de77b-107">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="de77b-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="de77b-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="de77b-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="de77b-109">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="de77b-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="de77b-110">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="de77b-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="de77b-111">ObjectQuery con tipo</span><span class="sxs-lookup"><span data-stu-id="de77b-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="de77b-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="de77b-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="de77b-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="de77b-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="de77b-114">Ejemplos de proveedor de datos ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de77b-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="de77b-115">En los listados de código siguientes se muestra cómo recuperar datos de una base de datos usando proveedores de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="de77b-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="de77b-116">Los datos se devuelven en `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="de77b-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="de77b-117">Para obtener más información, consulte [recuperar datos mediante DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).</span><span class="sxs-lookup"><span data-stu-id="de77b-117">For more information, see [Retrieving Data Using a DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="de77b-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="de77b-118">SqlClient</span></span>
<span data-ttu-id="de77b-119">El código en este ejemplo se da por supuesto que puede conectarse a la `Northwind` base de datos de ejemplo en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de77b-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="de77b-120">El código crea <xref:System.Data.SqlClient.SqlCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.SqlClient.SqlParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5.</span><span class="sxs-lookup"><span data-stu-id="de77b-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="de77b-121">El <xref:System.Data.SqlClient.SqlConnection> se abre dentro de un `using` bloque, lo que garantiza que los recursos se cierran y se eliminan cuando se cierra el código.</span><span class="sxs-lookup"><span data-stu-id="de77b-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="de77b-122">El código ejecuta el comando utilizando <xref:System.Data.SqlClient.SqlDataReader> y muestra los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="de77b-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="de77b-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="de77b-123">OleDb</span></span>
<span data-ttu-id="de77b-124">En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="de77b-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="de77b-125">El código crea <xref:System.Data.OleDb.OleDbCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.OleDb.OleDbParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5.</span><span class="sxs-lookup"><span data-stu-id="de77b-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="de77b-126"><xref:System.Data.OleDb.OleDbConnection> se abre dentro de un bloque `using`, que garantiza que los recursos se cierran y se eliminan cuando termina la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="de77b-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="de77b-127">El código ejecuta el comando utilizando <xref:System.Data.OleDb.OleDbDataReader> y muestra los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="de77b-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="de77b-128">Odbc</span><span class="sxs-lookup"><span data-stu-id="de77b-128">Odbc</span></span>
<span data-ttu-id="de77b-129">En el código de este ejemplo se asume que puede conectarse a la base de datos de ejemplo Northwind de Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="de77b-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="de77b-130">El código crea <xref:System.Data.Odbc.OdbcCommand> para seleccionar filas de la tabla Products, que añade <xref:System.Data.Odbc.OdbcParameter> para limitar los resultados a las filas con un UnitPrice mayor que el valor de parámetro especificado, en este caso 5.</span><span class="sxs-lookup"><span data-stu-id="de77b-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="de77b-131">El <xref:System.Data.Odbc.OdbcConnection> se abre dentro de un `using` bloque, lo que garantiza que los recursos se cierran y se eliminan cuando se cierra el código.</span><span class="sxs-lookup"><span data-stu-id="de77b-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="de77b-132">El código ejecuta el comando utilizando <xref:System.Data.Odbc.OdbcDataReader> y muestra los resultados en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="de77b-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a><span data-ttu-id="de77b-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="de77b-133">OracleClient</span></span>
<span data-ttu-id="de77b-134">En el código de este ejemplo se presupone una conexión a DEMO.CUSTOMER en un servidor Oracle.</span><span class="sxs-lookup"><span data-stu-id="de77b-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="de77b-135">También debe agregarse una referencia a System.Data.OracleClient.dll.</span><span class="sxs-lookup"><span data-stu-id="de77b-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="de77b-136">El código devuelve los datos en <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="de77b-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="de77b-137">Ejemplos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="de77b-137">Entity Framework examples</span></span>
<span data-ttu-id="de77b-138">En los listados de código siguientes se muestra cómo recuperar los datos de un origen de datos consultando las entidades de un Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="de77b-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="de77b-139">Estos ejemplos utilizan un modelo basado en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="de77b-139">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="de77b-140">Para obtener más información acerca de Entity Framework, vea [Introducción a Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).</span><span class="sxs-lookup"><span data-stu-id="de77b-140">For more information about Entity Framework, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="de77b-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="de77b-141">LINQ to Entities</span></span>
<span data-ttu-id="de77b-142">El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName.</span><span class="sxs-lookup"><span data-stu-id="de77b-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="de77b-143">Para obtener más información, consulte [LINQ: Introducción entidades](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="de77b-143">For more information, see [LINQ to Entities Overview](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).</span></span>

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

### <a name="typed-objectquery"></a><span data-ttu-id="de77b-144">ObjectQuery con establecimiento de tipos</span><span class="sxs-lookup"><span data-stu-id="de77b-144">Typed ObjectQuery</span></span>
<span data-ttu-id="de77b-145">En el código de este ejemplo se utiliza <xref:System.Data.Objects.ObjectQuery%601> para devolver los datos como objetos Categories.</span><span class="sxs-lookup"><span data-stu-id="de77b-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="de77b-146">Para obtener más información, consulte [las consultas de objeto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="de77b-146">For more information, see [Object Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

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

### <a name="entityclient"></a><span data-ttu-id="de77b-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="de77b-147">EntityClient</span></span>
<span data-ttu-id="de77b-148">El código de este ejemplo usa <xref:System.Data.EntityClient.EntityCommand> para ejecutar una consulta Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="de77b-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="de77b-149">Esta consulta devuelve una lista de registros que representan instancias del tipo de entidad Categories.</span><span class="sxs-lookup"><span data-stu-id="de77b-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="de77b-150">Se usa <xref:System.Data.EntityClient.EntityDataReader> para obtener acceso a los registros de datos del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="de77b-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="de77b-151">Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="de77b-151">For more information, see [EntityClient Provider for the Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>

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

## <a name="linq-to-sql"></a><span data-ttu-id="de77b-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="de77b-152">LINQ to SQL</span></span>
<span data-ttu-id="de77b-153">El código de este ejemplo usa una consulta LINQ para devolver los datos como objetos Categories, que se proyectan como un tipo anónimo que contiene solo las propiedades CategoryID y CategoryName.</span><span class="sxs-lookup"><span data-stu-id="de77b-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="de77b-154">Este ejemplo se basa en el contexto de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="de77b-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="de77b-155">Para más información, consulte [Introducción](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="de77b-155">For more information, see [Getting Started](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="de77b-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="de77b-156">See also</span></span>
- [<span data-ttu-id="de77b-157">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de77b-157">ADO.NET Overview</span></span>](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [<span data-ttu-id="de77b-158">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de77b-158">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- <span data-ttu-id="de77b-159">[Crear aplicaciones de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="de77b-159">[Creating Data Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="de77b-160">[Consultar un Entity Data Model (tareas de Entity Framework)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="de77b-160">[Querying an Entity Data Model (Entity Framework Tasks)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="de77b-161">[Cómo: Ejecutar una consulta que devuelve objetos de tipo anónimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="de77b-161">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>
- [<span data-ttu-id="de77b-162">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="de77b-162">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
