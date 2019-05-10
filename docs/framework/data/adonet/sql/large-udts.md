---
title: UDT grandes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 2114efcc4d39cb4d2ea9ca33d7ff244c81a7097f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650580"
---
# <a name="large-udts"></a>UDT grandes
Los tipos definidos por el usuario (UDT) permiten que el desarrollador amplíe el sistema de tipos escalares del servidor mediante el almacenamiento de objetos Common Language Runtime (CLR) en una base de datos de SQL Server. Los UDT pueden contener varios elementos y presentar diversos comportamientos, a diferencia de los tipos de datos de alias tradicionales, que constan de un solo tipo de datos del sistema SQL Server.  
  
> [!NOTE]
>  Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.  
  
 Anteriormente, los UDT tenían un tamaño máximo de 8 kilobytes. En SQL Server 2008, se ha quitado esta restricción para los UDT que tiene un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.  
  
 Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.  
  
 **Libros en pantalla de SQL Server**  
  
1. [Tipos CLR definidos por el usuario](https://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Recuperar los esquemas UDT mediante GetSchema  
 El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve la información de un esquema de base de datos de un elemento <xref:System.Data.DataTable>. Para obtener más información, consulte [colecciones de esquemas de SQL Server](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).  
  
### <a name="getschematable-column-values-for-udts"></a>Valores de columna de GetSchemaTable para los UDT  
 El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve <xref:System.Data.DataTable> que describe los metadatos de columna. La siguiente tabla describe las diferencias de los metadatos de columna para UDT grandes entre SQL Server 2005 y SQL Server 2008.  
  
|Columna SqlDataReader|SQL Server 2005|SQL Server 2008 y posteriores|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Varía|Varía|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|Instancia de UDT|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|Instancia de UDT|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Especificado como el nombre de tres partes *Database.SchemaName.TypeName*.|  
|`IsLong`|Varía|Varía|  
  
## <a name="sqldatareader-considerations"></a>Consideraciones de SqlDataReader  
 <xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes. El procesamiento de los valores UDT grandes por parte de <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que use, así como de la `Type System Version` especificada en la cadena de conexión. Para obtener más información, consulta <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando el `Type System Version` esté establecido en SQL Server 2005:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.  
  
## <a name="specifying-sqlparameters"></a>Especificar SqlParameters  
 Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT grandes.  
  
|Propiedad de SqlParameter|Descripción|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Obtiene o establece un objeto que representa el valor del parámetro. El valor predeterminado es null. La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Obtiene o establece un objeto que representa el valor del parámetro. El valor predeterminado es null. La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Obtiene o establece el tamaño del valor del parámetro que se va a resolver. El valor predeterminado es 0. La propiedad puede ser un entero que representa el tamaño del valor del parámetro. En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.|  
  
## <a name="retrieving-data-example"></a>Ejemplo de recuperación de datos  
 El fragmento de código siguiente muestra cómo se recuperan datos UDT grandes. La variable `connectionString` asume una conexión válida con una base de datos de SQL Server y la variable `commandString`, una instrucción SELECT válida con la columna de clave principal en primer lugar.  
  
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

- [Configuración de parámetros y tipos de datos de parámetros](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Recuperación de información del esquema de la base de datos](../../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Asignaciones de tipos de datos de SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [Datos binarios y datos de valores grandes de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
