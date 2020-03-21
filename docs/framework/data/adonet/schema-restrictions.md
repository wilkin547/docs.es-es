---
title: Restricciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149016"
---
# <a name="schema-restrictions"></a><span data-ttu-id="e28ac-102">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="e28ac-102">Schema Restrictions</span></span>
<span data-ttu-id="e28ac-103">El segundo parámetro opcional del método **GetSchema** son las restricciones que se usan para limitar la cantidad de información de esquema devuelta y se pasa al método **GetSchema** como una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="e28ac-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="e28ac-104">La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.</span><span class="sxs-lookup"><span data-stu-id="e28ac-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="e28ac-105">Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e28ac-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="e28ac-106">Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="e28ac-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="e28ac-107">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-107">Restriction Name</span></span>|<span data-ttu-id="e28ac-108">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-108">Parameter Name</span></span>|<span data-ttu-id="e28ac-109">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-109">Restriction Default</span></span>|<span data-ttu-id="e28ac-110">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-111">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-111">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-112">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-113">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-113">1</span></span>|  
|<span data-ttu-id="e28ac-114">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-114">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-116">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-116">2</span></span>|  
|<span data-ttu-id="e28ac-117">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-117">Table</span></span>|@Name|<span data-ttu-id="e28ac-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-118">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-119">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-119">3</span></span>|  
|<span data-ttu-id="e28ac-120">TableType</span><span class="sxs-lookup"><span data-stu-id="e28ac-120">TableType</span></span>|@TableType|<span data-ttu-id="e28ac-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e28ac-121">TABLE_TYPE</span></span>|<span data-ttu-id="e28ac-122">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="e28ac-123">Especificación de los valores de restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="e28ac-124">Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.</span><span class="sxs-lookup"><span data-stu-id="e28ac-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="e28ac-125">Por ejemplo, para restringir las tablas devueltas por el **método GetSchema** solo a las tablas del esquema "Sales", establezca el segundo elemento de la matriz en "Sales" antes de pasarlo al método **GetSchema.**</span><span class="sxs-lookup"><span data-stu-id="e28ac-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e28ac-126">Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.</span><span class="sxs-lookup"><span data-stu-id="e28ac-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="e28ac-127">La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.</span><span class="sxs-lookup"><span data-stu-id="e28ac-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="e28ac-128">Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.</span><span class="sxs-lookup"><span data-stu-id="e28ac-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e28ac-129">El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="e28ac-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="e28ac-130">Puede haber un número de restricciones inferior al máximo.</span><span class="sxs-lookup"><span data-stu-id="e28ac-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="e28ac-131">Se supone que las restricciones que faltan serán nulas (sin restricciones).</span><span class="sxs-lookup"><span data-stu-id="e28ac-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="e28ac-132">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas llamando al método **GetSchema** con el nombre de la colección de esquemas de restricciones, que es "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="e28ac-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="e28ac-133">Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.</span><span class="sxs-lookup"><span data-stu-id="e28ac-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e28ac-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e28ac-134">Example</span></span>  
 <span data-ttu-id="e28ac-135">En los ejemplos siguientes <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> se muestra cómo utilizar el método <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos de .NET Framework para la clase de SQL ServerSQL Server para recuperar información de esquema sobre todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks** y restringir la información devuelta solo a las tablas del esquema "Sales":</span><span class="sxs-lookup"><span data-stu-id="e28ac-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="e28ac-136">Restricciones de esquema de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e28ac-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="e28ac-137">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e28ac-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="e28ac-138">Usuarios</span><span class="sxs-lookup"><span data-stu-id="e28ac-138">Users</span></span>  
  
|<span data-ttu-id="e28ac-139">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-139">Restriction Name</span></span>|<span data-ttu-id="e28ac-140">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-140">Parameter Name</span></span>|<span data-ttu-id="e28ac-141">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-141">Restriction Default</span></span>|<span data-ttu-id="e28ac-142">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="e28ac-143">User_Name</span></span>|@Name|<span data-ttu-id="e28ac-144">name</span><span class="sxs-lookup"><span data-stu-id="e28ac-144">name</span></span>|<span data-ttu-id="e28ac-145">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="e28ac-146">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="e28ac-146">Databases</span></span>  
  
|<span data-ttu-id="e28ac-147">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-147">Restriction Name</span></span>|<span data-ttu-id="e28ac-148">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-148">Parameter Name</span></span>|<span data-ttu-id="e28ac-149">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-149">Restriction Default</span></span>|<span data-ttu-id="e28ac-150">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="e28ac-151">Name</span></span>|@Name|<span data-ttu-id="e28ac-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="e28ac-152">Name</span></span>|<span data-ttu-id="e28ac-153">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="e28ac-154">Tablas</span><span class="sxs-lookup"><span data-stu-id="e28ac-154">Tables</span></span>  
  
|<span data-ttu-id="e28ac-155">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-155">Restriction Name</span></span>|<span data-ttu-id="e28ac-156">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-156">Parameter Name</span></span>|<span data-ttu-id="e28ac-157">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-157">Restriction Default</span></span>|<span data-ttu-id="e28ac-158">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-159">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-159">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-160">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-161">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-161">1</span></span>|  
|<span data-ttu-id="e28ac-162">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-162">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-164">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-164">2</span></span>|  
|<span data-ttu-id="e28ac-165">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-165">Table</span></span>|@Name|<span data-ttu-id="e28ac-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-166">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-167">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-167">3</span></span>|  
|<span data-ttu-id="e28ac-168">TableType</span><span class="sxs-lookup"><span data-stu-id="e28ac-168">TableType</span></span>|@TableType|<span data-ttu-id="e28ac-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e28ac-169">TABLE_TYPE</span></span>|<span data-ttu-id="e28ac-170">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e28ac-171">Columnas</span><span class="sxs-lookup"><span data-stu-id="e28ac-171">Columns</span></span>  
  
|<span data-ttu-id="e28ac-172">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-172">Restriction Name</span></span>|<span data-ttu-id="e28ac-173">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-173">Parameter Name</span></span>|<span data-ttu-id="e28ac-174">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-174">Restriction Default</span></span>|<span data-ttu-id="e28ac-175">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-176">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-176">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-177">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-178">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-178">1</span></span>|  
|<span data-ttu-id="e28ac-179">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-179">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-181">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-181">2</span></span>|  
|<span data-ttu-id="e28ac-182">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-182">Table</span></span>|@Table|<span data-ttu-id="e28ac-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-183">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-184">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-184">3</span></span>|  
|<span data-ttu-id="e28ac-185">Columna</span><span class="sxs-lookup"><span data-stu-id="e28ac-185">Column</span></span>|@Column|<span data-ttu-id="e28ac-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-186">COLUMN_NAME</span></span>|<span data-ttu-id="e28ac-187">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="e28ac-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="e28ac-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="e28ac-189">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-189">Restriction Name</span></span>|<span data-ttu-id="e28ac-190">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-190">Parameter Name</span></span>|<span data-ttu-id="e28ac-191">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-191">Restriction Default</span></span>|<span data-ttu-id="e28ac-192">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-193">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-193">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-194">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-195">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-195">1</span></span>|  
|<span data-ttu-id="e28ac-196">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-196">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-198">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-198">2</span></span>|  
|<span data-ttu-id="e28ac-199">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-199">Table</span></span>|@Table|<span data-ttu-id="e28ac-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-200">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-201">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-201">3</span></span>|  
|<span data-ttu-id="e28ac-202">Columna</span><span class="sxs-lookup"><span data-stu-id="e28ac-202">Column</span></span>|@Column|<span data-ttu-id="e28ac-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-203">COLUMN_NAME</span></span>|<span data-ttu-id="e28ac-204">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e28ac-205">Vistas</span><span class="sxs-lookup"><span data-stu-id="e28ac-205">Views</span></span>  
  
|<span data-ttu-id="e28ac-206">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-206">Restriction Name</span></span>|<span data-ttu-id="e28ac-207">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-207">Parameter Name</span></span>|<span data-ttu-id="e28ac-208">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-208">Restriction Default</span></span>|<span data-ttu-id="e28ac-209">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-210">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-210">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-211">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-212">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-212">1</span></span>|  
|<span data-ttu-id="e28ac-213">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-213">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-215">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-215">2</span></span>|  
|<span data-ttu-id="e28ac-216">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-216">Table</span></span>|@Table|<span data-ttu-id="e28ac-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-217">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-218">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="e28ac-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="e28ac-219">ViewColumns</span></span>  
  
|<span data-ttu-id="e28ac-220">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-220">Restriction Name</span></span>|<span data-ttu-id="e28ac-221">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-221">Parameter Name</span></span>|<span data-ttu-id="e28ac-222">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-222">Restriction Default</span></span>|<span data-ttu-id="e28ac-223">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-224">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-224">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-225">VIEW_CATALOG</span></span>|<span data-ttu-id="e28ac-226">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-226">1</span></span>|  
|<span data-ttu-id="e28ac-227">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-227">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="e28ac-229">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-229">2</span></span>|  
|<span data-ttu-id="e28ac-230">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-230">Table</span></span>|@Table|<span data-ttu-id="e28ac-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-231">VIEW_NAME</span></span>|<span data-ttu-id="e28ac-232">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-232">3</span></span>|  
|<span data-ttu-id="e28ac-233">Columna</span><span class="sxs-lookup"><span data-stu-id="e28ac-233">Column</span></span>|@Column|<span data-ttu-id="e28ac-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-234">COLUMN_NAME</span></span>|<span data-ttu-id="e28ac-235">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e28ac-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e28ac-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e28ac-237">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-237">Restriction Name</span></span>|<span data-ttu-id="e28ac-238">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-238">Parameter Name</span></span>|<span data-ttu-id="e28ac-239">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-239">Restriction Default</span></span>|<span data-ttu-id="e28ac-240">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-241">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-241">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="e28ac-243">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-243">1</span></span>|  
|<span data-ttu-id="e28ac-244">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-244">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="e28ac-246">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-246">2</span></span>|  
|<span data-ttu-id="e28ac-247">Nombre</span><span class="sxs-lookup"><span data-stu-id="e28ac-247">Name</span></span>|@Name|<span data-ttu-id="e28ac-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="e28ac-249">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-249">3</span></span>|  
|<span data-ttu-id="e28ac-250">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-250">Parameter</span></span>|@Parameter|<span data-ttu-id="e28ac-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-251">PARAMETER_NAME</span></span>|<span data-ttu-id="e28ac-252">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e28ac-253">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e28ac-253">Procedures</span></span>  
  
|<span data-ttu-id="e28ac-254">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-254">Restriction Name</span></span>|<span data-ttu-id="e28ac-255">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-255">Parameter Name</span></span>|<span data-ttu-id="e28ac-256">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-256">Restriction Default</span></span>|<span data-ttu-id="e28ac-257">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-258">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="e28ac-260">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-260">1</span></span>|  
|<span data-ttu-id="e28ac-261">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-261">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="e28ac-263">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-263">2</span></span>|  
|<span data-ttu-id="e28ac-264">Nombre</span><span class="sxs-lookup"><span data-stu-id="e28ac-264">Name</span></span>|@Name|<span data-ttu-id="e28ac-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="e28ac-266">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-266">3</span></span>|  
|<span data-ttu-id="e28ac-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="e28ac-267">Type</span></span>|@Type|<span data-ttu-id="e28ac-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e28ac-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="e28ac-269">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="e28ac-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="e28ac-270">IndexColumns</span></span>  
  
|<span data-ttu-id="e28ac-271">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-271">Restriction Name</span></span>|<span data-ttu-id="e28ac-272">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-272">Parameter Name</span></span>|<span data-ttu-id="e28ac-273">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-273">Restriction Default</span></span>|<span data-ttu-id="e28ac-274">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-275">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-275">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="e28ac-276">db_name()</span></span>|<span data-ttu-id="e28ac-277">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-277">1</span></span>|  
|<span data-ttu-id="e28ac-278">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-278">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="e28ac-279">user_name()</span></span>|<span data-ttu-id="e28ac-280">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-280">2</span></span>|  
|<span data-ttu-id="e28ac-281">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-281">Table</span></span>|@Table|<span data-ttu-id="e28ac-282">o.name</span><span class="sxs-lookup"><span data-stu-id="e28ac-282">o.name</span></span>|<span data-ttu-id="e28ac-283">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-283">3</span></span>|  
|<span data-ttu-id="e28ac-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="e28ac-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="e28ac-285">x.name</span><span class="sxs-lookup"><span data-stu-id="e28ac-285">x.name</span></span>|<span data-ttu-id="e28ac-286">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-286">4</span></span>|  
|<span data-ttu-id="e28ac-287">Columna</span><span class="sxs-lookup"><span data-stu-id="e28ac-287">Column</span></span>|@Column|<span data-ttu-id="e28ac-288">c.name</span><span class="sxs-lookup"><span data-stu-id="e28ac-288">c.name</span></span>|<span data-ttu-id="e28ac-289">5</span><span class="sxs-lookup"><span data-stu-id="e28ac-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e28ac-290">Índices</span><span class="sxs-lookup"><span data-stu-id="e28ac-290">Indexes</span></span>  
  
|<span data-ttu-id="e28ac-291">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-291">Restriction Name</span></span>|<span data-ttu-id="e28ac-292">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-292">Parameter Name</span></span>|<span data-ttu-id="e28ac-293">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-293">Restriction Default</span></span>|<span data-ttu-id="e28ac-294">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-295">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-295">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="e28ac-296">db_name()</span></span>|<span data-ttu-id="e28ac-297">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-297">1</span></span>|  
|<span data-ttu-id="e28ac-298">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-298">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="e28ac-299">user_name()</span></span>|<span data-ttu-id="e28ac-300">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-300">2</span></span>|  
|<span data-ttu-id="e28ac-301">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-301">Table</span></span>|@Table|<span data-ttu-id="e28ac-302">o.name</span><span class="sxs-lookup"><span data-stu-id="e28ac-302">o.name</span></span>|<span data-ttu-id="e28ac-303">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="e28ac-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="e28ac-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="e28ac-305">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-305">Restriction Name</span></span>|<span data-ttu-id="e28ac-306">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-306">Parameter Name</span></span>|<span data-ttu-id="e28ac-307">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-307">Restriction Default</span></span>|<span data-ttu-id="e28ac-308">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="e28ac-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="e28ac-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="e28ac-310">assemblies.name</span></span>|<span data-ttu-id="e28ac-311">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-311">1</span></span>|  
|<span data-ttu-id="e28ac-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="e28ac-312">udt_name</span></span>|@UDTName|<span data-ttu-id="e28ac-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="e28ac-313">types.assembly_class</span></span>|<span data-ttu-id="e28ac-314">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="e28ac-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="e28ac-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="e28ac-316">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-316">Restriction Name</span></span>|<span data-ttu-id="e28ac-317">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-317">Parameter Name</span></span>|<span data-ttu-id="e28ac-318">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-318">Restriction Default</span></span>|<span data-ttu-id="e28ac-319">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-320">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-320">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="e28ac-322">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-322">1</span></span>|  
|<span data-ttu-id="e28ac-323">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-323">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="e28ac-325">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-325">2</span></span>|  
|<span data-ttu-id="e28ac-326">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-326">Table</span></span>|@Table|<span data-ttu-id="e28ac-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-327">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-328">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-328">3</span></span>|  
|<span data-ttu-id="e28ac-329">Nombre</span><span class="sxs-lookup"><span data-stu-id="e28ac-329">Name</span></span>|@Name|<span data-ttu-id="e28ac-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="e28ac-331">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="e28ac-332">Restricciones de esquema de SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="e28ac-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="e28ac-333">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e28ac-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="e28ac-334">Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="e28ac-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="e28ac-335">No se admiten en versiones anteriores de .NET Framework y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e28ac-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="e28ac-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="e28ac-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="e28ac-337">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-337">Restriction Name</span></span>|<span data-ttu-id="e28ac-338">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-338">Parameter Name</span></span>|<span data-ttu-id="e28ac-339">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-339">Restriction Default</span></span>|<span data-ttu-id="e28ac-340">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-341">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-341">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-342">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-343">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-343">1</span></span>|  
|<span data-ttu-id="e28ac-344">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-344">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-346">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-346">2</span></span>|  
|<span data-ttu-id="e28ac-347">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-347">Table</span></span>|@Table|<span data-ttu-id="e28ac-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-348">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-349">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="e28ac-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="e28ac-350">AllColumns</span></span>  
  
|<span data-ttu-id="e28ac-351">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-351">Restriction Name</span></span>|<span data-ttu-id="e28ac-352">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e28ac-352">Parameter Name</span></span>|<span data-ttu-id="e28ac-353">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="e28ac-353">Restriction Default</span></span>|<span data-ttu-id="e28ac-354">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="e28ac-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="e28ac-355">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e28ac-355">Catalog</span></span>|@Catalog|<span data-ttu-id="e28ac-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e28ac-356">TABLE_CATALOG</span></span>|<span data-ttu-id="e28ac-357">1</span><span class="sxs-lookup"><span data-stu-id="e28ac-357">1</span></span>|  
|<span data-ttu-id="e28ac-358">Propietario</span><span class="sxs-lookup"><span data-stu-id="e28ac-358">Owner</span></span>|@Owner|<span data-ttu-id="e28ac-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e28ac-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="e28ac-360">2</span><span class="sxs-lookup"><span data-stu-id="e28ac-360">2</span></span>|  
|<span data-ttu-id="e28ac-361">Tabla</span><span class="sxs-lookup"><span data-stu-id="e28ac-361">Table</span></span>|@Table|<span data-ttu-id="e28ac-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-362">TABLE_NAME</span></span>|<span data-ttu-id="e28ac-363">3</span><span class="sxs-lookup"><span data-stu-id="e28ac-363">3</span></span>|  
|<span data-ttu-id="e28ac-364">Columna</span><span class="sxs-lookup"><span data-stu-id="e28ac-364">Column</span></span>|@Column|<span data-ttu-id="e28ac-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e28ac-365">COLUMN_NAME</span></span>|<span data-ttu-id="e28ac-366">4</span><span class="sxs-lookup"><span data-stu-id="e28ac-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e28ac-367">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e28ac-367">See also</span></span>

- [<span data-ttu-id="e28ac-368">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e28ac-368">ADO.NET Overview</span></span>](ado-net-overview.md)
