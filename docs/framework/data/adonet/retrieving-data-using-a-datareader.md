---
title: Recuperar datos utilizando un objeto DataReader
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: f3add49d48a569664d4cbb6b5c26d5f3379b6f18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794414"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="16b99-102">Recuperación de datos mediante DataReader</span><span class="sxs-lookup"><span data-stu-id="16b99-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="16b99-103">Para recuperar datos mediante un **DataReader**, cree una instancia del objeto de **comando** y, a continuación, cree un **DataReader** mediante una llamada a **Command. ExecuteReader** para recuperar las filas de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="16b99-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="16b99-104">**DataReader** proporciona un flujo de datos no almacenado en búfer que permite que la lógica de procedimientos procese eficazmente los resultados de un origen de datos de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="16b99-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="16b99-105">**DataReader** es una buena elección cuando se recuperan grandes cantidades de datos porque los datos no se almacenan en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="16b99-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="16b99-106">En el ejemplo siguiente se muestra el uso de **DataReader**, donde `reader` representa un DataReader válido y `command` representa un objeto de comando válido.</span><span class="sxs-lookup"><span data-stu-id="16b99-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="16b99-107">Use el método **DataReader. Read** para obtener una fila de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="16b99-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="16b99-108">Puede tener acceso a cada columna de la fila devuelta pasando el nombre o el número ordinal de la columna al **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="16b99-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="16b99-109">Sin embargo, para obtener el mejor rendimiento, **DataReader** proporciona una serie de métodos que le permiten tener acceso a los valores de columna en sus tipos de datos nativos (**GetDateTime**, **getDouble**, **GetGuid**, **GetInt32**, etc.).</span><span class="sxs-lookup"><span data-stu-id="16b99-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="16b99-110">Para obtener una lista de métodos de descriptor de acceso con tipo para los **DataReader**específicos <xref:System.Data.OleDb.OleDbDataReader> del <xref:System.Data.SqlClient.SqlDataReader>proveedor de datos, vea y.</span><span class="sxs-lookup"><span data-stu-id="16b99-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="16b99-111">El uso de los métodos de descriptor de acceso con tipo cuando se conoce el tipo de datos subyacente reduce la cantidad de conversión de tipos necesaria al recuperar el valor de la columna.</span><span class="sxs-lookup"><span data-stu-id="16b99-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="16b99-112">En el ejemplo siguiente se recorre en iteración un objeto **DataReader** y se devuelven dos columnas de cada fila.</span><span class="sxs-lookup"><span data-stu-id="16b99-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="16b99-113">Cerrar el DataReader</span><span class="sxs-lookup"><span data-stu-id="16b99-113">Closing the DataReader</span></span>  
 <span data-ttu-id="16b99-114">Llame siempre al método **Close** cuando haya terminado de usar el objeto **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="16b99-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="16b99-115">Si el **comando** contiene parámetros de salida o valores devueltos, esos valores no estarán disponibles hasta que se cierre **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="16b99-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="16b99-116">Mientras un **DataReader** está abierto, la **conexión** está en uso exclusivamente por parte de **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="16b99-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="16b99-117">No se puede ejecutar ningún comando para la **conexión**, incluida la creación de otro **DataReader**, hasta que se cierre el **DataReader** original.</span><span class="sxs-lookup"><span data-stu-id="16b99-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16b99-118">No llame a **Close** o **Dispose** en una **conexión**, **DataReader**o cualquier otro objeto administrado en el método **Finalize** de la clase.</span><span class="sxs-lookup"><span data-stu-id="16b99-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="16b99-119">En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="16b99-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="16b99-120">Si la clase no posee recursos no administrados, no incluya un método **Finalize** en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="16b99-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="16b99-121">Para obtener más información, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="16b99-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="16b99-122">Recuperar varios conjuntos de resultados mediante NextResult</span><span class="sxs-lookup"><span data-stu-id="16b99-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="16b99-123">Si **DataReader** devuelve varios conjuntos de resultados, llame al método **NextResult** para recorrer en iteración los conjuntos de resultados secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="16b99-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="16b99-124">En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="16b99-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="16b99-125">Obtención de información de esquema de DataReader</span><span class="sxs-lookup"><span data-stu-id="16b99-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="16b99-126">Mientras un **DataReader** está abierto, puede recuperar información de esquema sobre el conjunto de resultados actual mediante el método **GetSchemaTable** .</span><span class="sxs-lookup"><span data-stu-id="16b99-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="16b99-127">**GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual.</span><span class="sxs-lookup"><span data-stu-id="16b99-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="16b99-128">El **objeto DataTable** contiene una fila por cada columna del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="16b99-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="16b99-129">Cada columna de la tabla de esquema se asigna a una propiedad de las columnas devueltas en las filas del conjunto de resultados, donde **columnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="16b99-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="16b99-130">En el ejemplo siguiente se escribe la información de esquema de **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="16b99-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="16b99-131">Trabajar con capítulos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="16b99-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="16b99-132">Los conjuntos<xref:System.Data.OleDb.OleDbDataReader>de filas jerárquicos, o capítulos (OLE DB Type **DBTYPE_HCHAPTER**, adChapter Type de ADO), se pueden recuperar mediante.</span><span class="sxs-lookup"><span data-stu-id="16b99-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="16b99-133">Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, el capítulo se devuelve como una columna en ese **DataReader** y se expone como un objeto **DataReader** .</span><span class="sxs-lookup"><span data-stu-id="16b99-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="16b99-134">El **conjunto** de ADO.net también se puede usar para representar conjuntos de filas jerárquicos mediante el uso de relaciones de elementos primarios y secundarios entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="16b99-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="16b99-135">Para obtener más información, vea conjuntos de datos [, tablas de datos y vistas](./dataset-datatable-dataview/index.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="16b99-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="16b99-136">En el ejemplo de código siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista.</span><span class="sxs-lookup"><span data-stu-id="16b99-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="16b99-137">Devolver resultados con CURSOres REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="16b99-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="16b99-138">El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="16b99-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="16b99-139">Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="16b99-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="16b99-140">Puede recuperar un <xref:System.Data.OracleClient.OracleDataReader> objeto que representa un cursor Ref cursor de Oracle mediante el <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método.</span><span class="sxs-lookup"><span data-stu-id="16b99-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="16b99-141">También <xref:System.Data.OracleClient.OracleCommand> puede especificar un que devuelve uno o varios cursores REF cursor de Oracle como **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un. <xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="16b99-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="16b99-142">Para tener acceso a un Ref cursor devuelto desde un origen de datos <xref:System.Data.OracleClient.OracleCommand> de Oracle, cree un para la consulta y agregue un parámetro de salida que <xref:System.Data.OracleClient.OracleCommand.Parameters> haga referencia al <xref:System.Data.OracleClient.OracleCommand>cursor Ref a la colección de.</span><span class="sxs-lookup"><span data-stu-id="16b99-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="16b99-143">El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta.</span><span class="sxs-lookup"><span data-stu-id="16b99-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="16b99-144">Establezca el tipo del parámetro en <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16b99-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="16b99-145">El <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método <xref:System.Data.OracleClient.OracleDataReader> de devuelve un para el cursor Ref. <xref:System.Data.OracleClient.OracleCommand></span><span class="sxs-lookup"><span data-stu-id="16b99-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="16b99-146"><xref:System.Data.OracleClient.OracleCommand> Si devuelve varios cursores REF cursor, agregue varios parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="16b99-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="16b99-147">Puede tener acceso a los diferentes cursores REF cursor llamando <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> al método.</span><span class="sxs-lookup"><span data-stu-id="16b99-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="16b99-148">La llamada a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> devuelve un <xref:System.Data.OracleClient.OracleDataReader> que hace referencia al primer cursor Ref.</span><span class="sxs-lookup"><span data-stu-id="16b99-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="16b99-149">Después, puede llamar al <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> método para tener acceso a los siguientes cursores REF cursor.</span><span class="sxs-lookup"><span data-stu-id="16b99-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="16b99-150">Aunque los parámetros de la <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> colección coinciden con los parámetros de salida Ref cursor por <xref:System.Data.OracleClient.OracleDataReader> nombre, el obtiene acceso a ellos en el orden en que se <xref:System.Data.OracleClient.OracleCommand.Parameters> agregaron a la colección.</span><span class="sxs-lookup"><span data-stu-id="16b99-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="16b99-151">Por ejemplo, considere el siguiente paquete de Oracle y, concretamente, el cuerpo del paquete.</span><span class="sxs-lookup"><span data-stu-id="16b99-151">For example, consider the following Oracle package and package body.</span></span>  
  
```sql
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
  
 <span data-ttu-id="16b99-152">En el código siguiente se <xref:System.Data.OracleClient.OracleCommand> crea un que devuelve los cursores REF cursor del paquete anterior de Oracle agregando dos <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> parámetros de <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> tipo a la colección.</span><span class="sxs-lookup"><span data-stu-id="16b99-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="16b99-153">El código siguiente devuelve los resultados del comando anterior mediante los <xref:System.Data.OracleClient.OracleDataReader.Read> métodos y <xref:System.Data.OracleClient.OracleDataReader.NextResult> de. <xref:System.Data.OracleClient.OracleDataReader></span><span class="sxs-lookup"><span data-stu-id="16b99-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="16b99-154">Los parámetros REF CURSOR se devuelven en orden.</span><span class="sxs-lookup"><span data-stu-id="16b99-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="16b99-155">En el ejemplo siguiente se usa el comando anterior para <xref:System.Data.DataSet> rellenar un con los resultados del paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="16b99-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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

> [!NOTE]
> <span data-ttu-id="16b99-156">Para evitar una **excepción OverflowException**, se recomienda que también se controle cualquier conversión del tipo Number de Oracle a un tipo de .NET Framework válido antes de almacenar <xref:System.Data.DataRow>el valor en.</span><span class="sxs-lookup"><span data-stu-id="16b99-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="16b99-157">Puede utilizar el <xref:System.Data.Common.DataAdapter.FillError> evento para determinar si se ha producido una **excepción OverflowException** .</span><span class="sxs-lookup"><span data-stu-id="16b99-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="16b99-158">Para obtener más información sobre <xref:System.Data.Common.DataAdapter.FillError> el evento, vea [controlar eventos DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="16b99-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b99-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="16b99-159">See also</span></span>

- [<span data-ttu-id="16b99-160">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="16b99-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="16b99-161">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="16b99-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="16b99-162">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="16b99-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="16b99-163">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="16b99-163">ADO.NET Overview</span></span>](ado-net-overview.md)
