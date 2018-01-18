---
title: Restricciones de esquema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f5b004b70716c61af8ac37fef76f660c488e5a74
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="schema-restrictions"></a><span data-ttu-id="69316-102">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="69316-102">Schema Restrictions</span></span>
<span data-ttu-id="69316-103">El segundo parámetro opcional de la **GetSchema** método es las restricciones que se utilizan para limitar la cantidad de información de esquema devuelven se pasa a la **GetSchema** método como una matriz de cadenas .</span><span class="sxs-lookup"><span data-stu-id="69316-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="69316-104">La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.</span><span class="sxs-lookup"><span data-stu-id="69316-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="69316-105">Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69316-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="69316-106">Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="69316-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="69316-107">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-107">Restriction Name</span></span>|<span data-ttu-id="69316-108">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-108">Parameter Name</span></span>|<span data-ttu-id="69316-109">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-109">Restriction Default</span></span>|<span data-ttu-id="69316-110">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-111">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-111">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-112">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-113">1</span><span class="sxs-lookup"><span data-stu-id="69316-113">1</span></span>|  
|<span data-ttu-id="69316-114">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-114">Owner</span></span>|@Owner|<span data-ttu-id="69316-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-116">2</span><span class="sxs-lookup"><span data-stu-id="69316-116">2</span></span>|  
|<span data-ttu-id="69316-117">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-117">Table</span></span>|@Name|<span data-ttu-id="69316-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-118">TABLE_NAME</span></span>|<span data-ttu-id="69316-119">3</span><span class="sxs-lookup"><span data-stu-id="69316-119">3</span></span>|  
|<span data-ttu-id="69316-120">TableType</span><span class="sxs-lookup"><span data-stu-id="69316-120">TableType</span></span>|@TableType|<span data-ttu-id="69316-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69316-121">TABLE_TYPE</span></span>|<span data-ttu-id="69316-122">4</span><span class="sxs-lookup"><span data-stu-id="69316-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="69316-123">Especificación de los valores de restricción</span><span class="sxs-lookup"><span data-stu-id="69316-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="69316-124">Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.</span><span class="sxs-lookup"><span data-stu-id="69316-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="69316-125">Por ejemplo, para restringir las tablas devueltas por la **GetSchema** método sólo a esas tablas en el esquema "Sales", establezca el segundo elemento de la matriz en "Sales" antes de pasarlo a la **GetSchema** método.</span><span class="sxs-lookup"><span data-stu-id="69316-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69316-126">Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.</span><span class="sxs-lookup"><span data-stu-id="69316-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="69316-127">La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.</span><span class="sxs-lookup"><span data-stu-id="69316-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="69316-128">Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.</span><span class="sxs-lookup"><span data-stu-id="69316-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69316-129">El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="69316-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="69316-130">Puede haber un número de restricciones inferior al máximo.</span><span class="sxs-lookup"><span data-stu-id="69316-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="69316-131">Se supone que las restricciones que faltan serán nulas (sin restricciones).</span><span class="sxs-lookup"><span data-stu-id="69316-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="69316-132">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas mediante la llamada la **GetSchema** método con el nombre de la colección de esquemas de restricciones, que es "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="69316-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="69316-133">Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.</span><span class="sxs-lookup"><span data-stu-id="69316-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="69316-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69316-134">Example</span></span>  
 <span data-ttu-id="69316-135">Los ejemplos siguientes muestran cómo utilizar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos de .NET Framework para SQL Server <xref:System.Data.SqlClient.SqlConnection> clase para recuperar información de esquema de todas las tablas contenidas en el **AdventureWorks**base de datos de ejemplo y restringir la información devuelta a solo las tablas en el esquema "Sales":</span><span class="sxs-lookup"><span data-stu-id="69316-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="69316-136">Restricciones de esquema de SQL Server</span><span class="sxs-lookup"><span data-stu-id="69316-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="69316-137">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69316-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="69316-138">Usuarios</span><span class="sxs-lookup"><span data-stu-id="69316-138">Users</span></span>  
  
|<span data-ttu-id="69316-139">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-139">Restriction Name</span></span>|<span data-ttu-id="69316-140">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-140">Parameter Name</span></span>|<span data-ttu-id="69316-141">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-141">Restriction Default</span></span>|<span data-ttu-id="69316-142">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="69316-143">User_Name</span></span>|@Name|<span data-ttu-id="69316-144">name</span><span class="sxs-lookup"><span data-stu-id="69316-144">name</span></span>|<span data-ttu-id="69316-145">1</span><span class="sxs-lookup"><span data-stu-id="69316-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="69316-146">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="69316-146">Databases</span></span>  
  
|<span data-ttu-id="69316-147">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-147">Restriction Name</span></span>|<span data-ttu-id="69316-148">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-148">Parameter Name</span></span>|<span data-ttu-id="69316-149">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-149">Restriction Default</span></span>|<span data-ttu-id="69316-150">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="69316-151">Name</span></span>|@Name|<span data-ttu-id="69316-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="69316-152">Name</span></span>|<span data-ttu-id="69316-153">1</span><span class="sxs-lookup"><span data-stu-id="69316-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="69316-154">Tablas</span><span class="sxs-lookup"><span data-stu-id="69316-154">Tables</span></span>  
  
|<span data-ttu-id="69316-155">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-155">Restriction Name</span></span>|<span data-ttu-id="69316-156">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-156">Parameter Name</span></span>|<span data-ttu-id="69316-157">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-157">Restriction Default</span></span>|<span data-ttu-id="69316-158">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-159">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-159">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-160">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-161">1</span><span class="sxs-lookup"><span data-stu-id="69316-161">1</span></span>|  
|<span data-ttu-id="69316-162">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-162">Owner</span></span>|@Owner|<span data-ttu-id="69316-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-164">2</span><span class="sxs-lookup"><span data-stu-id="69316-164">2</span></span>|  
|<span data-ttu-id="69316-165">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-165">Table</span></span>|@Name|<span data-ttu-id="69316-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-166">TABLE_NAME</span></span>|<span data-ttu-id="69316-167">3</span><span class="sxs-lookup"><span data-stu-id="69316-167">3</span></span>|  
|<span data-ttu-id="69316-168">TableType</span><span class="sxs-lookup"><span data-stu-id="69316-168">TableType</span></span>|@TableType|<span data-ttu-id="69316-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69316-169">TABLE_TYPE</span></span>|<span data-ttu-id="69316-170">4</span><span class="sxs-lookup"><span data-stu-id="69316-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="69316-171">Columnas</span><span class="sxs-lookup"><span data-stu-id="69316-171">Columns</span></span>  
  
|<span data-ttu-id="69316-172">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-172">Restriction Name</span></span>|<span data-ttu-id="69316-173">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-173">Parameter Name</span></span>|<span data-ttu-id="69316-174">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-174">Restriction Default</span></span>|<span data-ttu-id="69316-175">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-176">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-176">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-177">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-178">1</span><span class="sxs-lookup"><span data-stu-id="69316-178">1</span></span>|  
|<span data-ttu-id="69316-179">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-179">Owner</span></span>|@Owner|<span data-ttu-id="69316-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-181">2</span><span class="sxs-lookup"><span data-stu-id="69316-181">2</span></span>|  
|<span data-ttu-id="69316-182">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-182">Table</span></span>|@Table|<span data-ttu-id="69316-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-183">TABLE_NAME</span></span>|<span data-ttu-id="69316-184">3</span><span class="sxs-lookup"><span data-stu-id="69316-184">3</span></span>|  
|<span data-ttu-id="69316-185">Columna</span><span class="sxs-lookup"><span data-stu-id="69316-185">Column</span></span>|@Column|<span data-ttu-id="69316-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-186">COLUMN_NAME</span></span>|<span data-ttu-id="69316-187">4</span><span class="sxs-lookup"><span data-stu-id="69316-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="69316-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="69316-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="69316-189">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-189">Restriction Name</span></span>|<span data-ttu-id="69316-190">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-190">Parameter Name</span></span>|<span data-ttu-id="69316-191">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-191">Restriction Default</span></span>|<span data-ttu-id="69316-192">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-193">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-193">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-194">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-195">1</span><span class="sxs-lookup"><span data-stu-id="69316-195">1</span></span>|  
|<span data-ttu-id="69316-196">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-196">Owner</span></span>|@Owner|<span data-ttu-id="69316-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-198">2</span><span class="sxs-lookup"><span data-stu-id="69316-198">2</span></span>|  
|<span data-ttu-id="69316-199">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-199">Table</span></span>|@Table|<span data-ttu-id="69316-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-200">TABLE_NAME</span></span>|<span data-ttu-id="69316-201">3</span><span class="sxs-lookup"><span data-stu-id="69316-201">3</span></span>|  
|<span data-ttu-id="69316-202">Columna</span><span class="sxs-lookup"><span data-stu-id="69316-202">Column</span></span>|@Column|<span data-ttu-id="69316-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-203">COLUMN_NAME</span></span>|<span data-ttu-id="69316-204">4</span><span class="sxs-lookup"><span data-stu-id="69316-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="69316-205">Vistas</span><span class="sxs-lookup"><span data-stu-id="69316-205">Views</span></span>  
  
|<span data-ttu-id="69316-206">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-206">Restriction Name</span></span>|<span data-ttu-id="69316-207">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-207">Parameter Name</span></span>|<span data-ttu-id="69316-208">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-208">Restriction Default</span></span>|<span data-ttu-id="69316-209">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-210">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-210">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-211">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-212">1</span><span class="sxs-lookup"><span data-stu-id="69316-212">1</span></span>|  
|<span data-ttu-id="69316-213">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-213">Owner</span></span>|@Owner|<span data-ttu-id="69316-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-215">2</span><span class="sxs-lookup"><span data-stu-id="69316-215">2</span></span>|  
|<span data-ttu-id="69316-216">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-216">Table</span></span>|@Table|<span data-ttu-id="69316-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-217">TABLE_NAME</span></span>|<span data-ttu-id="69316-218">3</span><span class="sxs-lookup"><span data-stu-id="69316-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="69316-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="69316-219">ViewColumns</span></span>  
  
|<span data-ttu-id="69316-220">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-220">Restriction Name</span></span>|<span data-ttu-id="69316-221">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-221">Parameter Name</span></span>|<span data-ttu-id="69316-222">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-222">Restriction Default</span></span>|<span data-ttu-id="69316-223">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-224">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-224">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-225">VIEW_CATALOG</span></span>|<span data-ttu-id="69316-226">1</span><span class="sxs-lookup"><span data-stu-id="69316-226">1</span></span>|  
|<span data-ttu-id="69316-227">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-227">Owner</span></span>|@Owner|<span data-ttu-id="69316-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="69316-229">2</span><span class="sxs-lookup"><span data-stu-id="69316-229">2</span></span>|  
|<span data-ttu-id="69316-230">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-230">Table</span></span>|@Table|<span data-ttu-id="69316-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-231">VIEW_NAME</span></span>|<span data-ttu-id="69316-232">3</span><span class="sxs-lookup"><span data-stu-id="69316-232">3</span></span>|  
|<span data-ttu-id="69316-233">Columna</span><span class="sxs-lookup"><span data-stu-id="69316-233">Column</span></span>|@Column|<span data-ttu-id="69316-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-234">COLUMN_NAME</span></span>|<span data-ttu-id="69316-235">4</span><span class="sxs-lookup"><span data-stu-id="69316-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="69316-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69316-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="69316-237">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-237">Restriction Name</span></span>|<span data-ttu-id="69316-238">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-238">Parameter Name</span></span>|<span data-ttu-id="69316-239">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-239">Restriction Default</span></span>|<span data-ttu-id="69316-240">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-241">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-241">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="69316-243">1</span><span class="sxs-lookup"><span data-stu-id="69316-243">1</span></span>|  
|<span data-ttu-id="69316-244">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-244">Owner</span></span>|@Owner|<span data-ttu-id="69316-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="69316-246">2</span><span class="sxs-lookup"><span data-stu-id="69316-246">2</span></span>|  
|<span data-ttu-id="69316-247">Nombre</span><span class="sxs-lookup"><span data-stu-id="69316-247">Name</span></span>|@Name|<span data-ttu-id="69316-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="69316-249">3</span><span class="sxs-lookup"><span data-stu-id="69316-249">3</span></span>|  
|<span data-ttu-id="69316-250">Parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-250">Parameter</span></span>|@Parameter|<span data-ttu-id="69316-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-251">PARAMETER_NAME</span></span>|<span data-ttu-id="69316-252">4</span><span class="sxs-lookup"><span data-stu-id="69316-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="69316-253">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="69316-253">Procedures</span></span>  
  
|<span data-ttu-id="69316-254">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-254">Restriction Name</span></span>|<span data-ttu-id="69316-255">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-255">Parameter Name</span></span>|<span data-ttu-id="69316-256">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-256">Restriction Default</span></span>|<span data-ttu-id="69316-257">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-258">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="69316-260">1</span><span class="sxs-lookup"><span data-stu-id="69316-260">1</span></span>|  
|<span data-ttu-id="69316-261">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-261">Owner</span></span>|@Owner|<span data-ttu-id="69316-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="69316-263">2</span><span class="sxs-lookup"><span data-stu-id="69316-263">2</span></span>|  
|<span data-ttu-id="69316-264">Nombre</span><span class="sxs-lookup"><span data-stu-id="69316-264">Name</span></span>|@Name|<span data-ttu-id="69316-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="69316-266">3</span><span class="sxs-lookup"><span data-stu-id="69316-266">3</span></span>|  
|<span data-ttu-id="69316-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="69316-267">Type</span></span>|@Type|<span data-ttu-id="69316-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69316-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="69316-269">4</span><span class="sxs-lookup"><span data-stu-id="69316-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="69316-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="69316-270">IndexColumns</span></span>  
  
|<span data-ttu-id="69316-271">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-271">Restriction Name</span></span>|<span data-ttu-id="69316-272">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-272">Parameter Name</span></span>|<span data-ttu-id="69316-273">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-273">Restriction Default</span></span>|<span data-ttu-id="69316-274">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-275">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-275">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="69316-276">db_name()</span></span>|<span data-ttu-id="69316-277">1</span><span class="sxs-lookup"><span data-stu-id="69316-277">1</span></span>|  
|<span data-ttu-id="69316-278">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-278">Owner</span></span>|@Owner|<span data-ttu-id="69316-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="69316-279">user_name()</span></span>|<span data-ttu-id="69316-280">2</span><span class="sxs-lookup"><span data-stu-id="69316-280">2</span></span>|  
|<span data-ttu-id="69316-281">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-281">Table</span></span>|@Table|<span data-ttu-id="69316-282">o.name</span><span class="sxs-lookup"><span data-stu-id="69316-282">o.name</span></span>|<span data-ttu-id="69316-283">3</span><span class="sxs-lookup"><span data-stu-id="69316-283">3</span></span>|  
|<span data-ttu-id="69316-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="69316-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="69316-285">x.name</span><span class="sxs-lookup"><span data-stu-id="69316-285">x.name</span></span>|<span data-ttu-id="69316-286">4</span><span class="sxs-lookup"><span data-stu-id="69316-286">4</span></span>|  
|<span data-ttu-id="69316-287">Columna</span><span class="sxs-lookup"><span data-stu-id="69316-287">Column</span></span>|@Column|<span data-ttu-id="69316-288">c.name</span><span class="sxs-lookup"><span data-stu-id="69316-288">c.name</span></span>|<span data-ttu-id="69316-289">5</span><span class="sxs-lookup"><span data-stu-id="69316-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="69316-290">Índices</span><span class="sxs-lookup"><span data-stu-id="69316-290">Indexes</span></span>  
  
|<span data-ttu-id="69316-291">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-291">Restriction Name</span></span>|<span data-ttu-id="69316-292">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-292">Parameter Name</span></span>|<span data-ttu-id="69316-293">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-293">Restriction Default</span></span>|<span data-ttu-id="69316-294">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-295">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-295">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="69316-296">db_name()</span></span>|<span data-ttu-id="69316-297">1</span><span class="sxs-lookup"><span data-stu-id="69316-297">1</span></span>|  
|<span data-ttu-id="69316-298">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-298">Owner</span></span>|@Owner|<span data-ttu-id="69316-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="69316-299">user_name()</span></span>|<span data-ttu-id="69316-300">2</span><span class="sxs-lookup"><span data-stu-id="69316-300">2</span></span>|  
|<span data-ttu-id="69316-301">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-301">Table</span></span>|@Table|<span data-ttu-id="69316-302">o.name</span><span class="sxs-lookup"><span data-stu-id="69316-302">o.name</span></span>|<span data-ttu-id="69316-303">3</span><span class="sxs-lookup"><span data-stu-id="69316-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="69316-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="69316-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="69316-305">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-305">Restriction Name</span></span>|<span data-ttu-id="69316-306">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-306">Parameter Name</span></span>|<span data-ttu-id="69316-307">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-307">Restriction Default</span></span>|<span data-ttu-id="69316-308">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="69316-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="69316-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="69316-310">assemblies.name</span></span>|<span data-ttu-id="69316-311">1</span><span class="sxs-lookup"><span data-stu-id="69316-311">1</span></span>|  
|<span data-ttu-id="69316-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="69316-312">udt_name</span></span>|@UDTName|<span data-ttu-id="69316-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="69316-313">types.assembly_class</span></span>|<span data-ttu-id="69316-314">2</span><span class="sxs-lookup"><span data-stu-id="69316-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="69316-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="69316-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="69316-316">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-316">Restriction Name</span></span>|<span data-ttu-id="69316-317">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-317">Parameter Name</span></span>|<span data-ttu-id="69316-318">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-318">Restriction Default</span></span>|<span data-ttu-id="69316-319">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-320">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-320">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="69316-322">1</span><span class="sxs-lookup"><span data-stu-id="69316-322">1</span></span>|  
|<span data-ttu-id="69316-323">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-323">Owner</span></span>|@Owner|<span data-ttu-id="69316-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="69316-325">2</span><span class="sxs-lookup"><span data-stu-id="69316-325">2</span></span>|  
|<span data-ttu-id="69316-326">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-326">Table</span></span>|@Table|<span data-ttu-id="69316-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-327">TABLE_NAME</span></span>|<span data-ttu-id="69316-328">3</span><span class="sxs-lookup"><span data-stu-id="69316-328">3</span></span>|  
|<span data-ttu-id="69316-329">Nombre</span><span class="sxs-lookup"><span data-stu-id="69316-329">Name</span></span>|@Name|<span data-ttu-id="69316-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="69316-331">4</span><span class="sxs-lookup"><span data-stu-id="69316-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="69316-332">Restricciones de esquema de SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="69316-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="69316-333">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="69316-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="69316-334">Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="69316-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="69316-335">No se admiten en versiones anteriores de .NET Framework y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69316-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="69316-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="69316-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="69316-337">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-337">Restriction Name</span></span>|<span data-ttu-id="69316-338">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-338">Parameter Name</span></span>|<span data-ttu-id="69316-339">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-339">Restriction Default</span></span>|<span data-ttu-id="69316-340">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-341">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-341">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-342">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-343">1</span><span class="sxs-lookup"><span data-stu-id="69316-343">1</span></span>|  
|<span data-ttu-id="69316-344">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-344">Owner</span></span>|@Owner|<span data-ttu-id="69316-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-346">2</span><span class="sxs-lookup"><span data-stu-id="69316-346">2</span></span>|  
|<span data-ttu-id="69316-347">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-347">Table</span></span>|@Table|<span data-ttu-id="69316-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-348">TABLE_NAME</span></span>|<span data-ttu-id="69316-349">3</span><span class="sxs-lookup"><span data-stu-id="69316-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="69316-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="69316-350">AllColumns</span></span>  
  
|<span data-ttu-id="69316-351">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-351">Restriction Name</span></span>|<span data-ttu-id="69316-352">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="69316-352">Parameter Name</span></span>|<span data-ttu-id="69316-353">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="69316-353">Restriction Default</span></span>|<span data-ttu-id="69316-354">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="69316-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="69316-355">Catálogo</span><span class="sxs-lookup"><span data-stu-id="69316-355">Catalog</span></span>|@Catalog|<span data-ttu-id="69316-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69316-356">TABLE_CATALOG</span></span>|<span data-ttu-id="69316-357">1</span><span class="sxs-lookup"><span data-stu-id="69316-357">1</span></span>|  
|<span data-ttu-id="69316-358">Propietario</span><span class="sxs-lookup"><span data-stu-id="69316-358">Owner</span></span>|@Owner|<span data-ttu-id="69316-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69316-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="69316-360">2</span><span class="sxs-lookup"><span data-stu-id="69316-360">2</span></span>|  
|<span data-ttu-id="69316-361">Tabla</span><span class="sxs-lookup"><span data-stu-id="69316-361">Table</span></span>|@Table|<span data-ttu-id="69316-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-362">TABLE_NAME</span></span>|<span data-ttu-id="69316-363">3</span><span class="sxs-lookup"><span data-stu-id="69316-363">3</span></span>|  
|<span data-ttu-id="69316-364">Columna</span><span class="sxs-lookup"><span data-stu-id="69316-364">Column</span></span>|@Column|<span data-ttu-id="69316-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69316-365">COLUMN_NAME</span></span>|<span data-ttu-id="69316-366">4</span><span class="sxs-lookup"><span data-stu-id="69316-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69316-367">Vea también</span><span class="sxs-lookup"><span data-stu-id="69316-367">See Also</span></span>  
 [<span data-ttu-id="69316-368">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="69316-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
