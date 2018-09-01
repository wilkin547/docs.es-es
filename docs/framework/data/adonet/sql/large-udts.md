---
title: UDT grandes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: a57bf400288c11e5ba651515feba42437b93148f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389580"
---
# <a name="large-udts"></a><span data-ttu-id="3a37e-102">UDT grandes</span><span class="sxs-lookup"><span data-stu-id="3a37e-102">Large UDTs</span></span>
<span data-ttu-id="3a37e-103">Los tipos definidos por el usuario (UDT) permiten que el desarrollador amplíe el sistema de tipos escalares del servidor mediante el almacenamiento de objetos Common Language Runtime (CLR) en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3a37e-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="3a37e-104">Los UDT pueden contener varios elementos y presentar diversos comportamientos, a diferencia de los tipos de datos de alias tradicionales, que constan de un solo tipo de datos del sistema SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3a37e-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a37e-105">Debe instalar .NET Framework 3.5 SP1 (o posterior) para aprovechar la compatibilidad de SqlClient mejorada para UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="3a37e-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="3a37e-106">Anteriormente, los UDT tenían un tamaño máximo de 8 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="3a37e-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="3a37e-107">En SQL Server 2008, se ha quitado esta restricción para los UDT que tiene un formato de <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="3a37e-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="3a37e-108">Para obtener la documentación completa de los UDT, vea la versión de los Libros en pantalla de SQL Server de la versión de SQL Server que use.</span><span class="sxs-lookup"><span data-stu-id="3a37e-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="3a37e-109">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3a37e-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="3a37e-110">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="3a37e-110">CLR User-Defined Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="3a37e-111">Recuperar los esquemas UDT mediante GetSchema</span><span class="sxs-lookup"><span data-stu-id="3a37e-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="3a37e-112">El método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> de <xref:System.Data.SqlClient.SqlConnection> devuelve la información de un esquema de base de datos de un elemento <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="3a37e-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="3a37e-113">Para obtener más información, consulte [colecciones de esquemas de SQL Server](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="3a37e-113">For more information, see [SQL Server Schema Collections](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="3a37e-114">Valores de columna de GetSchemaTable para los UDT</span><span class="sxs-lookup"><span data-stu-id="3a37e-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="3a37e-115">El método <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve <xref:System.Data.DataTable> que describe los metadatos de columna.</span><span class="sxs-lookup"><span data-stu-id="3a37e-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="3a37e-116">La siguiente tabla describe las diferencias de los metadatos de columna para UDT grandes entre SQL Server 2005 y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3a37e-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="3a37e-117">Columna SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="3a37e-117">SqlDataReader column</span></span>|<span data-ttu-id="3a37e-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="3a37e-118">SQL Server 2005</span></span>|<span data-ttu-id="3a37e-119">SQL Server 2008 y posteriores</span><span class="sxs-lookup"><span data-stu-id="3a37e-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="3a37e-120">Varía</span><span class="sxs-lookup"><span data-stu-id="3a37e-120">Varies</span></span>|<span data-ttu-id="3a37e-121">Varía</span><span class="sxs-lookup"><span data-stu-id="3a37e-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="3a37e-122">255</span><span class="sxs-lookup"><span data-stu-id="3a37e-122">255</span></span>|<span data-ttu-id="3a37e-123">255</span><span class="sxs-lookup"><span data-stu-id="3a37e-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="3a37e-124">255</span><span class="sxs-lookup"><span data-stu-id="3a37e-124">255</span></span>|<span data-ttu-id="3a37e-125">255</span><span class="sxs-lookup"><span data-stu-id="3a37e-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="3a37e-126">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="3a37e-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="3a37e-127">Instancia de UDT</span><span class="sxs-lookup"><span data-stu-id="3a37e-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="3a37e-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="3a37e-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="3a37e-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="3a37e-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="3a37e-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="3a37e-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="3a37e-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="3a37e-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="3a37e-132">Especificado como el nombre de tres partes *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="3a37e-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="3a37e-133">Varía</span><span class="sxs-lookup"><span data-stu-id="3a37e-133">Varies</span></span>|<span data-ttu-id="3a37e-134">Varía</span><span class="sxs-lookup"><span data-stu-id="3a37e-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="3a37e-135">Consideraciones de SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="3a37e-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="3a37e-136"><xref:System.Data.SqlClient.SqlDataReader> se ha ampliado a partir de SQL Server 2008 para admitir la recuperación de valores UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="3a37e-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="3a37e-137">El procesamiento de los valores UDT grandes por parte de <xref:System.Data.SqlClient.SqlDataReader> depende de la versión de SQL Server que use, así como de la `Type System Version` especificada en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="3a37e-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="3a37e-138">Para obtener más información, consulta <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a37e-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="3a37e-139">Los siguientes métodos de <xref:System.Data.SqlClient.SqlDataReader> devolverán <xref:System.Data.SqlTypes.SqlBinary> en lugar de un UDT cuando `Type System Version` se establezca en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="3a37e-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="3a37e-140">Los siguientes métodos devolverán una matriz de `Byte[]` en lugar de un UDT cuando el `Type System Version` esté establecido en SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="3a37e-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="3a37e-141">Tenga en cuenta que no se realiza ninguna conversión para la versión actual de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="3a37e-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="3a37e-142">Especificar SqlParameters</span><span class="sxs-lookup"><span data-stu-id="3a37e-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="3a37e-143">Las siguientes propiedades de <xref:System.Data.SqlClient.SqlParameter> se han ampliado para trabajar con UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="3a37e-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="3a37e-144">Propiedad de SqlParameter</span><span class="sxs-lookup"><span data-stu-id="3a37e-144">SqlParameter Property</span></span>|<span data-ttu-id="3a37e-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a37e-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="3a37e-146">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3a37e-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="3a37e-147">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="3a37e-147">The default is null.</span></span> <span data-ttu-id="3a37e-148">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="3a37e-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="3a37e-149">Obtiene o establece un objeto que representa el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3a37e-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="3a37e-150">El valor predeterminado es null.</span><span class="sxs-lookup"><span data-stu-id="3a37e-150">The default is null.</span></span> <span data-ttu-id="3a37e-151">La propiedad puede ser `SqlBinary`, `Byte[]` o un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="3a37e-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="3a37e-152">Obtiene o establece el tamaño del valor del parámetro que se va a resolver.</span><span class="sxs-lookup"><span data-stu-id="3a37e-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="3a37e-153">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="3a37e-153">The default value is 0.</span></span> <span data-ttu-id="3a37e-154">La propiedad puede ser un entero que representa el tamaño del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3a37e-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="3a37e-155">En UDT grandes, puede ser el tamaño real del UDT o -1 si no se conoce.</span><span class="sxs-lookup"><span data-stu-id="3a37e-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="3a37e-156">Ejemplo de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="3a37e-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="3a37e-157">El fragmento de código siguiente muestra cómo se recuperan datos UDT grandes.</span><span class="sxs-lookup"><span data-stu-id="3a37e-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="3a37e-158">La variable `connectionString` asume una conexión válida con una base de datos de SQL Server y la variable `commandString`, una instrucción SELECT válida con la columna de clave principal en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="3a37e-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3a37e-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a37e-159">See Also</span></span>  
 [<span data-ttu-id="3a37e-160">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="3a37e-160">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="3a37e-161">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="3a37e-161">Retrieving Database Schema Information</span></span>](../../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="3a37e-162">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a37e-162">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="3a37e-163">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a37e-163">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="3a37e-164">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="3a37e-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
