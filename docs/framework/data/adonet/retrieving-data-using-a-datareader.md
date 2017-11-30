---
title: Recuperar datos utilizando un objeto DataReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0b66ca2fbcc760598b771b4c02a46acc3c9c1d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="4dda2-102">Recuperar datos utilizando un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="4dda2-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="4dda2-103">Recuperar datos mediante un **DataReader** implica la creación de una instancia de la **comando** objeto y, a continuación, crear un **DataReader** mediante una llamada a  **Command.ExecuteReader** para recuperar filas de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4dda2-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="4dda2-104">En el ejemplo siguiente se muestra cómo utilizar un **DataReader** donde `reader` representa un DataReader válido y `command` representa un objeto Command válido.</span><span class="sxs-lookup"><span data-stu-id="4dda2-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="4dda2-105">Usa el **lectura** método de la **DataReader** objeto para obtener una fila de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4dda2-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="4dda2-106">Puede tener acceso a cada columna de la fila devuelta, pasando el nombre o la referencia ordinal de la columna a la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="4dda2-107">Sin embargo, para un rendimiento óptimo, el **DataReader** proporciona una serie de métodos que permiten tener acceso a los valores de las columnas en sus tipos de datos nativos (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="4dda2-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="4dda2-108">Para obtener una lista de métodos de descriptor de acceso con tipo de datos específico del proveedor **DataReaders**, consulte <xref:System.Data.OleDb.OleDbDataReader> y <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="4dda2-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="4dda2-109">Si se utilizan los métodos de descriptor de acceso con tipo, dando por supuesto que se conoce el tipo de datos subyacentes, se reduce el número de conversiones de tipo necesarias para recuperar el valor de una columna.</span><span class="sxs-lookup"><span data-stu-id="4dda2-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dda2-110">La versión de Windows Server 2003 de .NET Framework incluye una propiedad adicional para la **DataReader**, **HasRows**, lo que permite determinar si el **DataReader**ha devuelto algún resultado antes de leer de él.</span><span class="sxs-lookup"><span data-stu-id="4dda2-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="4dda2-111">En el ejemplo de código siguiente se recorre en iteración un **DataReader** objeto y devuelven dos columnas de cada fila.</span><span class="sxs-lookup"><span data-stu-id="4dda2-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="4dda2-112">El **DataReader** proporciona un flujo de datos que permite la lógica de procedimientos procesar los resultados de un origen de datos de forma secuencial eficazmente no almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="4dda2-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="4dda2-113">El **DataReader** es una buena opción para recuperar grandes cantidades de datos porque no se almacena en caché los datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="4dda2-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="4dda2-114">Cerrar el DataReader</span><span class="sxs-lookup"><span data-stu-id="4dda2-114">Closing the DataReader</span></span>  
 <span data-ttu-id="4dda2-115">Siempre debe llamar a la **cerrar** método cuando haya terminado de utilizar el **DataReader** objeto.</span><span class="sxs-lookup"><span data-stu-id="4dda2-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="4dda2-116">Si su **comando** contiene salida parámetros o valores devueltos, no estarán disponibles hasta que el **DataReader** está cerrado.</span><span class="sxs-lookup"><span data-stu-id="4dda2-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="4dda2-117">Tenga en cuenta que mientras un **DataReader** está abierto, el **conexión** está en uso exclusivo por que **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="4dda2-118">No se puede ejecutar ningún comando para el **conexión**, incluida la creación de otro **DataReader**, hasta que el original **DataReader** está cerrado.</span><span class="sxs-lookup"><span data-stu-id="4dda2-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dda2-119">No llame a **cerrar** o **Dispose** en un **conexión**, **DataReader**, o cualquier otro objeto administrado en el **Finalize**  método de la clase.</span><span class="sxs-lookup"><span data-stu-id="4dda2-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="4dda2-120">En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="4dda2-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="4dda2-121">Si la clase no dispone de los recursos no administrados, no incluya un **Finalize** método en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="4dda2-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="4dda2-122">Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="4dda2-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="4dda2-123">Recuperar varios conjuntos de resultados con NextResult</span><span class="sxs-lookup"><span data-stu-id="4dda2-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="4dda2-124">Si se devuelven varios conjuntos de resultados, el **DataReader** proporciona el **NextResult** método para recorrer en iteración el resultado se establece en orden.</span><span class="sxs-lookup"><span data-stu-id="4dda2-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="4dda2-125">En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="4dda2-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="4dda2-126">Obtener información del esquema a partir del DataReader</span><span class="sxs-lookup"><span data-stu-id="4dda2-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="4dda2-127">Mientras un **DataReader** está abierto, puede recuperar información de esquema sobre el actual conjunto de resultados mediante el **GetSchemaTable** método.</span><span class="sxs-lookup"><span data-stu-id="4dda2-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="4dda2-128">**GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual.</span><span class="sxs-lookup"><span data-stu-id="4dda2-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="4dda2-129">El **DataTable** contiene una fila por cada columna del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4dda2-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="4dda2-130">Cada columna de la fila de la tabla de esquema que se asigna a una propiedad de la columna devuelta en el conjunto de resultados, donde el **ColumnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4dda2-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="4dda2-131">En el ejemplo de código siguiente se muestra la información de esquema para **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="4dda2-132">Trabajar con capítulos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="4dda2-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="4dda2-133">Conjuntos jerárquicos de filas, o capítulos (tipo de OLE DB **DBTYPE_HCHAPTER**, tipo de ADO **Dbtype_hchapter**) se puede recuperar mediante el <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="4dda2-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="4dda2-134">Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, éste se devuelve como una columna en la que **DataReader** y se expone como un **DataReader** objeto.</span><span class="sxs-lookup"><span data-stu-id="4dda2-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="4dda2-135">ADO.NET **conjunto de datos** también puede usarse para representar conjuntos jerárquicos de filas utilizando relaciones de elementos primarios y secundarios entre tablas.</span><span class="sxs-lookup"><span data-stu-id="4dda2-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="4dda2-136">Para obtener más información, consulte [conjuntos de datos, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="4dda2-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="4dda2-137">En el ejemplo de código siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista.</span><span class="sxs-lookup"><span data-stu-id="4dda2-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="4dda2-138">Devolver resultados con cursores REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="4dda2-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="4dda2-139">El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="4dda2-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="4dda2-140">Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="4dda2-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="4dda2-141">Puede recuperar un **OracleDataReader** objeto, que representa un REF CURSOR de Oracle utilizando el <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método y, también puede especificar un <xref:System.Data.OracleClient.OracleCommand> que devuelve uno o varios cursores REF de Oracle como la  **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="4dda2-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="4dda2-142">Para obtener acceso a un REF CURSOR devuelto desde un origen de datos de Oracle, cree un **OracleCommand** para la consulta y agregue un parámetro de salida que hace referencia el REF CURSOR y la **parámetros** colección de su  **OracleCommand**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="4dda2-143">El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4dda2-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="4dda2-144">Establezca el tipo del parámetro para **OracleType.Cursor**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="4dda2-145">El **ExecuteReader** método de su **OracleCommand** devolverá un **OracleDataReader** para el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="4dda2-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="4dda2-146">Si su **OracleCommand** devuelve varios cursores REF CURSOR, agregue varios parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="4dda2-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="4dda2-147">Puede tener acceso a los distintos cursores REF CURSOR llamando el **OracleCommand.ExecuteReader** método.</span><span class="sxs-lookup"><span data-stu-id="4dda2-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="4dda2-148">La llamada a **ExecuteReader** devuelve un **OracleDataReader** hacer referencia al primer REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="4dda2-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="4dda2-149">A continuación, puede llamar a la **OracleDataReader.NextResult** método para tener acceso a los cursores REF CURSOR posteriores.</span><span class="sxs-lookup"><span data-stu-id="4dda2-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="4dda2-150">Aunque los parámetros en su **OracleCommand.Parameters** colección REF CURSOR parámetros de salida por su nombre, el **OracleDataReader** obtendrá acceso a éstos en el orden en que se agregaron a la  **Parámetros de** colección.</span><span class="sxs-lookup"><span data-stu-id="4dda2-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="4dda2-151">Por ejemplo, considere el siguiente paquete de Oracle y, concretamente, el cuerpo del paquete.</span><span class="sxs-lookup"><span data-stu-id="4dda2-151">For example, consider the following Oracle package and package body.</span></span>  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="4dda2-152">El siguiente código crea un **OracleCommand** que devuelve los cursores REF cursor del paquete anterior de Oracle mediante la adición de dos parámetros de tipo **OracleType.Cursor** a la **parámetros** colección.</span><span class="sxs-lookup"><span data-stu-id="4dda2-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="4dda2-153">El código siguiente devuelve los resultados del comando anterior utilizando el **lectura** y **NextResult** métodos de la **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="4dda2-154">Los parámetros REF CURSOR se devuelven en orden.</span><span class="sxs-lookup"><span data-stu-id="4dda2-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="4dda2-155">En el ejemplo siguiente se utiliza el comando anterior para rellenar un **conjunto de datos** con los resultados del paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="4dda2-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dda2-156">Para evitar un **OverflowException**, se recomienda que se controle también cualquier conversión del tipo NUMBER de Oracle a un tipo válido de .NET Framework antes de almacenar el valor de un **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="4dda2-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="4dda2-157">Puede usar el **FillError** evento para determinar si un **OverflowException** se ha producido.</span><span class="sxs-lookup"><span data-stu-id="4dda2-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="4dda2-158">Para obtener más información sobre la **FillError** eventos, vea [control de eventos de DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="4dda2-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4dda2-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dda2-159">See Also</span></span>  
 [<span data-ttu-id="4dda2-160">Trabajar con DataReaders</span><span class="sxs-lookup"><span data-stu-id="4dda2-160">Working with DataReaders</span></span>](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="4dda2-161">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="4dda2-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="4dda2-162">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="4dda2-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="4dda2-163">Recuperar información del esquema de base de datos</span><span class="sxs-lookup"><span data-stu-id="4dda2-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="4dda2-164">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4dda2-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
