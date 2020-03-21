---
title: Generar comandos con objetos CommandBuilder
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
ms.openlocfilehash: 76c2a6cb0661a0e39fc3a0dd599fcbb3c046f382
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149617"
---
# <a name="generating-commands-with-commandbuilders"></a>Generar comandos con objetos CommandBuilder
Cuando la propiedad `SelectCommand` se especifica de forma dinámica en tiempo de ejecución, por ejemplo a través de una herramienta de consulta que acepta un comando de texto del usuario, existe la posibilidad de que no se pueda especificar adecuadamente en tiempo de diseño el comando `InsertCommand`, `UpdateCommand` o `DeleteCommand` correspondiente. Si el objeto <xref:System.Data.DataTable> se asigna a una única tabla de base de datos o se genera a partir de ella, puede utilizar el objeto <xref:System.Data.Common.DbCommandBuilder> para generar automáticamente las propiedades `DeleteCommand`, `InsertCommand` y `UpdateCommand` de <xref:System.Data.Common.DbDataAdapter>.  
  
 El requisito mínimo para que la generación automática de comandos funcione correctamente consiste en establecer la propiedad `SelectCommand`. El esquema de tabla que recupera la propiedad `SelectCommand` determina la sintaxis de las instrucciones INSERT, UPDATE y DELETE generadas automáticamente.  
  
 <xref:System.Data.Common.DbCommandBuilder> debe ejecutar `SelectCommand` con el objeto de devolver los metadatos necesarios para construir los comandos SQL INSERT, UPDATE y DELETE. Por eso es necesario realizar un viaje adicional al origen de datos, con el consiguiente efecto adverso en el rendimiento. Para mejorar el rendimiento, debe especificar los comandos de forma explícita, en lugar de utilizar <xref:System.Data.Common.DbCommandBuilder>.  
  
 `SelectCommand` también debe devolver como mínimo una clave principal o una columna única. Si no hay ninguna, se genera una excepción `InvalidOperation` y no se genera ningún comando.  
  
 Cuando se asocia con un objeto `DataAdapter`, <xref:System.Data.Common.DbCommandBuilder> genera automáticamente las propiedades `InsertCommand`, `UpdateCommand` y `DeleteCommand` del objeto `DataAdapter` si son referencias nulas. Si ya existe algún objeto `Command` para una propiedad, se utilizará el objeto `Command` existente.  
  
 Las vistas de bases de datos creadas al unir una o varias tablas no se consideran una tabla única de base de datos. En este caso no puede utilizar <xref:System.Data.Common.DbCommandBuilder> para generar comandos automáticamente y deberá especificarlos de manera explícita. Para obtener información sobre cómo establecer `DataSet` explícitamente comandos para resolver actualizaciones de una copia posterior en el origen de datos, vea Actualizar orígenes de [datos con DataAdapters](updating-data-sources-with-dataadapters.md).  
  
 Es posible que desee asignar parámetros de salida a la fila actualizada de un `DataSet`. Una tarea habitual consiste en recuperar, a partir del origen de datos, el valor de un campo de identidad de generación automática o una marca de tiempo. <xref:System.Data.Common.DbCommandBuilder> no asigna de forma predeterminada los parámetros de salida a las columnas de una fila actualizada. En este caso, debe especificar el comando de forma explícita. Para obtener un ejemplo de asignación de un campo de identidad generado automáticamente a una columna de una fila insertada, vea Recuperar valores de [identidad o numeración automática](retrieving-identity-or-autonumber-values.md).  
  
## <a name="rules-for-automatically-generated-commands"></a>Reglas para comandos generados automáticamente  
 En la tabla siguiente se muestran las reglas de la generación automática de comandos.  
  
|Get-Help|Regla|  
|-------------|----------|  
|`InsertCommand`|Inserta una fila en el origen de datos para todas las filas de la tabla con una <xref:System.Data.DataRow.RowState%2A> con el valor <xref:System.Data.DataRowState.Added>. Inserta valores para todas las columnas actualizables, pero no para determinadas columnas como identidades, expresiones o marcas de tiempo.|  
|`UpdateCommand`|Actualiza filas en el origen de datos para todas las filas de la tabla con una propiedad `RowState` con el valor <xref:System.Data.DataRowState.Modified>. Actualiza los valores de todas las columnas, con excepción de las que no son actualizables, como identidades o expresiones. Actualiza todas las filas en las que los valores de columna en el origen de datos coinciden con los valores de la columna de clave principal de la fila, siempre que las restantes columnas del origen de datos coincidan con los valores originales de la fila. Para obtener más información, vea la sección "Modelo de simultaneidad optimista para actualizaciones y eliminaciones" de este mismo tema.|  
|`DeleteCommand`|Elimina filas en el origen de datos para todas las filas de la tabla con una propiedad `RowState` con el valor <xref:System.Data.DataRowState.Deleted>. Elimina todas las filas en las que los valores de columna coinciden con los valores de la columna de clave principal de la fila, siempre que las restantes columnas del origen de datos coincidan con los valores originales de la fila. Para obtener más información, vea la sección "Modelo de simultaneidad optimista para actualizaciones y eliminaciones" de este mismo tema.|  
  
## <a name="optimistic-concurrency-model-for-updates-and-deletes"></a>Modelo de simultaneidad optimista para actualizaciones y eliminaciones  
 La lógica para generar comandos automáticamente para las instrucciones UPDATE y DELETE se basa en la *simultaneidad optimista,* es decir, los registros no están bloqueados para su edición y pueden ser modificados por otros usuarios o procesos en cualquier momento. Dado que existe la posibilidad de que un registro haya sido modificado después de que haya sido devuelto por la instrucción SELECT y antes de que se emita la instrucción UPDATE o DELETE, la instrucción UPDATE o DELETE generada automáticamente incluye una cláusula WHERE que especifica que la fila solo se actualiza cuando contiene todos los valores originales y no ha sido eliminada del origen de datos. Esto evita que se sobrescriban los datos nuevos. Si una actualización generada automáticamente intenta actualizar una fila que ha sido eliminada o que no contiene los valores originales del <xref:System.Data.DataSet>, el comando no tienen ningún efecto en los registros y se inicia una excepción <xref:System.Data.DBConcurrencyException>.  
  
 Si desea que la instrucción UPDATE o DELETE se ejecute sin tener en cuenta los valores originales, debe establecer de forma explícita la propiedad `UpdateCommand` del `DataAdapter` sin utilizar la generación automática de comandos.  
  
## <a name="limitations-of-automatic-command-generation-logic"></a>Limitaciones de la lógica de generación automática de comandos  
 La generación automática de comandos tiene las siguientes limitaciones.  
  
### <a name="unrelated-tables-only"></a>Solo tablas no relacionadas  
 La lógica de generación automática de comandos crea instrucciones INSERT, UPDATE o DELETE para tablas independientes sin tener en cuenta las relaciones que éstas puedan tener con otras tablas en el origen de datos. Por eso, se puede producir un error al llamar a `Update` para realizar cambios en una columna que participa de una restricción de clave externa en la base de datos. Para evitar esa excepción, no utilice <xref:System.Data.Common.DbCommandBuilder> al actualizar las columnas que participan en una restricción de clave externa. En este caso debe especificar de forma explícita las instrucciones que se van a utilizar para llevar a cabo la operación.  
  
### <a name="table-and-column-names"></a>Nombres de tabla y columna  
 La lógica de generación automática de comandos puede ocasionar un error cuando los nombres de las tablas o de las columnas incluyen algún carácter especial, como espacios, puntos, comillas y otros caracteres no alfanuméricos, incluso si están delimitados por corchetes. En función del proveedor, el establecimiento de los parámetros QuotePrefix y QuoteSuffix puede permitir que la lógica de generación procese espacios, pero los caracteres especiales no pueden convertirse en caracteres de escape. Se admiten nombres de tabla completos en forma de *catalog.schema.table.*  
  
## <a name="using-the-commandbuilder-to-automatically-generate-an-sql-statement"></a>Utilizar CommandBuilder para generar automáticamente una instrucción SQL  
 Para generar instrucciones SQL automáticamente para un `DataAdapter`, defina en primer lugar la propiedad `SelectCommand` del `DataAdapter` y, a continuación, cree un objeto `CommandBuilder` y especifique como argumento el `DataAdapter` para el que `CommandBuilder` generará automáticamente las instrucciones SQL.  
  
```vb  
' Assumes that connection is a valid SqlConnection object
' inside of a Using block.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", connection)  
Dim builder As SqlCommandBuilder = New SqlCommandBuilder(adapter)  
builder.QuotePrefix = "["  
builder.QuoteSuffix = "]"  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object  
// inside of a using block.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", connection);  
SqlCommandBuilder builder = new SqlCommandBuilder(adapter);  
builder.QuotePrefix = "[";  
builder.QuoteSuffix = "]";  
```  
  
## <a name="modifying-the-selectcommand"></a>Modificar SelectCommand  
 Es posible que se inicie una excepción si modifica valor `CommandText` de `SelectCommand` después de generar automáticamente los comandos INSERT, UPDATE o DELETE. Si el valor `SelectCommand.CommandText` modificado contiene información del esquema que sea incoherente con el valor `SelectCommand.CommandText` utilizado en el momento de la generación automática de los comandos de inserción, actualización o eliminación, las futuras llamadas al método `DataAdapter.Update` pueden tratar de obtener acceso a columnas que ya no existen en la tabla actual a la que hace referencia `SelectCommand`, con lo que se iniciará una excepción.  
  
 Puede actualizar la información del esquema que utiliza `CommandBuilder` para generar automáticamente los comandos; para ello, basta con llamar al método `RefreshSchema` de `CommandBuilder`.  
  
 Si desea conocer el comando generado automáticamente, puede obtener una referencia a los comandos generados automáticamente mediante los métodos `GetInsertCommand`, `GetUpdateCommand` y `GetDeleteCommand` del objeto `CommandBuilder` y la comprobación de la propiedad `CommandText` del comando asociado.  
  
 En el ejemplo de código siguiente se escribe en la consola el comando de actualización generado automáticamente.  
  
```vb
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```

```csharp
Console.WriteLine(builder.GetUpdateCommand().CommandText);
```
  
 En el siguiente ejemplo se vuelve a crear la tabla `Customers` en el conjunto de datos `custDS`. El **RefreshSchema** se llama al método para actualizar los comandos generados automáticamente con esta nueva información de columna.  
  
```vb  
' Assumes an open SqlConnection and SqlDataAdapter inside of a Using block.  
adapter.SelectCommand.CommandText = _  
  "SELECT CustomerID, ContactName FROM dbo.Customers"  
builder.RefreshSchema()  
  
custDS.Tables.Remove(custDS.Tables("Customers"))  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
// Assumes an open SqlConnection and SqlDataAdapter inside of a using block.  
adapter.SelectCommand.CommandText =
  "SELECT CustomerID, ContactName FROM dbo.Customers";  
builder.RefreshSchema();  
  
custDS.Tables.Remove(custDS.Tables["Customers"]);  
adapter.Fill(custDS, "Customers");  
```  
  
## <a name="see-also"></a>Consulte también

- [Comandos y parámetros](commands-and-parameters.md)
- [Ejecución de un comando](executing-a-command.md)
- [DbConnection, DbCommand y DbException](dbconnection-dbcommand-and-dbexception.md)
- [Información general de ADO.NET](ado-net-overview.md)
