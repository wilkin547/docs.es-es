---
description: 'Más información sobre: UDT grandes'
title: UDT grandes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: e1a40330bb48d6320dc96533e764f1b856e0f410
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663188"
---
# <a name="large-udts"></a>UDT grandes

Los tipos definidos por el usuario (UDT) permiten a los desarrolladores extender el sistema de tipo escalar del servidor mediante el almacenamiento de objetos de Common Language Runtime (CLR) en una base de datos de SQL Server. Los UDT pueden contener varios elementos y tener comportamientos, a diferencia de los tipos de datos de alias tradicionales, que se componen de un solo tipo de datos de sistema de SQL Server.  
  
> [!NOTE]
> Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.  
  
 Anteriormente, los UDT estaban restringidos a un tamaño máximo de 8 kilobytes. En SQL Server 2008, esta restricción se ha eliminado en los UDT con un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.  
  
 Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.  
  
 **Documentación de SQL Server**  
  
1. [Tipos CLR definidos por el usuario](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Recuperar los esquemas UDT mediante GetSchema  

 El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve información del esquema de la base de datos en un parámetro <xref:System.Data.DataTable>. Para obtener más información, vea [SQL Server colecciones de esquemas](../sql-server-schema-collections.md).  
  
### <a name="getschematable-column-values-for-udts"></a>Valores de columna de GetSchemaTable para los UDT  

 El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve un valor <xref:System.Data.DataTable> que describe los metadatos de la columna. En la tabla siguiente se describen las diferencias en los metadatos de columna para los UDT de gran tamaño entre SQL Server 2005 y SQL Server 2008.  
  
|Columna SqlDataReader|SQL Server 2005|SQL Server 2008 y versiones posteriores|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Varía|Varía|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|Instancia de UDT|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|Instancia de UDT|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Nombre de tres partes especificado como *Database.SchemaName.TypeName*.|  
|`IsLong`|Varía|Varía|  
  
## <a name="sqldatareader-considerations"></a>Consideraciones de SqlDataReader  

 <xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes. La forma en que se procesan los valores UDT de gran tamaño mediante <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que esté utilizando, así como del valor `Type System Version` especificado en la cadena de conexión. Para obtener más información, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.  
  
## <a name="specifying-sqlparameters"></a>Especificación de SqlParameters  

 Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT de gran tamaño.  
  
|Propiedades de SqlParameter|Descripción|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Obtiene o establece un objeto que representa el valor del parámetro. El valor predeterminado es null. La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Obtiene o establece un objeto que representa el valor del parámetro. El valor predeterminado es null. La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Obtiene o establece el tamaño del valor del parámetro que se va a resolver. El valor predeterminado es 0. La propiedad puede ser un entero que represente el tamaño del valor del parámetro. En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.|  
  
## <a name="retrieving-data-example"></a>Ejemplo de recuperación de datos  

 El fragmento de código siguiente muestra cómo se recuperan datos de UDT de gran tamaño. La variable `connectionString` asume la existencia de una conexión válida a una base de datos de SQL Server, y la variable `commandString` asume la existencia de una instrucción SELECT válida con la columna de clave principal que aparece en primer lugar.  
  
```csharp  
using (SqlConnection connection = new SqlConnection(
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a>Vea también

- [Configurar parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Recuperación de la información del esquema de la base de datos](../retrieving-database-schema-information.md)
- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Datos binarios y datos de valores grandes de SQL Server](sql-server-binary-and-large-value-data.md)
- [Información general de ADO.NET](../ado-net-overview.md)
