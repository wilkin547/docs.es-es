---
title: Rellenar un conjunto de datos desde un objeto DataAdapter
description: Obtenga información sobre cómo rellenar un conjunto de datos desde un DataAdapter en ADO.NET, que proporciona un modelo de programación relacional coherente independiente del origen de datos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
ms.openlocfilehash: ac84af884238b166266d4206802878c1e21169fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177415"
---
# <a name="populating-a-dataset-from-a-dataadapter"></a>Rellenar un conjunto de datos desde un objeto DataAdapter

ADO.NET <xref:System.Data.DataSet> es una representación residente en memoria de los datos que proporciona un modelo de programación relacional coherente independiente del origen de datos. `DataSet` representa un conjunto completo de datos que incluye tablas, restricciones y relaciones entre las tablas. Dado que `DataSet` es independiente del origen de datos, `DataSet` puede incluir datos locales de la aplicación y datos de otros muchos orígenes. La interacción con los orígenes de datos existentes se controla mediante el `DataAdapter`.  
  
 La propiedad `SelectCommand` de `DataAdapter` es un objeto `Command` que recupera datos del origen de datos. Las propiedades `InsertCommand`, `UpdateCommand`y `DeleteCommand` de `DataAdapter` son objetos `Command` que permiten administrar las actualizaciones de los datos en el origen de datos para reflejar las modificaciones efectuadas en los datos de `DataSet`. Estas propiedades se describen con más detalle en [Actualizar orígenes de datos con DataAdapters](updating-data-sources-with-dataadapters.md).  
  
 El método `Fill` de `DataAdapter` se usa para rellenar un objeto `DataSet` con los resultados del elemento `SelectCommand` de `DataAdapter`. `Fill` toma como argumentos un elemento `DataSet` que se debe rellenar y un objeto `DataTable` o el nombre del objeto `DataTable` que se debe rellenar con las filas que devuelve `SelectCommand`.  
  
> [!NOTE]
> El uso de `DataAdapter` para recuperar la totalidad de una tabla lleva tiempo, en especial si la tabla incluye un gran número de filas. Esto se debe a que el acceso a la base de datos, la localización y el procesamiento de los datos, y la posterior transferencia de los mismos al cliente son procesos largos. La extracción de la tabla completa al cliente también bloquea todas las filas en el servidor. Para mejorar el rendimiento, puede usar la cláusula `WHERE` para reducir en gran medida el número de filas que se devuelven al cliente. También puede reducir la cantidad de datos que se devuelven al cliente si enumera de forma explícita las columnas necesarias en la instrucción `SELECT` . Otra solución consiste en recuperar las filas por lotes (por ejemplo varios cientos de filas de una vez) y recuperar solo el siguiente lote cuando el cliente haya finalizado con el lote actual.  
  
 El método `Fill` utiliza el objeto `DataReader` de forma implícita para devolver los nombres y tipos de columna que se usan para crear las tablas de `DataSet`, y los datos para rellenar las filas de las tablas en `DataSet`. Las tablas y columnas solo se crean cuando no existen; en caso contrario, `Fill` utiliza el esquema existente de `DataSet` . Los tipos de columna se crean como tipos de .NET Framework de acuerdo con las tablas de las [asignaciones de tipos de datos en ADO.net](data-type-mappings-in-ado-net.md). Las claves principales no se crean a menos que existan en el origen de datos y `DataAdapter` **.**`MissingSchemaAction` está establecido en `MissingSchemaAction` **.** `AddWithKey` . Si el método `Fill` encuentra que una tabla tiene una clave principal, sobrescribe los datos de `DataSet` con los del origen de datos en las filas donde los valores de columna de clave principal coinciden con los de la fila que devuelve el origen de datos. Si no se detecta ninguna clave principal, los datos se agregan a las tablas de `DataSet`. `Fill` utiliza las asignaciones que pueden existir al rellenar `DataSet` (vea las [asignaciones DataTable y DataColumn de DataAdapter](dataadapter-datatable-and-datacolumn-mappings.md)).  
  
> [!NOTE]
> Si `SelectCommand` devuelve los resultados de OUTER JOIN, `DataAdapter` no establece un valor `PrimaryKey` para el objeto `DataTable`resultante. Debe definir `PrimaryKey` para asegurarse de que las filas duplicadas se resuelven correctamente. Para obtener más información, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).  
  
 En el ejemplo de código siguiente se crea una instancia de <xref:System.Data.SqlClient.SqlDataAdapter> que utiliza un objeto <xref:System.Data.SqlClient.SqlConnection> a la base de datos `Northwind` de Microsoft SQL Server y se rellena un objeto <xref:System.Data.DataTable> en un `DataSet` con la lista de clientes. La instrucción SQL y los argumentos <xref:System.Data.SqlClient.SqlConnection> pasados al constructor <xref:System.Data.SqlClient.SqlDataAdapter> se utilizan para crear la propiedad <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> del <xref:System.Data.SqlClient.SqlDataAdapter>.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> El código que se muestra en este ejemplo no abre ni cierra explícitamente el objeto `Connection`. El método `Fill` abre de forma implícita el objeto `Connection` que `DataAdapter` utiliza cuando encuentra que la conexión no está abierta todavía. Si el método `Fill` ha abierto la conexión, también la cierra cuando el método `Fill` deja de utilizarla. Este hecho simplifica el código cuando se trabaja con una operación única, como `Fill` o `Update`. Sin embargo, en el caso de que se estén realizando varias operaciones que necesiten tener abierta una conexión, se puede mejorar el rendimiento de la aplicación llamando explícitamente al método `Open` de `Connection`, realizando las operaciones en el origen de datos y, finalmente, llamando al método `Close` de `Connection`. Es conveniente mantener abiertas las conexiones con el origen de datos el menor tiempo posible para liberar recursos, de manera que estén disponibles para otras aplicaciones cliente.  
  
## <a name="multiple-result-sets"></a>Varios conjuntos de resultados  

 Si `DataAdapter` encuentra varios conjuntos de resultados, crea varias tablas en `DataSet`. Las tablas reciben de forma predeterminada el nombre secuencial Table*N*, comenzando por "Table" que representa Table0. Si se pasa un nombre de tabla como argumento al método `Fill` , las tablas reciben de forma predeterminada el nombre secuencial TableName*N*, comenzando por "TableName" que representa TableName0.  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a>Llenar un DataSet desde múltiples DataAdapter  

 `DataAdapter`Se puede usar cualquier número de objetos con `DataSet` . Cada `DataAdapter` se puede usar para rellenar uno o varios objetos `DataTable` y resolver de nuevo las actualizaciones en el origen de datos correspondiente. Se pueden agregar objetos`DataRelation` y `Constraint` a `DataSet` localmente, lo que permite relacionar datos procedentes de varios orígenes distintos. Por ejemplo, un `DataSet` puede contener datos de una base de datos de Microsoft SQL Server, una base de datos de IBM DB2 expuesta mediante OLE DB y un origen de datos que genera secuencias XML. La comunicación con cada origen de datos se puede controlar usando uno o varios objetos `DataAdapter` .  
  
### <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se rellena una lista de clientes a partir de la base de datos `Northwind` almacenada en Microsoft SQL Server, y una lista de pedidos a partir de la base de datos `Northwind` almacenada en Microsoft Access 2000. Las tablas rellenas se relacionan entre sí mediante `DataRelation`, con lo que se puede mostrar una lista de clientes con los pedidos que ha realizado cada uno. Para obtener más información acerca de los `DataRelation` objetos, vea [Agregar DataRelations](./dataset-datatable-dataview/adding-datarelations.md) y [navegar por DataRelations](./dataset-datatable-dataview/navigating-datarelations.md).  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a>Tipo decimal de SQL Server  

 De forma predeterminada, `DataSet` almacena los datos mediante .NET Framework tipos de datos. En la mayor parte de las aplicaciones, estos tipos proporcionan una representación adecuada de la información del origen de datos. Sin embargo, esa representación puede ocasionar problemas cuando el tipo de datos del origen de datos es decimal o numérico de SQL Server. El `decimal` tipo de datos .NET Framework permite un máximo de 28 dígitos significativos, mientras que el `decimal` tipo de datos SQL Server permite 38 dígitos significativos. Si `SqlDataAdapter` determina durante una operación `Fill` que la precisión de un campo `decimal` de SQL Server es superior a 28 caracteres, la fila actual no se agrega a `DataTable`. En su lugar, se produce el evento `FillError` que permite determinar si se va a producir o no una pérdida de precisión y tomar las medidas adecuadas. Para obtener más información sobre el `FillError` evento, vea [controlar eventos DataAdapter](handling-dataadapter-events.md). Para obtener el valor `decimal` de SQL Server, también se puede utilizar un objeto <xref:System.Data.SqlClient.SqlDataReader> y llamar al método <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> .  
  
 ADO.NET 2,0 presentó compatibilidad mejorada con <xref:System.Data.SqlTypes> en `DataSet` . Para obtener más información, consulta [SqlTypes and the DataSet](./sql/sqltypes-and-the-dataset.md).  
  
## <a name="ole-db-chapters"></a>Capítulos de OLE DB  

 Se pueden usar conjuntos jerárquicos de filas, o capítulos (tipo `DBTYPE_HCHAPTER`de OLE DB y tipo `adChapter`de ADO), para rellenar el contenido de `DataSet`. Cuando <xref:System.Data.OleDb.OleDbDataAdapter> encuentra una columna que tiene un capítulo durante una operación `Fill` , se crea un objeto `DataTable` para dicha columna y la tabla se rellena con las columnas y filas del capítulo. Para asignar un nombre a la tabla creada para la columna con capítulo se usa tanto el nombre de la tabla primaria como el de la columna con capítulo. El formato del nombre es "*nombreDeTablaPrimariaNombreDeColumnaConCapítulo*". Si ya existe una tabla en `DataSet` que tenga el nombre de la columna con capítulo, la tabla actual se rellena con los datos del capítulo. Si ninguna de las columnas de la tabla existente coincide con una de las columnas del capítulo, se agrega una nueva columna a la tabla.  
  
 Antes de que las tablas de `DataSet` se rellenen con los datos de las columnas con capítulos, se crea una relación entre las tablas primaria y secundaria del conjunto jerárquico de filas; para ello, se agrega una columna de tipo entero a las tablas primaria y secundaria, se establece el valor de incremento automático para la columna de la tabla primaria y se crea un objeto `DataRelation` usando las columnas agregadas de ambas tablas. Para asignar un nombre a la relación se utilizan los nombres de la tabla primaria y de la columna con capítulo. El formato es "*nombreDeTablaPrimariaNombreDeColumnaConCapítulo*".  
  
 Tenga en cuenta que la columna relacionada solo existe en `DataSet`. Las operaciones de relleno que se realicen posteriormente desde el origen de datos pueden provocar que se agreguen nuevas filas a las tablas en lugar de que se introduzcan los cambios en las filas existentes.  
  
 Tenga en cuenta además que, si se utiliza una sobrecarga de `DataAdapter.Fill` que acepte un objeto `DataTable`, solo se rellanará esa tabla. En este caso también se agrega a la tabla una columna de tipo entero y con incremento automático, aunque no se crea ni rellena ninguna tabla secundaria, ni se crea ninguna relación.  
  
 En el ejemplo siguiente se utiliza el proveedor MSDataShape para generar un capítulo con la columna de pedidos realizados por cada uno de los clientes de una lista. A continuación, se rellena un `DataSet` con los datos.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 Una vez completada la operación `Fill` , `DataSet` contiene dos tablas: `Customers` y `CustomersOrders`, donde `CustomersOrders` representa la columna con capítulo. Se agrega una columna adicional denominada `Orders` a la tabla `Customers` , y una columna adicional denominada `CustomersOrders` a la tabla `CustomersOrders` . Se establece el valor de incremento automático para la columna `Orders` de la tabla `Customers` . Se crea también una relación `DataRelation`, `CustomersOrders`, utilizando las columnas que se han agregado a las tablas, siendo `Customers` la tabla primaria. Las siguientes tablas muestran algunos ejemplos de los resultados.  
  
### <a name="tablename-customers"></a>Nombre de tabla: Customers  
  
|Identificador de cliente|CompanyName|Orders (Pedidos)|  
|----------------|-----------------|------------|  
|ALFKI|Alfreds Futterkiste|0|  
|ANATR|Ana Trujillo Emparedados y helados|1|  
  
### <a name="tablename-customersorders"></a>Nombre de tabla: CustomersOrders  
  
|Identificador de cliente|OrderID|CustomersOrders|  
|----------------|-------------|---------------------|  
|ALFKI|10643|0|  
|ALFKI|10692|0|  
|ANATR|10308|1|  
|ANATR|10625|1|  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Asignaciones de tipos de datos en ADO.NET](data-type-mappings-in-ado-net.md)
- [Modificar datos con un objeto DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Conjuntos de resultados activos múltiples (MARS)](./sql/multiple-active-result-sets-mars.md)
- [Información general de ADO.NET](ado-net-overview.md)
