---
title: Recuperar datos utilizando un objeto DataReader
ms.date: 10/259/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 134bb68b9cf60cc5082afefdd9eb87d991b6e0ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692761"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="02102-102">Recuperar datos mediante DataReader</span><span class="sxs-lookup"><span data-stu-id="02102-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="02102-103">Para recuperar datos mediante un **DataReader**, cree una instancia de la **comando** objeto y, a continuación, cree un **DataReader** mediante una llamada a **Command.ExecuteReader**  para recuperar filas de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="02102-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="02102-104">El **DataReader** proporciona una secuencia sin almacenamiento en búfer de datos que permite la lógica de procedimientos procesar secuencialmente de forma eficaz los resultados de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="02102-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="02102-105">El **DataReader** es una buena elección cuando se está recuperando grandes cantidades de datos porque no se almacena en caché los datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="02102-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="02102-106">El ejemplo siguiente se muestra cómo utilizar un **DataReader**, donde `reader` representa un DataReader válido y `command` representa un objeto Command válido.</span><span class="sxs-lookup"><span data-stu-id="02102-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="02102-107">Use la **DataReader.Read** método para obtener una fila de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="02102-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="02102-108">Puede tener acceso a cada columna de la fila devuelta, pasando el nombre o número ordinal de la columna a la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="02102-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="02102-109">Sin embargo, para obtener el mejor rendimiento, la **DataReader** proporciona una serie de métodos que permiten tener acceso a los valores de columna en sus tipos de datos nativos (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="02102-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="02102-110">Para obtener una lista de métodos de descriptor de acceso con tipo de datos específico del proveedor **DataReaders**, consulte <xref:System.Data.OleDb.OleDbDataReader> y <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="02102-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="02102-111">Mediante los métodos de descriptor de acceso con tipo cuando se saben que los datos subyacentes tipo reduce la cantidad de conversión de tipo necesaria para recuperar el valor de columna.</span><span class="sxs-lookup"><span data-stu-id="02102-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="02102-112">En el ejemplo siguiente se recorre un **DataReader** de objetos y devuelve dos columnas de cada fila.</span><span class="sxs-lookup"><span data-stu-id="02102-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="02102-113">Cerrar el DataReader</span><span class="sxs-lookup"><span data-stu-id="02102-113">Closing the DataReader</span></span>  
 <span data-ttu-id="02102-114">Llame siempre a la **cerrar** método cuando haya terminado de utilizar el **DataReader** objeto.</span><span class="sxs-lookup"><span data-stu-id="02102-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="02102-115">Si su **comando** contiene la salida de parámetros o valores devueltos, dichos valores no están disponibles hasta que el **DataReader** está cerrado.</span><span class="sxs-lookup"><span data-stu-id="02102-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="02102-116">Mientras un **DataReader** está abierto, el **conexión** está en uso de forma exclusiva **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="02102-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="02102-117">No se puede ejecutar ningún comando para el **conexión**, incluida la creación de otro **DataReader**, hasta que el original **DataReader** está cerrado.</span><span class="sxs-lookup"><span data-stu-id="02102-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02102-118">No llame a **cerrar** o **Dispose** en un **conexión**, un **DataReader**, o cualquier otro objeto administrado en el **Finalize**  método de la clase.</span><span class="sxs-lookup"><span data-stu-id="02102-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="02102-119">En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase.</span><span class="sxs-lookup"><span data-stu-id="02102-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="02102-120">Si la clase no dispone de los recursos no administrados, no incluya un **Finalize** método en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="02102-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="02102-121">Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="02102-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="02102-122">Recuperando resultados múltiples establece con NextResult</span><span class="sxs-lookup"><span data-stu-id="02102-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="02102-123">Si el **DataReader** devuelve varios conjuntos de resultados, llamada la **NextResult** método para recorrer en iteración el resultado se establece secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="02102-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="02102-124">En el siguiente ejemplo se muestra el <xref:System.Data.SqlClient.SqlDataReader> mientras procesa los resultados de las dos instrucciones SELECT mediante el método <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="02102-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="02102-125">Obtención de información de esquema de DataReader</span><span class="sxs-lookup"><span data-stu-id="02102-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="02102-126">Mientras un **DataReader** está abierto, puede recuperar información del esquema acerca del actual conjunto de resultados mediante el **GetSchemaTable** método.</span><span class="sxs-lookup"><span data-stu-id="02102-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="02102-127">**GetSchemaTable** devuelve un <xref:System.Data.DataTable> objeto rellenado con filas y columnas que contienen la información de esquema para el conjunto de resultados actual.</span><span class="sxs-lookup"><span data-stu-id="02102-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="02102-128">El **DataTable** contiene una fila por cada columna del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="02102-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="02102-129">Cada columna de la tabla de esquema se asigna a una propiedad de las columnas devueltas en las filas del resultado conjunto, donde el **ColumnName** es el nombre de la propiedad y el valor de la columna es el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="02102-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="02102-130">El ejemplo siguiente escribe la información de esquema **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="02102-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="02102-131">Trabajar con capítulos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="02102-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="02102-132">Conjuntos jerárquicos de filas o capítulos (tipo de OLE DB **DBTYPE_HCHAPTER**, tipo de ADO **adChapter**), se puede recuperar mediante el <xref:System.Data.OleDb.OleDbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="02102-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="02102-133">Cuando una consulta que incluye un capítulo se devuelve como un **DataReader**, éste se devuelve como una columna en la que **DataReader** y se expone como un **DataReader** objeto.</span><span class="sxs-lookup"><span data-stu-id="02102-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="02102-134">ADO.NET **DataSet** también se puede usar para representar conjuntos jerárquicos de filas utilizando relaciones de elementos primarios y secundarios entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="02102-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="02102-135">Para obtener más información, consulte [DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span><span class="sxs-lookup"><span data-stu-id="02102-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="02102-136">En el ejemplo de código siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista.</span><span class="sxs-lookup"><span data-stu-id="02102-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="02102-137">Devolver resultados con cursores REF cursor de Oracle</span><span class="sxs-lookup"><span data-stu-id="02102-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="02102-138">El proveedor de datos .NET Framework para Oracle admite el uso de cursores REF CURSOR de Oracle para devolver los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="02102-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="02102-139">Un REF CURSOR de Oracle se devuelve en forma de objeto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="02102-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="02102-140">Puede recuperar un <xref:System.Data.OracleClient.OracleDataReader> objeto que representa un REF CURSOR de Oracle mediante el uso de la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> método.</span><span class="sxs-lookup"><span data-stu-id="02102-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="02102-141">También puede especificar un <xref:System.Data.OracleClient.OracleCommand> que devuelve uno o varios cursores REF de Oracle como el **SelectCommand** para un <xref:System.Data.OracleClient.OracleDataAdapter> utilizado para rellenar un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="02102-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="02102-142">Para obtener acceso a un REF CURSOR devuelto desde un origen de datos de Oracle, cree un <xref:System.Data.OracleClient.OracleCommand> para la consulta y agregue un parámetro de salida que hace referencia el REF CURSOR y la <xref:System.Data.OracleClient.OracleCommand.Parameters> colección de su <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="02102-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="02102-143">El nombre del parámetro debe coincidir con el nombre del parámetro REF CURSOR de la consulta.</span><span class="sxs-lookup"><span data-stu-id="02102-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="02102-144">Establezca el tipo del parámetro para <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="02102-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="02102-145">El <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método de su <xref:System.Data.OracleClient.OracleCommand> devuelve un <xref:System.Data.OracleClient.OracleDataReader> para el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="02102-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="02102-146">Si su <xref:System.Data.OracleClient.OracleCommand> devuelve varios cursores REF CURSOR, agregue varios parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="02102-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="02102-147">Puede tener acceso a los distintos cursores REF CURSOR llamando a la <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="02102-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="02102-148">La llamada a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> devuelve un <xref:System.Data.OracleClient.OracleDataReader> hacer referencia al primer REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="02102-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="02102-149">A continuación, puede llamar a la <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> método para acceder a los cursores REF CURSOR posteriores.</span><span class="sxs-lookup"><span data-stu-id="02102-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="02102-150">Aunque los parámetros en su <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> parámetros de salida de coincidencia de la colección el REF CURSOR por su nombre, el <xref:System.Data.OracleClient.OracleDataReader> tiene acceso a ellos en el orden en que se agregaron a la <xref:System.Data.OracleClient.OracleCommand.Parameters> colección.</span><span class="sxs-lookup"><span data-stu-id="02102-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="02102-151">Por ejemplo, considere el siguiente paquete de Oracle y, concretamente, el cuerpo del paquete.</span><span class="sxs-lookup"><span data-stu-id="02102-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="02102-152">El código siguiente crea un <xref:System.Data.OracleClient.OracleCommand> que devuelve los cursores REF cursor del paquete anterior de Oracle mediante la adición de dos parámetros de tipo <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> a la <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> colección.</span><span class="sxs-lookup"><span data-stu-id="02102-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="02102-153">El código siguiente devuelve los resultados del comando anterior utilizando el <xref:System.Data.OracleClient.OracleDataReader.Read> y <xref:System.Data.OracleClient.OracleDataReader.NextResult> métodos de la <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="02102-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="02102-154">Los parámetros REF CURSOR se devuelven en orden.</span><span class="sxs-lookup"><span data-stu-id="02102-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="02102-155">En el ejemplo siguiente se usa el comando anterior para rellenar un <xref:System.Data.DataSet> con los resultados del paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="02102-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
>  <span data-ttu-id="02102-156">Para evitar un **OverflowException**, se recomienda que controle también cualquier conversión de tipo NUMBER de Oracle a un tipo válido de .NET Framework antes de almacenar el valor en un <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="02102-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="02102-157">Puede usar el <xref:System.Data.Common.DataAdapter.FillError> evento para determinar si un **OverflowException** se ha producido.</span><span class="sxs-lookup"><span data-stu-id="02102-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="02102-158">Para obtener más información sobre la <xref:System.Data.Common.DataAdapter.FillError> eventos, consulte [controlar eventos de DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="02102-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02102-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="02102-159">See also</span></span>
- [<span data-ttu-id="02102-160">Trabajar con DataReaders</span><span class="sxs-lookup"><span data-stu-id="02102-160">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)
- [<span data-ttu-id="02102-161">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="02102-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="02102-162">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="02102-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="02102-163">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="02102-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="02102-164">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="02102-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
