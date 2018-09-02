---
title: Restricciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417087"
---
# <a name="schema-restrictions"></a><span data-ttu-id="07bc0-102">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="07bc0-102">Schema Restrictions</span></span>
<span data-ttu-id="07bc0-103">El segundo parámetro opcional de la **GetSchema** método es devuelven las restricciones que se usan para limitar la cantidad de información de esquema y se pasa a la **GetSchema** método como una matriz de cadenas .</span><span class="sxs-lookup"><span data-stu-id="07bc0-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="07bc0-104">La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.</span><span class="sxs-lookup"><span data-stu-id="07bc0-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="07bc0-105">Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07bc0-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="07bc0-106">Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="07bc0-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="07bc0-107">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-107">Restriction Name</span></span>|<span data-ttu-id="07bc0-108">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-108">Parameter Name</span></span>|<span data-ttu-id="07bc0-109">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-109">Restriction Default</span></span>|<span data-ttu-id="07bc0-110">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-111">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-111">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-112">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-113">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-113">1</span></span>|  
|<span data-ttu-id="07bc0-114">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-114">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-116">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-116">2</span></span>|  
|<span data-ttu-id="07bc0-117">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-117">Table</span></span>|@Name|<span data-ttu-id="07bc0-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-118">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-119">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-119">3</span></span>|  
|<span data-ttu-id="07bc0-120">TableType</span><span class="sxs-lookup"><span data-stu-id="07bc0-120">TableType</span></span>|@TableType|<span data-ttu-id="07bc0-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07bc0-121">TABLE_TYPE</span></span>|<span data-ttu-id="07bc0-122">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="07bc0-123">Especificación de los valores de restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="07bc0-124">Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.</span><span class="sxs-lookup"><span data-stu-id="07bc0-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="07bc0-125">Por ejemplo restringir las tablas devuelto por la **GetSchema** método sólo a esas tablas en el esquema "Sales", establezca el segundo elemento de la matriz en "Ventas" antes de pasarlo a la **GetSchema** método.</span><span class="sxs-lookup"><span data-stu-id="07bc0-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07bc0-126">Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.</span><span class="sxs-lookup"><span data-stu-id="07bc0-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="07bc0-127">La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.</span><span class="sxs-lookup"><span data-stu-id="07bc0-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="07bc0-128">Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.</span><span class="sxs-lookup"><span data-stu-id="07bc0-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07bc0-129">El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="07bc0-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="07bc0-130">Puede haber un número de restricciones inferior al máximo.</span><span class="sxs-lookup"><span data-stu-id="07bc0-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="07bc0-131">Se supone que las restricciones que faltan serán nulas (sin restricciones).</span><span class="sxs-lookup"><span data-stu-id="07bc0-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="07bc0-132">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas mediante una llamada a la **GetSchema** método con el nombre de la colección de esquemas de restricciones, que es "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="07bc0-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="07bc0-133">Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.</span><span class="sxs-lookup"><span data-stu-id="07bc0-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="07bc0-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07bc0-134">Example</span></span>  
 <span data-ttu-id="07bc0-135">Los ejemplos siguientes muestran cómo usar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos .NET Framework para SQL Server <xref:System.Data.SqlClient.SqlConnection> clase para recuperar información de esquema de todas las tablas contenidas en el **AdventureWorks**base de datos de ejemplo y restringir la información devuelta a sólo las tablas en el esquema "Sales":</span><span class="sxs-lookup"><span data-stu-id="07bc0-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="07bc0-136">Restricciones de esquema de SQL Server</span><span class="sxs-lookup"><span data-stu-id="07bc0-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="07bc0-137">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07bc0-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="07bc0-138">Usuarios</span><span class="sxs-lookup"><span data-stu-id="07bc0-138">Users</span></span>  
  
|<span data-ttu-id="07bc0-139">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-139">Restriction Name</span></span>|<span data-ttu-id="07bc0-140">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-140">Parameter Name</span></span>|<span data-ttu-id="07bc0-141">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-141">Restriction Default</span></span>|<span data-ttu-id="07bc0-142">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="07bc0-143">User_Name</span></span>|@Name|<span data-ttu-id="07bc0-144">name</span><span class="sxs-lookup"><span data-stu-id="07bc0-144">name</span></span>|<span data-ttu-id="07bc0-145">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="07bc0-146">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="07bc0-146">Databases</span></span>  
  
|<span data-ttu-id="07bc0-147">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-147">Restriction Name</span></span>|<span data-ttu-id="07bc0-148">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-148">Parameter Name</span></span>|<span data-ttu-id="07bc0-149">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-149">Restriction Default</span></span>|<span data-ttu-id="07bc0-150">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-151">nombre</span><span class="sxs-lookup"><span data-stu-id="07bc0-151">Name</span></span>|@Name|<span data-ttu-id="07bc0-152">nombre</span><span class="sxs-lookup"><span data-stu-id="07bc0-152">Name</span></span>|<span data-ttu-id="07bc0-153">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="07bc0-154">Tablas</span><span class="sxs-lookup"><span data-stu-id="07bc0-154">Tables</span></span>  
  
|<span data-ttu-id="07bc0-155">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-155">Restriction Name</span></span>|<span data-ttu-id="07bc0-156">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-156">Parameter Name</span></span>|<span data-ttu-id="07bc0-157">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-157">Restriction Default</span></span>|<span data-ttu-id="07bc0-158">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-159">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-159">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-160">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-161">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-161">1</span></span>|  
|<span data-ttu-id="07bc0-162">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-162">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-164">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-164">2</span></span>|  
|<span data-ttu-id="07bc0-165">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-165">Table</span></span>|@Name|<span data-ttu-id="07bc0-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-166">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-167">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-167">3</span></span>|  
|<span data-ttu-id="07bc0-168">TableType</span><span class="sxs-lookup"><span data-stu-id="07bc0-168">TableType</span></span>|@TableType|<span data-ttu-id="07bc0-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07bc0-169">TABLE_TYPE</span></span>|<span data-ttu-id="07bc0-170">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="07bc0-171">Columnas</span><span class="sxs-lookup"><span data-stu-id="07bc0-171">Columns</span></span>  
  
|<span data-ttu-id="07bc0-172">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-172">Restriction Name</span></span>|<span data-ttu-id="07bc0-173">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-173">Parameter Name</span></span>|<span data-ttu-id="07bc0-174">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-174">Restriction Default</span></span>|<span data-ttu-id="07bc0-175">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-176">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-176">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-177">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-178">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-178">1</span></span>|  
|<span data-ttu-id="07bc0-179">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-179">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-181">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-181">2</span></span>|  
|<span data-ttu-id="07bc0-182">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-182">Table</span></span>|@Table|<span data-ttu-id="07bc0-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-183">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-184">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-184">3</span></span>|  
|<span data-ttu-id="07bc0-185">Columna</span><span class="sxs-lookup"><span data-stu-id="07bc0-185">Column</span></span>|@Column|<span data-ttu-id="07bc0-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-186">COLUMN_NAME</span></span>|<span data-ttu-id="07bc0-187">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="07bc0-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="07bc0-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="07bc0-189">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-189">Restriction Name</span></span>|<span data-ttu-id="07bc0-190">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-190">Parameter Name</span></span>|<span data-ttu-id="07bc0-191">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-191">Restriction Default</span></span>|<span data-ttu-id="07bc0-192">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-193">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-193">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-194">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-195">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-195">1</span></span>|  
|<span data-ttu-id="07bc0-196">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-196">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-198">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-198">2</span></span>|  
|<span data-ttu-id="07bc0-199">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-199">Table</span></span>|@Table|<span data-ttu-id="07bc0-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-200">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-201">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-201">3</span></span>|  
|<span data-ttu-id="07bc0-202">Columna</span><span class="sxs-lookup"><span data-stu-id="07bc0-202">Column</span></span>|@Column|<span data-ttu-id="07bc0-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-203">COLUMN_NAME</span></span>|<span data-ttu-id="07bc0-204">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="07bc0-205">Vistas</span><span class="sxs-lookup"><span data-stu-id="07bc0-205">Views</span></span>  
  
|<span data-ttu-id="07bc0-206">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-206">Restriction Name</span></span>|<span data-ttu-id="07bc0-207">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-207">Parameter Name</span></span>|<span data-ttu-id="07bc0-208">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-208">Restriction Default</span></span>|<span data-ttu-id="07bc0-209">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-210">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-210">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-211">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-212">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-212">1</span></span>|  
|<span data-ttu-id="07bc0-213">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-213">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-215">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-215">2</span></span>|  
|<span data-ttu-id="07bc0-216">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-216">Table</span></span>|@Table|<span data-ttu-id="07bc0-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-217">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-218">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="07bc0-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="07bc0-219">ViewColumns</span></span>  
  
|<span data-ttu-id="07bc0-220">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-220">Restriction Name</span></span>|<span data-ttu-id="07bc0-221">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-221">Parameter Name</span></span>|<span data-ttu-id="07bc0-222">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-222">Restriction Default</span></span>|<span data-ttu-id="07bc0-223">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-224">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-224">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-225">VIEW_CATALOG</span></span>|<span data-ttu-id="07bc0-226">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-226">1</span></span>|  
|<span data-ttu-id="07bc0-227">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-227">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="07bc0-229">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-229">2</span></span>|  
|<span data-ttu-id="07bc0-230">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-230">Table</span></span>|@Table|<span data-ttu-id="07bc0-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-231">VIEW_NAME</span></span>|<span data-ttu-id="07bc0-232">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-232">3</span></span>|  
|<span data-ttu-id="07bc0-233">Columna</span><span class="sxs-lookup"><span data-stu-id="07bc0-233">Column</span></span>|@Column|<span data-ttu-id="07bc0-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-234">COLUMN_NAME</span></span>|<span data-ttu-id="07bc0-235">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="07bc0-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="07bc0-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="07bc0-237">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-237">Restriction Name</span></span>|<span data-ttu-id="07bc0-238">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-238">Parameter Name</span></span>|<span data-ttu-id="07bc0-239">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-239">Restriction Default</span></span>|<span data-ttu-id="07bc0-240">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-241">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-241">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="07bc0-243">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-243">1</span></span>|  
|<span data-ttu-id="07bc0-244">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-244">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="07bc0-246">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-246">2</span></span>|  
|<span data-ttu-id="07bc0-247">nombre</span><span class="sxs-lookup"><span data-stu-id="07bc0-247">Name</span></span>|@Name|<span data-ttu-id="07bc0-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="07bc0-249">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-249">3</span></span>|  
|<span data-ttu-id="07bc0-250">Parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-250">Parameter</span></span>|@Parameter|<span data-ttu-id="07bc0-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-251">PARAMETER_NAME</span></span>|<span data-ttu-id="07bc0-252">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="07bc0-253">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="07bc0-253">Procedures</span></span>  
  
|<span data-ttu-id="07bc0-254">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-254">Restriction Name</span></span>|<span data-ttu-id="07bc0-255">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-255">Parameter Name</span></span>|<span data-ttu-id="07bc0-256">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-256">Restriction Default</span></span>|<span data-ttu-id="07bc0-257">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-258">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="07bc0-260">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-260">1</span></span>|  
|<span data-ttu-id="07bc0-261">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-261">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="07bc0-263">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-263">2</span></span>|  
|<span data-ttu-id="07bc0-264">nombre</span><span class="sxs-lookup"><span data-stu-id="07bc0-264">Name</span></span>|@Name|<span data-ttu-id="07bc0-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="07bc0-266">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-266">3</span></span>|  
|<span data-ttu-id="07bc0-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="07bc0-267">Type</span></span>|@Type|<span data-ttu-id="07bc0-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07bc0-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="07bc0-269">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="07bc0-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="07bc0-270">IndexColumns</span></span>  
  
|<span data-ttu-id="07bc0-271">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-271">Restriction Name</span></span>|<span data-ttu-id="07bc0-272">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-272">Parameter Name</span></span>|<span data-ttu-id="07bc0-273">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-273">Restriction Default</span></span>|<span data-ttu-id="07bc0-274">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-275">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-275">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="07bc0-276">db_name()</span></span>|<span data-ttu-id="07bc0-277">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-277">1</span></span>|  
|<span data-ttu-id="07bc0-278">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-278">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="07bc0-279">user_name()</span></span>|<span data-ttu-id="07bc0-280">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-280">2</span></span>|  
|<span data-ttu-id="07bc0-281">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-281">Table</span></span>|@Table|<span data-ttu-id="07bc0-282">o.name</span><span class="sxs-lookup"><span data-stu-id="07bc0-282">o.name</span></span>|<span data-ttu-id="07bc0-283">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-283">3</span></span>|  
|<span data-ttu-id="07bc0-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="07bc0-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="07bc0-285">x.name</span><span class="sxs-lookup"><span data-stu-id="07bc0-285">x.name</span></span>|<span data-ttu-id="07bc0-286">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-286">4</span></span>|  
|<span data-ttu-id="07bc0-287">Columna</span><span class="sxs-lookup"><span data-stu-id="07bc0-287">Column</span></span>|@Column|<span data-ttu-id="07bc0-288">c.name</span><span class="sxs-lookup"><span data-stu-id="07bc0-288">c.name</span></span>|<span data-ttu-id="07bc0-289">5</span><span class="sxs-lookup"><span data-stu-id="07bc0-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="07bc0-290">Índices</span><span class="sxs-lookup"><span data-stu-id="07bc0-290">Indexes</span></span>  
  
|<span data-ttu-id="07bc0-291">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-291">Restriction Name</span></span>|<span data-ttu-id="07bc0-292">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-292">Parameter Name</span></span>|<span data-ttu-id="07bc0-293">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-293">Restriction Default</span></span>|<span data-ttu-id="07bc0-294">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-295">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-295">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="07bc0-296">db_name()</span></span>|<span data-ttu-id="07bc0-297">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-297">1</span></span>|  
|<span data-ttu-id="07bc0-298">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-298">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="07bc0-299">user_name()</span></span>|<span data-ttu-id="07bc0-300">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-300">2</span></span>|  
|<span data-ttu-id="07bc0-301">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-301">Table</span></span>|@Table|<span data-ttu-id="07bc0-302">o.name</span><span class="sxs-lookup"><span data-stu-id="07bc0-302">o.name</span></span>|<span data-ttu-id="07bc0-303">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="07bc0-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="07bc0-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="07bc0-305">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-305">Restriction Name</span></span>|<span data-ttu-id="07bc0-306">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-306">Parameter Name</span></span>|<span data-ttu-id="07bc0-307">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-307">Restriction Default</span></span>|<span data-ttu-id="07bc0-308">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="07bc0-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="07bc0-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="07bc0-310">assemblies.name</span></span>|<span data-ttu-id="07bc0-311">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-311">1</span></span>|  
|<span data-ttu-id="07bc0-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="07bc0-312">udt_name</span></span>|@UDTName|<span data-ttu-id="07bc0-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="07bc0-313">types.assembly_class</span></span>|<span data-ttu-id="07bc0-314">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="07bc0-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="07bc0-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="07bc0-316">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-316">Restriction Name</span></span>|<span data-ttu-id="07bc0-317">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-317">Parameter Name</span></span>|<span data-ttu-id="07bc0-318">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-318">Restriction Default</span></span>|<span data-ttu-id="07bc0-319">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-320">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-320">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="07bc0-322">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-322">1</span></span>|  
|<span data-ttu-id="07bc0-323">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-323">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="07bc0-325">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-325">2</span></span>|  
|<span data-ttu-id="07bc0-326">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-326">Table</span></span>|@Table|<span data-ttu-id="07bc0-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-327">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-328">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-328">3</span></span>|  
|<span data-ttu-id="07bc0-329">nombre</span><span class="sxs-lookup"><span data-stu-id="07bc0-329">Name</span></span>|@Name|<span data-ttu-id="07bc0-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="07bc0-331">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="07bc0-332">Restricciones de esquema de SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="07bc0-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="07bc0-333">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="07bc0-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="07bc0-334">Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="07bc0-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="07bc0-335">No se admiten en versiones anteriores de .NET Framework y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07bc0-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="07bc0-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="07bc0-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="07bc0-337">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-337">Restriction Name</span></span>|<span data-ttu-id="07bc0-338">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-338">Parameter Name</span></span>|<span data-ttu-id="07bc0-339">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-339">Restriction Default</span></span>|<span data-ttu-id="07bc0-340">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-341">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-341">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-342">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-343">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-343">1</span></span>|  
|<span data-ttu-id="07bc0-344">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-344">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-346">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-346">2</span></span>|  
|<span data-ttu-id="07bc0-347">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-347">Table</span></span>|@Table|<span data-ttu-id="07bc0-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-348">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-349">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="07bc0-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="07bc0-350">AllColumns</span></span>  
  
|<span data-ttu-id="07bc0-351">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-351">Restriction Name</span></span>|<span data-ttu-id="07bc0-352">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="07bc0-352">Parameter Name</span></span>|<span data-ttu-id="07bc0-353">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="07bc0-353">Restriction Default</span></span>|<span data-ttu-id="07bc0-354">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="07bc0-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="07bc0-355">Catálogo</span><span class="sxs-lookup"><span data-stu-id="07bc0-355">Catalog</span></span>|@Catalog|<span data-ttu-id="07bc0-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07bc0-356">TABLE_CATALOG</span></span>|<span data-ttu-id="07bc0-357">1</span><span class="sxs-lookup"><span data-stu-id="07bc0-357">1</span></span>|  
|<span data-ttu-id="07bc0-358">Propietario</span><span class="sxs-lookup"><span data-stu-id="07bc0-358">Owner</span></span>|@Owner|<span data-ttu-id="07bc0-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07bc0-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="07bc0-360">2</span><span class="sxs-lookup"><span data-stu-id="07bc0-360">2</span></span>|  
|<span data-ttu-id="07bc0-361">Tabla</span><span class="sxs-lookup"><span data-stu-id="07bc0-361">Table</span></span>|@Table|<span data-ttu-id="07bc0-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-362">TABLE_NAME</span></span>|<span data-ttu-id="07bc0-363">3</span><span class="sxs-lookup"><span data-stu-id="07bc0-363">3</span></span>|  
|<span data-ttu-id="07bc0-364">Columna</span><span class="sxs-lookup"><span data-stu-id="07bc0-364">Column</span></span>|@Column|<span data-ttu-id="07bc0-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07bc0-365">COLUMN_NAME</span></span>|<span data-ttu-id="07bc0-366">4</span><span class="sxs-lookup"><span data-stu-id="07bc0-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07bc0-367">Vea también</span><span class="sxs-lookup"><span data-stu-id="07bc0-367">See Also</span></span>  
 [<span data-ttu-id="07bc0-368">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="07bc0-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
