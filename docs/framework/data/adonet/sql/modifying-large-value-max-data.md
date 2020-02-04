---
title: Modificación de datos de valores grandes (Max)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: cb37fdb85d323d4f0816a3667a4624da8ec75e65
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979851"
---
# <a name="modifying-large-value-max-data-in-adonet"></a>Modificar datos de valores grandes (max) en ADO.NET
Los tipos de datos de objeto grande (LOB) son aquellos que superan el tamaño máximo de fila de 8 kilobytes (KB). SQL Server proporciona un especificador `max` para los tipos de datos `varchar`, `nvarchar` y `varbinary` a fin de permitir el almacenamiento de valores tan grandes como 2^32 bytes. Las columnas de tabla y las variables de Transact-SQL pueden especificar tipos de datos `varchar(max)`, `nvarchar(max)` o `varbinary(max)`. En ADO.NET, los tipos de datos `max` se pueden recuperar mediante `DataReader` y también se pueden especificar como valores de parámetros de entrada y salida sin ningún control especial. En el caso de tipos de datos `varchar` grandes, los datos se pueden recuperar y actualizar de manera incremental.  
  
 Los tipos de datos `max` se pueden utilizar para las comparaciones, como variables de Transact-SQL y para la concatenación. También se pueden usar en las cláusulas DISTINCT, ORDER BY, GROUP BY de una instrucción SELECT, así como en agregados, combinaciones y subconsultas.  
  
 La tabla siguiente proporciona vínculos a la documentación de los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1. [Usar tipos de datos de valores grandes](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a>Restricciones de los tipos de valor grande  
 Las siguientes restricciones se aplican a los tipos de datos `max`, que no existen para tipos de datos más pequeños:  
  
- Una `sql_variant` no puede contener un tipo de datos `varchar` grande.  
  
- Las columnas `varchar` grandes no se pueden especificar como columnas de claves en un índice. Se permiten en una columna incluida en un índice no agrupado.  
  
- Las columnas `varchar` grandes no se pueden utilizar como columnas de claves de partición.  
  
## <a name="working-with-large-value-types-in-transact-sql"></a>Trabajar con tipos de valor grande en Transact-SQL  
 La función `OPENROWSET` de Transact-SQL es un método de un solo uso para la conexión y el acceso a datos remotos. Incluye toda la información de conexión necesaria para tener acceso a datos remotos desde un origen de datos OLE DB. Se puede hacer referencia a `OPENROWSET` en la cláusula FROM de una consulta como si fuese un nombre de tabla. y como si fuera la tabla de destino de una instrucción INSERT, UPDATE o DELETE, sujeta a las capacidades del proveedor OLE DB.  
  
 La función `OPENROWSET` incluye el proveedor de conjuntos de filas `BULK`, que permite leer datos directamente de un archivo sin tener que cargarlos en una tabla de destino. Esto permite usar `OPENROWSET` en una instrucción INSERT SELECT simple.  
  
 Los argumentos de la opción `OPENROWSET BULK` proporcionan un control significativo sobre dónde comienza y termina la lectura de datos, cómo tratar los errores y cómo se interpretan los datos. Por ejemplo, puede especificar que el archivo de datos se lea como un conjunto de filas con una única fila y una única columna del tipo `varbinary`, `varchar` o `nvarchar`. Para obtener la sintaxis y las opciones completas, vea los Libros en pantalla de SQL Server.  
  
 En el siguiente ejemplo se inserta una foto en la tabla ProductPhoto de la base de datos de ejemplo AdventureWorks. Al usar el proveedor de `BULK OPENROWSET`, debe proporcionar la lista con nombre de las columnas, incluso si no va a insertar valores en todas las columnas. En este caso, la clave principal se define como una columna de identidad y podría omitirse de la lista de columnas. Tenga en cuenta que también debe suministrar un nombre de correlación al final de la instrucción `OPENROWSET`, que en este caso es ThumbnailPhoto. Éste se correlaciona con la columna de la tabla `ProductPhoto` en la que se carga el archivo.  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a>Actualizar datos mediante UPDATE .WRITE  
 La instrucción UPDATE de Transact-SQL tiene una nueva sintaxis WRITE para la modificación del contenido de las columnas `varchar(max)`, `nvarchar(max)` o `varbinary(max)`. Esto permite realizar actualizaciones parciales de los datos. La sintaxis UPDATE .WRITE se muestra aquí de forma abreviada:  
  
 UPDATE  
  
 { *\<object>* }  
  
 SET  
  
 { *column_name* = {. WRITE ( *expresión* , @Offset, @Length)}  
  
 El método WRITE especifica que se modificará una sección del valor de la *column_name* . La expresión es el valor que se copiará en el *column_name*, el `@Offset` es el punto inicial en el que se escribirá la expresión y el argumento `@Length` es la longitud de la sección en la columna.  
  
|Si|A continuación,|  
|--------|----------|  
|La expresión se establece en NULL|`@Length` se omite y el valor de *column_name* se trunca en el `@Offset`especificado.|  
|`@Offset` es NULL|La operación de actualización anexa la expresión al final del valor de la *column_name* existente y se omite `@Length`.|  
|`@Offset` es mayor que la longitud del valor de column_name|SQL Server devuelve un error.|  
|`@Length` es NULL|La operación de actualización quita todos los datos de `@Offset` hasta el final del valor de `column_name`.|  
  
> [!NOTE]
> Ni `@Offset` ni `@Length` pueden ser un número negativo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo de Transact-SQL se actualiza un valor parcial de DocumentSummary, una columna `nvarchar(max)` de la tabla Document de la base de datos AdventureWorks. La palabra 'components' se sustituye por la palabra 'features' mediante la especificación de la palabra de sustitución, la ubicación de comienzo (desplazamiento) de la palabra que se va a sustituir en los datos existentes y el número de caracteres que se van a sustituir (longitud). El ejemplo incluye instrucciones SELECT antes y después de la instrucción UPDATE para comparar los resultados.  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a>Trabajar con tipos de valor grandes en ADO.NET  
 Puede trabajar con tipos de valor grande en ADO.NET especificando tipos de valores grandes como <xref:System.Data.SqlClient.SqlParameter> objetos en un <xref:System.Data.SqlClient.SqlDataReader> para devolver un conjunto de resultados, o bien mediante un <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar una `DataSet`/`DataTable`. No existe ninguna diferencia entre la forma de trabajar con un tipo de valor grande y su tipo de datos de valor más pequeño relacionado.  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a>Uso de GetSqlBytes para recuperar datos  
 El método `GetSqlBytes` del <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varbinary(max)`. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> llamado `cmd` que selecciona datos `varbinary(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera los datos como <xref:System.Data.SqlTypes.SqlBytes>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a>Uso de GetSqlChars para recuperar datos  
 El método `GetSqlChars` del <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varchar(max)` o `nvarchar(max)`. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> llamado `cmd` que selecciona datos `nvarchar(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera los datos.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a>Uso de GetSqlBinary para recuperar datos  
 El método `GetSqlBinary` de un <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varbinary(max)`. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> llamado `cmd` que selecciona datos `varbinary(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera los datos como una secuencia <xref:System.Data.SqlTypes.SqlBinary>.  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a>Uso de GetBytes para recuperar datos  
 El método `GetBytes` de un <xref:System.Data.SqlClient.SqlDataReader> lee una secuencia de bytes desde el desplazamiento de columna especificado a una matriz de bytes a partir del desplazamiento de matriz especificado. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera bytes en una matriz de bytes. Tenga en cuenta que, a diferencia de `GetSqlBytes`, `GetBytes` necesita un tamaño para el búfer de la matriz.  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a>Uso de GetValue para recuperar datos  
 El método `GetValue` de un <xref:System.Data.SqlClient.SqlDataReader> lee el valor desde el desplazamiento de columna especificado a una matriz. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera datos binarios del primer desplazamiento de columna y, a continuación, datos de cadena del segundo desplazamiento de columna.  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a>Conversión de tipos de valor grandes a tipos CLR  
 Puede convertir el contenido de una columna `varchar(max)` o `nvarchar(max)` mediante cualquiera de los métodos de conversión de cadenas, como `ToString`. El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> llamado `reader` que recupera los datos.  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a>Ejemplo  
 El código siguiente recupera el nombre y el objeto `LargePhoto` de la tabla `ProductPhoto` de la base de datos `AdventureWorks` y lo guarda en un archivo. Es necesario compilar el ensamblado con una referencia al espacio de nombres <xref:System.Drawing>.  El método <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve un objeto <xref:System.Data.SqlTypes.SqlBytes> que expone una propiedad `Stream`. El código usa esto para crear un nuevo objeto `Bitmap` y, a continuación, lo guarda en el `ImageFormat`GIF.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a>Usar parámetros de tipos de valor grande  
 Los tipos de valor grande se pueden emplear en objetos <xref:System.Data.SqlClient.SqlParameter> de la misma manera que se utilizan los tipos de valor más pequeño en objetos <xref:System.Data.SqlClient.SqlParameter>. Puede recuperar tipos de valor grandes como valores <xref:System.Data.SqlClient.SqlParameter>, como se muestra en el ejemplo siguiente. El código asume que el siguiente procedimiento almacenado GetDocumentSummary existe en la base de datos de ejemplo AdventureWorks. El procedimiento almacenado toma un parámetro de entrada denominado @DocumentID y devuelve el contenido de la columna DocumentSummary en el parámetro de salida @DocumentSummary.  
  
```sql
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a>Ejemplo  
 El código de ADO.NET crea objetos <xref:System.Data.SqlClient.SqlConnection> y <xref:System.Data.SqlClient.SqlCommand> para ejecutar el procedimiento almacenado GetDocumentSummary y recuperar el resumen de documento, que se encuentra almacenado como un tipo de valor grande. El código pasa un valor para el parámetro de entrada @DocumentID y muestra los resultados que se devuelven en el parámetro de salida @DocumentSummary de la ventana de la consola.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Datos binarios y datos de valores grandes de SQL Server](sql-server-binary-and-large-value-data.md)
- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Operaciones de datos de SQL Server en ADO.NET](sql-server-data-operations.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
