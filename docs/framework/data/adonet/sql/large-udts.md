---
title: UDT grandes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 012bddc0b4c29a0b50abc3a0df5c3cd34dc4725a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452401"
---
# <a name="large-udts"></a><span data-ttu-id="29cbd-102">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="29cbd-102">Large UDTs</span></span>
<span data-ttu-id="29cbd-103">Los tipos definidos por el usuario (UDT) permiten a los desarrolladores extender el sistema de tipo escalar del servidor mediante el almacenamiento de objetos de Common Language Runtime (CLR) en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="29cbd-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="29cbd-104">Los UDT pueden contener varios elementos y tener comportamientos, a diferencia de los tipos de datos de alias tradicionales, que se componen de un solo tipo de datos de sistema de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="29cbd-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29cbd-105">Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="29cbd-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="29cbd-106">Anteriormente, los UDT estaban restringidos a un tamaño máximo de 8 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="29cbd-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="29cbd-107">En SQL Server 2008, esta restricción se ha eliminado en los UDT con un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="29cbd-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="29cbd-108">Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.</span><span class="sxs-lookup"><span data-stu-id="29cbd-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="29cbd-109">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="29cbd-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="29cbd-110">Tipos definidos por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="29cbd-110">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="29cbd-111">Recuperar los esquemas UDT mediante GetSchema</span><span class="sxs-lookup"><span data-stu-id="29cbd-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="29cbd-112">El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve la información de un esquema de base de datos de un elemento <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="29cbd-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="29cbd-113">Para obtener más información, vea [SQL Server colecciones de esquemas](../sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="29cbd-113">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="29cbd-114">Valores de columna de GetSchemaTable para los UDT</span><span class="sxs-lookup"><span data-stu-id="29cbd-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="29cbd-115">El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve <xref:System.Data.DataTable> que describe los metadatos de columna.</span><span class="sxs-lookup"><span data-stu-id="29cbd-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="29cbd-116">La siguiente tabla describe las diferencias de los metadatos de columna para UDT grandes entre SQL Server 2005 y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="29cbd-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="29cbd-117">Columna SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="29cbd-117">SqlDataReader column</span></span>|<span data-ttu-id="29cbd-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="29cbd-118">SQL Server 2005</span></span>|<span data-ttu-id="29cbd-119">SQL Server 2008 y posterior</span><span class="sxs-lookup"><span data-stu-id="29cbd-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="29cbd-120">Varía</span><span class="sxs-lookup"><span data-stu-id="29cbd-120">Varies</span></span>|<span data-ttu-id="29cbd-121">Varía</span><span class="sxs-lookup"><span data-stu-id="29cbd-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="29cbd-122">255</span><span class="sxs-lookup"><span data-stu-id="29cbd-122">255</span></span>|<span data-ttu-id="29cbd-123">255</span><span class="sxs-lookup"><span data-stu-id="29cbd-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="29cbd-124">255</span><span class="sxs-lookup"><span data-stu-id="29cbd-124">255</span></span>|<span data-ttu-id="29cbd-125">255</span><span class="sxs-lookup"><span data-stu-id="29cbd-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="29cbd-126">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="29cbd-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="29cbd-127">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="29cbd-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="29cbd-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="29cbd-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="29cbd-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="29cbd-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="29cbd-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="29cbd-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="29cbd-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="29cbd-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="29cbd-132">Nombre de tres partes especificado como *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="29cbd-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="29cbd-133">Varía</span><span class="sxs-lookup"><span data-stu-id="29cbd-133">Varies</span></span>|<span data-ttu-id="29cbd-134">Varía</span><span class="sxs-lookup"><span data-stu-id="29cbd-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="29cbd-135">Consideraciones de SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="29cbd-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="29cbd-136"><xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="29cbd-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="29cbd-137">El procesamiento de los valores UDT grandes por parte de <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que use, así como de la `Type System Version` especificada en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="29cbd-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="29cbd-138">Para más información, consulte <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="29cbd-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="29cbd-139">Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="29cbd-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="29cbd-140">Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando el `Type System Version` esté establecido en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="29cbd-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="29cbd-141">Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="29cbd-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="29cbd-142">Especificar SqlParameters</span><span class="sxs-lookup"><span data-stu-id="29cbd-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="29cbd-143">Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="29cbd-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="29cbd-144">Propiedad de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="29cbd-144">SqlParameter Property</span></span>|<span data-ttu-id="29cbd-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="29cbd-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="29cbd-146">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="29cbd-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="29cbd-147">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="29cbd-147">The default is null.</span></span> <span data-ttu-id="29cbd-148">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="29cbd-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="29cbd-149">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="29cbd-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="29cbd-150">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="29cbd-150">The default is null.</span></span> <span data-ttu-id="29cbd-151">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="29cbd-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="29cbd-152">Obtiene o establece el tamaño del valor del parámetro que se va a resolver.</span><span class="sxs-lookup"><span data-stu-id="29cbd-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="29cbd-153">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="29cbd-153">The default value is 0.</span></span> <span data-ttu-id="29cbd-154">La propiedad puede ser un entero que representa el tamaño del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="29cbd-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="29cbd-155">En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.</span><span class="sxs-lookup"><span data-stu-id="29cbd-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="29cbd-156">Ejemplo de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="29cbd-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="29cbd-157">El fragmento de código siguiente muestra cómo se recuperan datos UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="29cbd-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="29cbd-158">La variable `connectionString` asume una conexión válida con una base de datos de SQL Server y la variable `commandString`, una instrucción SELECT válida con la columna de clave principal en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="29cbd-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29cbd-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29cbd-159">See also</span></span>

- [<span data-ttu-id="29cbd-160">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="29cbd-160">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="29cbd-161">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="29cbd-161">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="29cbd-162">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="29cbd-162">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="29cbd-163">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="29cbd-163">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="29cbd-164">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="29cbd-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
