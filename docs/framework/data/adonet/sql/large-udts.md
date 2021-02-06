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
# <a name="large-udts"></a><span data-ttu-id="a66f2-103">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="a66f2-103">Large UDTs</span></span>

<span data-ttu-id="a66f2-104">Los tipos definidos por el usuario (UDT) permiten a los desarrolladores extender el sistema de tipo escalar del servidor mediante el almacenamiento de objetos de Common Language Runtime (CLR) en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a66f2-104">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="a66f2-105">Los UDT pueden contener varios elementos y tener comportamientos, a diferencia de los tipos de datos de alias tradicionales, que se componen de un solo tipo de datos de sistema de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a66f2-105">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a66f2-106">Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="a66f2-106">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="a66f2-107">Anteriormente, los UDT estaban restringidos a un tamaño máximo de 8 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="a66f2-107">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="a66f2-108">En SQL Server 2008, esta restricción se ha eliminado en los UDT con un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="a66f2-108">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="a66f2-109">Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.</span><span class="sxs-lookup"><span data-stu-id="a66f2-109">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="a66f2-110">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a66f2-110">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="a66f2-111">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="a66f2-111">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="a66f2-112">Recuperar los esquemas UDT mediante GetSchema</span><span class="sxs-lookup"><span data-stu-id="a66f2-112">Retrieving UDT Schemas Using GetSchema</span></span>  

 <span data-ttu-id="a66f2-113">El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve información del esquema de la base de datos en un parámetro <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="a66f2-113">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a66f2-114">Para obtener más información, vea [SQL Server colecciones de esquemas](../sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a66f2-114">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="a66f2-115">Valores de columna de GetSchemaTable para los UDT</span><span class="sxs-lookup"><span data-stu-id="a66f2-115">GetSchemaTable Column Values for UDTs</span></span>  

 <span data-ttu-id="a66f2-116">El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve un valor <xref:System.Data.DataTable> que describe los metadatos de la columna.</span><span class="sxs-lookup"><span data-stu-id="a66f2-116">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="a66f2-117">En la tabla siguiente se describen las diferencias en los metadatos de columna para los UDT de gran tamaño entre SQL Server 2005 y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a66f2-117">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="a66f2-118">Columna SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="a66f2-118">SqlDataReader column</span></span>|<span data-ttu-id="a66f2-119">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="a66f2-119">SQL Server 2005</span></span>|<span data-ttu-id="a66f2-120">SQL Server 2008 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a66f2-120">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="a66f2-121">Varía</span><span class="sxs-lookup"><span data-stu-id="a66f2-121">Varies</span></span>|<span data-ttu-id="a66f2-122">Varía</span><span class="sxs-lookup"><span data-stu-id="a66f2-122">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="a66f2-123">255</span><span class="sxs-lookup"><span data-stu-id="a66f2-123">255</span></span>|<span data-ttu-id="a66f2-124">255</span><span class="sxs-lookup"><span data-stu-id="a66f2-124">255</span></span>|  
|`NumericScale`|<span data-ttu-id="a66f2-125">255</span><span class="sxs-lookup"><span data-stu-id="a66f2-125">255</span></span>|<span data-ttu-id="a66f2-126">255</span><span class="sxs-lookup"><span data-stu-id="a66f2-126">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="a66f2-127">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="a66f2-127">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="a66f2-128">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="a66f2-128">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="a66f2-129">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="a66f2-129">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="a66f2-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="a66f2-130">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="a66f2-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="a66f2-131">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="a66f2-132">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="a66f2-132">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="a66f2-133">Nombre de tres partes especificado como *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="a66f2-133">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="a66f2-134">Varía</span><span class="sxs-lookup"><span data-stu-id="a66f2-134">Varies</span></span>|<span data-ttu-id="a66f2-135">Varía</span><span class="sxs-lookup"><span data-stu-id="a66f2-135">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="a66f2-136">Consideraciones de SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="a66f2-136">SqlDataReader Considerations</span></span>  

 <span data-ttu-id="a66f2-137"><xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="a66f2-137">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="a66f2-138">La forma en que se procesan los valores UDT de gran tamaño mediante <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que esté utilizando, así como del valor `Type System Version` especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="a66f2-138">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="a66f2-139">Para obtener más información, vea <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="a66f2-139">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="a66f2-140">Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="a66f2-140">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="a66f2-141">Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="a66f2-141">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="a66f2-142">Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a66f2-142">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="a66f2-143">Especificación de SqlParameters</span><span class="sxs-lookup"><span data-stu-id="a66f2-143">Specifying SqlParameters</span></span>  

 <span data-ttu-id="a66f2-144">Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a66f2-144">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="a66f2-145">Propiedades de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="a66f2-145">SqlParameter Property</span></span>|<span data-ttu-id="a66f2-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="a66f2-146">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="a66f2-147">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="a66f2-147">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="a66f2-148">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="a66f2-148">The default is null.</span></span> <span data-ttu-id="a66f2-149">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="a66f2-149">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="a66f2-150">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="a66f2-150">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="a66f2-151">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="a66f2-151">The default is null.</span></span> <span data-ttu-id="a66f2-152">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="a66f2-152">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="a66f2-153">Obtiene o establece el tamaño del valor del parámetro que se va a resolver.</span><span class="sxs-lookup"><span data-stu-id="a66f2-153">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="a66f2-154">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="a66f2-154">The default value is 0.</span></span> <span data-ttu-id="a66f2-155">La propiedad puede ser un entero que represente el tamaño del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="a66f2-155">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="a66f2-156">En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.</span><span class="sxs-lookup"><span data-stu-id="a66f2-156">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="a66f2-157">Ejemplo de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="a66f2-157">Retrieving Data Example</span></span>  

 <span data-ttu-id="a66f2-158">El fragmento de código siguiente muestra cómo se recuperan datos de UDT de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a66f2-158">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="a66f2-159">La variable `connectionString` asume la existencia de una conexión válida a una base de datos de SQL Server, y la variable `commandString` asume la existencia de una instrucción SELECT válida con la columna de clave principal que aparece en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a66f2-159">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a66f2-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="a66f2-160">See also</span></span>

- [<span data-ttu-id="a66f2-161">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="a66f2-161">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="a66f2-162">Recuperación de la información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a66f2-162">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="a66f2-163">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a66f2-163">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="a66f2-164">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a66f2-164">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="a66f2-165">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a66f2-165">ADO.NET Overview</span></span>](../ado-net-overview.md)
