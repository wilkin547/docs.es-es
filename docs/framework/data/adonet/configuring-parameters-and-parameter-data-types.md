---
title: Configurar parámetros y tipos de datos de parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 537d8a2c-d40b-4000-83eb-bc1fcc93f707
ms.openlocfilehash: 320a45af1c2f3b460c23d8320c456120643902f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759548"
---
# <a name="configuring-parameters-and-parameter-data-types"></a>Configurar parámetros y tipos de datos de parámetros
Los objetos de comando usan parámetros para pasar valores a instrucciones SQL o procedimientos almacenados que permiten realizar operaciones de comprobación de tipos y validación. A diferencia del texto de comando, la entrada de parámetros se trata como un valor literal, y no como código ejecutable. De esta forma, se protege contra ataques por "inyección de código SQL", en los que un atacante inserta un comando que pone en peligro la seguridad del servidor en una instrucción SQL.  
  
 Los comandos parametrizados también pueden mejorar el rendimiento de ejecución de la consulta, ya que ayudan al servidor de bases de datos a que haga coincidir precisamente el comando entrante con un plan de consulta almacenado en caché adecuado. Para obtener más información, consulte [Almacenar en caché y volver a utilizar un plan de ejecución](http://go.microsoft.com/fwlink/?LinkId=120424) y [Parámetros y reutilización de un plan de ejecución](http://go.microsoft.com/fwlink/?LinkId=120423) en los Libros en pantalla de SQL Server. Además de las ventajas en la seguridad y el rendimiento, los comandos con parámetros proporcionan un método práctico para organizar los valores que se pasan a un origen de datos.  
  
 Para crear un objeto <xref:System.Data.Common.DbParameter> , se puede usar su constructor o bien se puede agregar a <xref:System.Data.Common.DbCommand.DbParameterCollection%2A> mediante una llamada al método `Add` de la colección <xref:System.Data.Common.DbParameterCollection> . El método `Add` acepta como entrada argumentos del constructor o cualquier objeto de parámetro ya existente, en función del proveedor de datos.  
  
## <a name="supplying-the-parameterdirection-property"></a>Proporcionar la propiedad ParameterDirection  
 Cuando se agregan parámetros distintos de los parámetros de entrada, se debe proporcionar una propiedad <xref:System.Data.ParameterDirection> . En la tabla siguiente se muestran los valores de `ParameterDirection` que se pueden usar con la enumeración <xref:System.Data.ParameterDirection> .  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|<xref:System.Data.ParameterDirection.Input>|Se trata de un parámetro de entrada. Este es el valor predeterminado.|  
|<xref:System.Data.ParameterDirection.InputOutput>|El parámetro se puede comportar tanto de entrada como de salida.|  
|<xref:System.Data.ParameterDirection.Output>|Se trata de un parámetro de salida.|  
|<xref:System.Data.ParameterDirection.ReturnValue>|El parámetro representa un valor devuelto de una operación como, por ejemplo, un procedimiento almacenado, una función integrada o una función definida por el usuario.|  
  
## <a name="working-with-parameter-placeholders"></a>Trabajar con marcadores de posición de parámetros  
 La sintaxis de los marcadores de posición de parámetros depende del origen de datos. Los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] administran la asignación de nombres y la especificación de parámetros y de marcadores de posición de parámetros de forma diferente. Esta sintaxis se personaliza para un origen de datos específico, como se describe en la tabla siguiente.  
  
|Proveedor de datos|Sintaxis de nomenclatura de parámetros|  
|-------------------|-----------------------------|  
|<xref:System.Data.SqlClient>|Usa parámetros con nombre, con el formato `@`*nombreDeParámetro*.|  
|<xref:System.Data.OleDb>|Usa marcadores de parámetro de posición, indicados por un signo de interrogación (`?`).|  
|<xref:System.Data.Odbc>|Usa marcadores de parámetro de posición, indicados por un signo de interrogación (`?`).|  
|<xref:System.Data.OracleClient>|Usa parámetros con nombre, con el formato `:`*nombreDeParámetro* (o *nombreDeParámetro*).|  
  
## <a name="specifying-parameter-data-types"></a>Especificar tipos de datos de parámetro  
 El tipo de datos de un parámetro es específico del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Al especificar el tipo, el valor de `Parameter` se convierte en el tipo del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] antes de pasar el valor al origen de datos. Si lo desea, puede especificar el tipo de un objeto `Parameter` de forma genérica estableciendo la propiedad `DbType` del objeto `Parameter` en un <xref:System.Data.DbType>determinado.  
  
 El tipo del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de un objeto `Parameter` se deduce del tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] del `Value` del objeto `Parameter` , o del `DbType` del objeto `Parameter` . En la siguiente tabla se muestra el tipo deducido de `Parameter` en función del objeto que se ha pasado como valor `Parameter` o del `DbType`especificado.  
  
|Tipo de .NET Framework|DbType|SqlDbType|OleDbType|OdbcType|OracleType|  
|-------------------------|------------|---------------|---------------|--------------|----------------|  
|<xref:System.Boolean>|Boolean|Bit|Booleano|Bit|Byte|  
|<xref:System.Byte>|Byte|TinyInt|UnsignedTinyInt|TinyInt|Byte|  
|byte[]|Binary|VarBinary`.` esta conversión implícita se producirá un error si la matriz de bytes es mayor que el tamaño máximo de un tipo VarBinary, que es de 8000 bytes. Matrices de bytes mayores de 8.000 bytes, debe establecer explícitamente el <xref:System.Data.SqlDbType>.|VarBinary|Binary|Raw|  
|<xref:System.Char>|``|No se admite la deducción de un tipo <xref:System.Data.SqlDbType> a partir de char.|Char|Char|Byte|  
|<xref:System.DateTime>|DateTime|DateTime|DBTimeStamp|DateTime|DateTime|  
|<xref:System.DateTimeOffset>|DateTimeOffset|DateTimeOffset en SQL Server 2008. La deducción de un elemento <xref:System.Data.SqlDbType> a partir de DateTimeOffset no se admite en versiones de SQL Server anteriores a SQL Server 2008.|||DateTime|  
|<xref:System.Decimal>|Decimal|Decimal|Decimal|Numérica|Número|  
|<xref:System.Double>|Double|Float|Double|Doble|Double|  
|<xref:System.Single>|Single|Real|Single|Real|Float|  
|<xref:System.Guid>|Guid|UniqueIdentifier|Guid|UniqueIdentifier|Raw|  
|<xref:System.Int16 >|Int16|SmallInt|SmallInt|SmallInt|Int16|  
|<xref:System.Int32>|Int32|Valor int.|Valor int.|Valor int.|Int32|  
|<xref:System.Int64>|Int64|BigInt|BigInt|BigInt|Número|  
|<xref:System.Object>|Objeto|Variante|Variante|No se admite la deducción de un tipo OdbcType a partir de Object.|Blob|  
|<xref:System.String>|String|NVarChar. Esta conversión implícita generará un error en el caso de que la cadena tenga un tamaño superior al tamaño máximo de un tipo NVarChar, que es de 4.000 caracteres. En cadenas con más de 4.000 caracteres, establezca de forma explícita el tipo <xref:System.Data.SqlDbType>.|VarWChar|NVarChar|NVarChar|  
|<xref:System.TimeSpan>|Tiempo|Time en SQL Server 2008. La deducción de un elemento <xref:System.Data.SqlDbType> a partir de TimeSpan no se admite en versiones de SQL Server anteriores a SQL Server 2008.|DBTime|Hora|DateTime|  
|<xref:System.UInt16>|UInt16|No se admite la deducción de un tipo <xref:System.Data.SqlDbType> a partir de UInt16.|UnsignedSmallInt|Valor int.|UInt16|  
|<xref:System.UInt32>|UInt32|No se admite la deducción de un tipo <xref:System.Data.SqlDbType> a partir de UInt32.|UnsignedInt|BigInt|UInt32|  
|<xref:System.UInt64>|UInt64|No se admite la deducción de un tipo <xref:System.Data.SqlDbType> a partir de UInt64.|UnsignedBigInt|Numérica|Número|  
||AnsiString|VarChar|VarChar|VarChar|VarChar|  
||AnsiStringFixedLength|Char|Char|Char|Char|  
|``|Moneda|Money|Moneda|No es posible deducir el valor de `OdbcType` a partir de `Currency` .|Número|  
|``|Fecha|Date en SQL Server 2008. La deducción de un elemento <xref:System.Data.SqlDbType> a partir de Date no se admite en versiones de SQL Server anteriores a SQL Server 2008.|DBDate|Fecha|DateTime|  
|``|SByte|No se admite la deducción de un elemento <xref:System.Data.SqlDbType> a partir de SByte.|TinyInt|No se admite la deducción de un tipo `OdbcType` a partir de SByte.|SByte|  
||StringFixedLength|NChar|WChar|NChar|NChar|  
||Hora|Time en SQL Server 2008. La deducción de un elemento <xref:System.Data.SqlDbType> a partir de Time no se admite en versiones de SQL Server anteriores a SQL Server 2008.|DBTime|Hora|DateTime|  
||VarNumeric|No se admite la deducción de un elemento <xref:System.Data.SqlDbType> a partir de VarNumeric.|VarNumeric|No se admite la deducción de un tipo `OdbcType` a partir de VarNumeric.|Número|  
|tipo definido por el usuario (un objeto con <xref:Microsoft.SqlServer.Server.SqlUserDefinedAggregateAttribute>|Object o String según el proveedor (SqlClient siempre devuelve Object, ODBC siempre devuelve String y el proveedor de datos administrados OleDb puede ver ambos)|SqlDbType.Udt si <xref:Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute> está presente; de lo contrario, Variant.|OleDbType.VarWChar (si el valor es NULL); de lo contrario, OleDbType.Variant.|OdbcType.NVarChar|no admitido|  
  
> [!NOTE]
>  Las conversiones de valores de tipo decimal en otros tipos de valor son conversiones de restricción que redondean el valor decimal al valor entero más próximo a cero. Si el resultado de la conversión no puede representarse en el tipo de destino, se produce <xref:System.OverflowException> .  
  
> [!NOTE]
>  Cuando se envía un valor de parámetro null al servidor, debe especificar <xref:System.DBNull>, no `null` (`Nothing` en Visual Basic). El valor nulo en el sistema es un objeto vacío que no tiene ningún valor. Para representar los valores nulos, se usa<xref:System.DBNull> . Para obtener más información sobre valores nulos de base de datos, consulte [Handling Null Values](../../../../docs/framework/data/adonet/sql/handling-null-values.md).  
  
## <a name="deriving-parameter-information"></a>Derivar la información de parámetros  
 Los parámetros también se pueden derivar de un procedimiento almacenado mediante la clase `DbCommandBuilder` . Las clases `SqlCommandBuilder` y `OleDbCommandBuilder` proporcionan un método estático, `DeriveParameters`, que rellena automáticamente la colección de parámetros de un objeto de comando que usa información de parámetros procedente de un procedimiento almacenado. Tenga en cuenta que `DeriveParameters` sobrescribirá toda la información de parámetros existente en el comando.  
  
> [!NOTE]
>  La derivación de información de parámetros afecta al rendimiento, ya que precisa un viaje adicional de ida y vuelta (round trip) al origen de datos para recuperar la información. Si la información de los parámetros se conoce en tiempo de diseño, se puede mejorar el rendimiento de la aplicación si se establecen los parámetros con los valores correspondientes de forma explícita.  
  
 Para obtener más información, consulte [generar comandos con objetos CommandBuilder](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).  
  
## <a name="using-parameters-with-a-sqlcommand-and-a-stored-procedure"></a>Usar parámetros con SqlCommand y con un procedimiento almacenado  
 Los procedimientos almacenados ofrecen numerosas ventajas en el caso de aplicaciones que procesan datos. Mediante el uso de procedimientos almacenados, las operaciones de bases de datos se pueden encapsular en un solo comando, optimizar para lograr el mejor rendimiento, y mejorar con seguridad adicional. Aunque se puede llamar a un procedimiento almacenado pasando el nombre del procedimiento almacenado seguido de argumentos de parámetro como una instrucción SQL, usando la <xref:System.Data.Common.DbCommand.Parameters%2A> colección de la [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] <xref:System.Data.Common.DbCommand> objeto le permite definir más explícitamente almacenado parámetros del procedimiento así como para tener acceso a los parámetros de salida y valores devueltos.  
  
> [!NOTE]
>  Las instrucciones con parámetros se ejecutan en el servidor utilizando `sp_executesql,` ; esto permite volver a utilizar el plan de consultas. Los cursores o las variables locales del lote de `sp_executesql` no son visibles para el lote que llama a `sp_executesql`. Los cambios en el contexto de base de datos solo se mantienen hasta el final de la instrucción `sp_executesql` . Para obtener más información, vea los Libros en pantalla de SQL Server.  
  
 Cuando se usan parámetros con <xref:System.Data.SqlClient.SqlCommand> para ejecutar un procedimiento almacenado de SQL Server, los nombres de los parámetros agregados a la colección <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> deben coincidir con los nombres de los marcadores de parámetro del procedimiento almacenado. El proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para SQL Server no admite el uso del marcador de posición de signo de interrogación de cierre (?) para pasar parámetros a una instrucción SQL o a un procedimiento almacenado. Este proveedor trata los parámetros del procedimiento almacenado como parámetros con nombre y busca marcadores de parámetros coincidentes. Por ejemplo, el procedimiento almacenado `CustOrderHist` se define usando un parámetro denominado `@CustomerID`. Cuando el código ejecuta el procedimiento almacenado, también debe usar un parámetro denominado `@CustomerID`.  
  
```  
CREATE PROCEDURE dbo.CustOrderHist @CustomerID varchar(5)  
```  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo llamar a un procedimiento almacenado de SQL Server en la base de datos de ejemplo `Northwind` . El nombre del procedimiento almacenado es `dbo.SalesByCategory` e incluye un parámetro de entrada denominado `@CategoryName` con el tipo de datos `nvarchar(15)`. El código crea una nueva clase <xref:System.Data.SqlClient.SqlConnection> dentro de un bloque en uso, de forma que la conexión se cierre cuando finalice el procedimiento. Se crean los objetos <xref:System.Data.SqlClient.SqlCommand> y <xref:System.Data.SqlClient.SqlParameter> , y se establecen sus propiedades. <xref:System.Data.SqlClient.SqlDataReader> ejecuta `SqlCommand` y devuelve el conjunto de resultados del procedimiento almacenado, mostrándolos en la ventana de consola.  
  
> [!NOTE]
>  En lugar de crear objetos `SqlCommand` y `SqlParameter` y, a continuación, establecer propiedades en instrucciones independientes, puede usar uno de los constructores sobrecargados para establecer varias propiedades en una única instrucción.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
## <a name="using-parameters-with-an-oledbcommand-or-odbccommand"></a>Utilizar parámetros con OleDbCommand o con OdbcCommand  
 Cuando se usan parámetros con <xref:System.Data.OleDb.OleDbCommand> o con <xref:System.Data.Odbc.OdbcCommand>, el orden de los parámetros agregados a la colección `Parameters` debe coincidir con el de los parámetros definidos en el procedimiento almacenado. El proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para OLE DB y el proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ODBC consideran los parámetros de un procedimiento almacenado como marcadores de posición y aplican los valores de los parámetros en orden. Además, los parámetros de valores devueltos deben ser los primeros que se agreguen a la colección `Parameters` .  
  
 El proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para OLE DB y el proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ODBC no admiten el uso de parámetros con nombre para pasar parámetros a una instrucción SQL o a un procedimiento almacenado. En este caso, se debe utilizar el marcador de posición de signo interrogación de cierre (?), como se muestra en el ejemplo siguiente.  
  
```  
SELECT * FROM Customers WHERE CustomerID = ?  
```  
  
 Por eso, el orden en que se agregan los objetos `Parameter` a la colección `Parameters` debe coincidir exactamente con la posición del marcador de posición de interrogación de cierre correspondiente al parámetro.  
  
### <a name="oledb-example"></a>Ejemplo de OleDb  
  
```vb  
Dim command As OleDbCommand = New OleDbCommand( _  
  "SampleProc", connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As OleDbParameter = command.Parameters.Add( _  
  "RETURN_VALUE", OleDbType.Integer)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OleDbType.VarChar, 12)  
parameter.Value = "Sample Value"  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OleDbType.VarChar, 28)  
parameter.Direction = ParameterDirection.Output  
```  
  
```csharp  
OleDbCommand command = new OleDbCommand("SampleProc", connection);  
command.CommandType = CommandType.StoredProcedure;  
  
OleDbParameter parameter = command.Parameters.Add(  
  "RETURN_VALUE", OleDbType.Integer);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@InputParm", OleDbType.VarChar, 12);  
parameter.Value = "Sample Value";  
  
parameter = command.Parameters.Add(  
  "@OutputParm", OleDbType.VarChar, 28);  
parameter.Direction = ParameterDirection.Output;  
```  
  
## <a name="odbc-example"></a>Ejemplo de Odbc  
  
```vb  
Dim command As OdbcCommand = New OdbcCommand( _  
  "{ ? = CALL SampleProc(?, ?) }", connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As OdbcParameter = command.Parameters.Add("RETURN_VALUE", OdbcType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OdbcType.VarChar, 12)  
parameter.Value = "Sample Value"  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OdbcType.VarChar, 28)  
parameter.Direction = ParameterDirection.Output  
```  
  
```csharp  
OdbcCommand command = new OdbcCommand( _  
  "{ ? = CALL SampleProc(?, ?) }", connection);  
command.CommandType = CommandType.StoredProcedure;  
  
OdbcParameter parameter = command.Parameters.Add( _  
  "RETURN_VALUE", OdbcType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OdbcType.VarChar, 12);  
parameter.Value = "Sample Value";  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OdbcType.VarChar, 28);  
parameter.Direction = ParameterDirection.Output;  
```  
  
## <a name="see-also"></a>Vea también  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Parámetros de DataAdapter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [Asignaciones de tipos de datos en ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
