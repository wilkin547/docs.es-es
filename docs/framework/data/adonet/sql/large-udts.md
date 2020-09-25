---
title: UDT grandes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 032093244f51893cd3b0cf50ad81c79413aaa32e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194549"
---
# <a name="large-udts"></a><span data-ttu-id="56214-102">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="56214-102">Large UDTs</span></span>

<span data-ttu-id="56214-103">Los tipos definidos por el usuario (UDT) permiten a los desarrolladores extender el sistema de tipo escalar del servidor mediante el almacenamiento de objetos de Common Language Runtime (CLR) en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56214-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="56214-104">Los UDT pueden contener varios elementos y tener comportamientos, a diferencia de los tipos de datos de alias tradicionales, que se componen de un solo tipo de datos de sistema de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56214-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56214-105">Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="56214-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="56214-106">Anteriormente, los UDT estaban restringidos a un tamaño máximo de 8 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="56214-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="56214-107">En SQL Server 2008, esta restricción se ha eliminado en los UDT con un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="56214-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="56214-108">Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.</span><span class="sxs-lookup"><span data-stu-id="56214-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="56214-109">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="56214-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="56214-110">Tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="56214-110">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="56214-111">Recuperar los esquemas UDT mediante GetSchema</span><span class="sxs-lookup"><span data-stu-id="56214-111">Retrieving UDT Schemas Using GetSchema</span></span>  

 <span data-ttu-id="56214-112">El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve información del esquema de la base de datos en un parámetro <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="56214-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="56214-113">Para obtener más información, vea [SQL Server colecciones de esquemas](../sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="56214-113">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="56214-114">Valores de columna de GetSchemaTable para los UDT</span><span class="sxs-lookup"><span data-stu-id="56214-114">GetSchemaTable Column Values for UDTs</span></span>  

 <span data-ttu-id="56214-115">El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve un valor <xref:System.Data.DataTable> que describe los metadatos de la columna.</span><span class="sxs-lookup"><span data-stu-id="56214-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="56214-116">En la tabla siguiente se describen las diferencias en los metadatos de columna para los UDT de gran tamaño entre SQL Server 2005 y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="56214-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="56214-117">Columna SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="56214-117">SqlDataReader column</span></span>|<span data-ttu-id="56214-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="56214-118">SQL Server 2005</span></span>|<span data-ttu-id="56214-119">SQL Server 2008 y posterior</span><span class="sxs-lookup"><span data-stu-id="56214-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="56214-120">Varía</span><span class="sxs-lookup"><span data-stu-id="56214-120">Varies</span></span>|<span data-ttu-id="56214-121">Varía</span><span class="sxs-lookup"><span data-stu-id="56214-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="56214-122">255</span><span class="sxs-lookup"><span data-stu-id="56214-122">255</span></span>|<span data-ttu-id="56214-123">255</span><span class="sxs-lookup"><span data-stu-id="56214-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="56214-124">255</span><span class="sxs-lookup"><span data-stu-id="56214-124">255</span></span>|<span data-ttu-id="56214-125">255</span><span class="sxs-lookup"><span data-stu-id="56214-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="56214-126">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="56214-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="56214-127">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="56214-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="56214-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="56214-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="56214-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="56214-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="56214-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="56214-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="56214-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="56214-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="56214-132">Nombre de tres partes especificado como *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="56214-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="56214-133">Varía</span><span class="sxs-lookup"><span data-stu-id="56214-133">Varies</span></span>|<span data-ttu-id="56214-134">Varía</span><span class="sxs-lookup"><span data-stu-id="56214-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="56214-135">Consideraciones de SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="56214-135">SqlDataReader Considerations</span></span>  

 <span data-ttu-id="56214-136"><xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="56214-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="56214-137">La forma en que se procesan los valores UDT de gran tamaño mediante <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que esté utilizando, así como del valor `Type System Version` especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="56214-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="56214-138">Para obtener más información, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="56214-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="56214-139">Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="56214-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="56214-140">Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="56214-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="56214-141">Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="56214-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="56214-142">Especificación de SqlParameters</span><span class="sxs-lookup"><span data-stu-id="56214-142">Specifying SqlParameters</span></span>  

 <span data-ttu-id="56214-143">Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="56214-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="56214-144">Propiedades de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="56214-144">SqlParameter Property</span></span>|<span data-ttu-id="56214-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="56214-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="56214-146">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="56214-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="56214-147">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="56214-147">The default is null.</span></span> <span data-ttu-id="56214-148">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="56214-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="56214-149">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="56214-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="56214-150">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="56214-150">The default is null.</span></span> <span data-ttu-id="56214-151">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="56214-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="56214-152">Obtiene o establece el tamaño del valor del parámetro que se va a resolver.</span><span class="sxs-lookup"><span data-stu-id="56214-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="56214-153">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="56214-153">The default value is 0.</span></span> <span data-ttu-id="56214-154">La propiedad puede ser un entero que represente el tamaño del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="56214-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="56214-155">En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.</span><span class="sxs-lookup"><span data-stu-id="56214-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="56214-156">Ejemplo de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="56214-156">Retrieving Data Example</span></span>  

 <span data-ttu-id="56214-157">El fragmento de código siguiente muestra cómo se recuperan datos de UDT de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="56214-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="56214-158">La variable `connectionString` asume la existencia de una conexión válida a una base de datos de SQL Server, y la variable `commandString` asume la existencia de una instrucción SELECT válida con la columna de clave principal que aparece en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="56214-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56214-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56214-159">See also</span></span>

- [<span data-ttu-id="56214-160">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="56214-160">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="56214-161">Recuperar información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="56214-161">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="56214-162">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="56214-162">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="56214-163">SQL Server datos binarios y de valores grandes</span><span class="sxs-lookup"><span data-stu-id="56214-163">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="56214-164">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="56214-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
