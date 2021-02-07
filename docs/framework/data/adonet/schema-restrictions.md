---
description: 'Más información acerca de: restricciones de esquema'
title: Restricciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 74ddfe5b8aaf9b8193e0c0b2a929ccde333eac26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719050"
---
# <a name="schema-restrictions"></a><span data-ttu-id="99935-103">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="99935-103">Schema Restrictions</span></span>

<span data-ttu-id="99935-104">El segundo parámetro opcional del método **GetSchema** son las restricciones que se usan para limitar la cantidad de información de esquema devuelta. Este parámetro se pasa al método **GetSchema** como una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="99935-104">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="99935-105">La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.</span><span class="sxs-lookup"><span data-stu-id="99935-105">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="99935-106">Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99935-106">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="99935-107">Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="99935-107">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="99935-108">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-108">Restriction Name</span></span>|<span data-ttu-id="99935-109">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-109">Parameter Name</span></span>|<span data-ttu-id="99935-110">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-110">Restriction Default</span></span>|<span data-ttu-id="99935-111">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-111">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-112">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-112">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-113">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-113">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-114">1</span><span class="sxs-lookup"><span data-stu-id="99935-114">1</span></span>|  
|<span data-ttu-id="99935-115">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-115">Owner</span></span>|@Owner|<span data-ttu-id="99935-116">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-116">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-117">2</span><span class="sxs-lookup"><span data-stu-id="99935-117">2</span></span>|  
|<span data-ttu-id="99935-118">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-118">Table</span></span>|@Name|<span data-ttu-id="99935-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-119">TABLE_NAME</span></span>|<span data-ttu-id="99935-120">3</span><span class="sxs-lookup"><span data-stu-id="99935-120">3</span></span>|  
|<span data-ttu-id="99935-121">TableType</span><span class="sxs-lookup"><span data-stu-id="99935-121">TableType</span></span>|@TableType|<span data-ttu-id="99935-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="99935-122">TABLE_TYPE</span></span>|<span data-ttu-id="99935-123">4</span><span class="sxs-lookup"><span data-stu-id="99935-123">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="99935-124">Especificación de los valores de restricción</span><span class="sxs-lookup"><span data-stu-id="99935-124">Specifying Restriction Values</span></span>  

 <span data-ttu-id="99935-125">Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.</span><span class="sxs-lookup"><span data-stu-id="99935-125">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="99935-126">Por ejemplo, para restringir las tablas devueltas por el método **GetSchema** solo a las del esquema "Sales", establezca el segundo elemento de la matriz en "Sales" antes de pasarlo al método **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="99935-126">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99935-127">Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.</span><span class="sxs-lookup"><span data-stu-id="99935-127">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="99935-128">La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.</span><span class="sxs-lookup"><span data-stu-id="99935-128">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="99935-129">Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.</span><span class="sxs-lookup"><span data-stu-id="99935-129">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99935-130">El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="99935-130">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="99935-131">Puede haber un número de restricciones inferior al máximo.</span><span class="sxs-lookup"><span data-stu-id="99935-131">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="99935-132">Se supone que las restricciones que faltan serán nulas (sin restricciones).</span><span class="sxs-lookup"><span data-stu-id="99935-132">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="99935-133">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas llamando al método **GetSchema** con el nombre de la colección de esquemas de restricciones, que es "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="99935-133">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="99935-134">Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.</span><span class="sxs-lookup"><span data-stu-id="99935-134">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="99935-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99935-135">Example</span></span>  

 <span data-ttu-id="99935-136">En los siguientes ejemplos se muestra cómo utilizar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos .NET Framework para la <xref:System.Data.SqlClient.SqlConnection> clase SQL Server para recuperar información de esquema de todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks** , y para restringir la información devuelta solo a las tablas del esquema "sales":</span><span class="sxs-lookup"><span data-stu-id="99935-136">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="99935-137">Restricciones de esquema de SQL Server</span><span class="sxs-lookup"><span data-stu-id="99935-137">SQL Server Schema Restrictions</span></span>  

 <span data-ttu-id="99935-138">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99935-138">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="99935-139">Usuarios</span><span class="sxs-lookup"><span data-stu-id="99935-139">Users</span></span>  
  
|<span data-ttu-id="99935-140">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-140">Restriction Name</span></span>|<span data-ttu-id="99935-141">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-141">Parameter Name</span></span>|<span data-ttu-id="99935-142">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-142">Restriction Default</span></span>|<span data-ttu-id="99935-143">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-143">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-144">User_Name</span><span class="sxs-lookup"><span data-stu-id="99935-144">User_Name</span></span>|@Name|<span data-ttu-id="99935-145">name</span><span class="sxs-lookup"><span data-stu-id="99935-145">name</span></span>|<span data-ttu-id="99935-146">1</span><span class="sxs-lookup"><span data-stu-id="99935-146">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="99935-147">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="99935-147">Databases</span></span>  
  
|<span data-ttu-id="99935-148">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-148">Restriction Name</span></span>|<span data-ttu-id="99935-149">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-149">Parameter Name</span></span>|<span data-ttu-id="99935-150">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-150">Restriction Default</span></span>|<span data-ttu-id="99935-151">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-151">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-152">Nombre</span><span class="sxs-lookup"><span data-stu-id="99935-152">Name</span></span>|@Name|<span data-ttu-id="99935-153">Nombre</span><span class="sxs-lookup"><span data-stu-id="99935-153">Name</span></span>|<span data-ttu-id="99935-154">1</span><span class="sxs-lookup"><span data-stu-id="99935-154">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="99935-155">Tablas</span><span class="sxs-lookup"><span data-stu-id="99935-155">Tables</span></span>  
  
|<span data-ttu-id="99935-156">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-156">Restriction Name</span></span>|<span data-ttu-id="99935-157">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-157">Parameter Name</span></span>|<span data-ttu-id="99935-158">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-158">Restriction Default</span></span>|<span data-ttu-id="99935-159">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-159">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-160">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-160">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-161">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-161">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-162">1</span><span class="sxs-lookup"><span data-stu-id="99935-162">1</span></span>|  
|<span data-ttu-id="99935-163">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-163">Owner</span></span>|@Owner|<span data-ttu-id="99935-164">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-164">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-165">2</span><span class="sxs-lookup"><span data-stu-id="99935-165">2</span></span>|  
|<span data-ttu-id="99935-166">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-166">Table</span></span>|@Name|<span data-ttu-id="99935-167">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-167">TABLE_NAME</span></span>|<span data-ttu-id="99935-168">3</span><span class="sxs-lookup"><span data-stu-id="99935-168">3</span></span>|  
|<span data-ttu-id="99935-169">TableType</span><span class="sxs-lookup"><span data-stu-id="99935-169">TableType</span></span>|@TableType|<span data-ttu-id="99935-170">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="99935-170">TABLE_TYPE</span></span>|<span data-ttu-id="99935-171">4</span><span class="sxs-lookup"><span data-stu-id="99935-171">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="99935-172">Columnas</span><span class="sxs-lookup"><span data-stu-id="99935-172">Columns</span></span>  
  
|<span data-ttu-id="99935-173">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-173">Restriction Name</span></span>|<span data-ttu-id="99935-174">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-174">Parameter Name</span></span>|<span data-ttu-id="99935-175">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-175">Restriction Default</span></span>|<span data-ttu-id="99935-176">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-176">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-177">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-177">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-178">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-178">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-179">1</span><span class="sxs-lookup"><span data-stu-id="99935-179">1</span></span>|  
|<span data-ttu-id="99935-180">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-180">Owner</span></span>|@Owner|<span data-ttu-id="99935-181">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-181">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-182">2</span><span class="sxs-lookup"><span data-stu-id="99935-182">2</span></span>|  
|<span data-ttu-id="99935-183">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-183">Table</span></span>|@Table|<span data-ttu-id="99935-184">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-184">TABLE_NAME</span></span>|<span data-ttu-id="99935-185">3</span><span class="sxs-lookup"><span data-stu-id="99935-185">3</span></span>|  
|<span data-ttu-id="99935-186">Columna</span><span class="sxs-lookup"><span data-stu-id="99935-186">Column</span></span>|@Column|<span data-ttu-id="99935-187">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-187">COLUMN_NAME</span></span>|<span data-ttu-id="99935-188">4</span><span class="sxs-lookup"><span data-stu-id="99935-188">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="99935-189">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="99935-189">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="99935-190">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-190">Restriction Name</span></span>|<span data-ttu-id="99935-191">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-191">Parameter Name</span></span>|<span data-ttu-id="99935-192">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-192">Restriction Default</span></span>|<span data-ttu-id="99935-193">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-193">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-194">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-194">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-195">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-195">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-196">1</span><span class="sxs-lookup"><span data-stu-id="99935-196">1</span></span>|  
|<span data-ttu-id="99935-197">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-197">Owner</span></span>|@Owner|<span data-ttu-id="99935-198">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-198">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-199">2</span><span class="sxs-lookup"><span data-stu-id="99935-199">2</span></span>|  
|<span data-ttu-id="99935-200">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-200">Table</span></span>|@Table|<span data-ttu-id="99935-201">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-201">TABLE_NAME</span></span>|<span data-ttu-id="99935-202">3</span><span class="sxs-lookup"><span data-stu-id="99935-202">3</span></span>|  
|<span data-ttu-id="99935-203">Columna</span><span class="sxs-lookup"><span data-stu-id="99935-203">Column</span></span>|@Column|<span data-ttu-id="99935-204">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-204">COLUMN_NAME</span></span>|<span data-ttu-id="99935-205">4</span><span class="sxs-lookup"><span data-stu-id="99935-205">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="99935-206">Vistas</span><span class="sxs-lookup"><span data-stu-id="99935-206">Views</span></span>  
  
|<span data-ttu-id="99935-207">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-207">Restriction Name</span></span>|<span data-ttu-id="99935-208">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-208">Parameter Name</span></span>|<span data-ttu-id="99935-209">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-209">Restriction Default</span></span>|<span data-ttu-id="99935-210">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-210">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-211">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-211">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-212">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-212">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-213">1</span><span class="sxs-lookup"><span data-stu-id="99935-213">1</span></span>|  
|<span data-ttu-id="99935-214">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-214">Owner</span></span>|@Owner|<span data-ttu-id="99935-215">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-215">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-216">2</span><span class="sxs-lookup"><span data-stu-id="99935-216">2</span></span>|  
|<span data-ttu-id="99935-217">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-217">Table</span></span>|@Table|<span data-ttu-id="99935-218">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-218">TABLE_NAME</span></span>|<span data-ttu-id="99935-219">3</span><span class="sxs-lookup"><span data-stu-id="99935-219">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="99935-220">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="99935-220">ViewColumns</span></span>  
  
|<span data-ttu-id="99935-221">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-221">Restriction Name</span></span>|<span data-ttu-id="99935-222">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-222">Parameter Name</span></span>|<span data-ttu-id="99935-223">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-223">Restriction Default</span></span>|<span data-ttu-id="99935-224">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-224">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-225">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-225">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-226">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-226">VIEW_CATALOG</span></span>|<span data-ttu-id="99935-227">1</span><span class="sxs-lookup"><span data-stu-id="99935-227">1</span></span>|  
|<span data-ttu-id="99935-228">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-228">Owner</span></span>|@Owner|<span data-ttu-id="99935-229">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-229">VIEW_SCHEMA</span></span>|<span data-ttu-id="99935-230">2</span><span class="sxs-lookup"><span data-stu-id="99935-230">2</span></span>|  
|<span data-ttu-id="99935-231">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-231">Table</span></span>|@Table|<span data-ttu-id="99935-232">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-232">VIEW_NAME</span></span>|<span data-ttu-id="99935-233">3</span><span class="sxs-lookup"><span data-stu-id="99935-233">3</span></span>|  
|<span data-ttu-id="99935-234">Columna</span><span class="sxs-lookup"><span data-stu-id="99935-234">Column</span></span>|@Column|<span data-ttu-id="99935-235">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-235">COLUMN_NAME</span></span>|<span data-ttu-id="99935-236">4</span><span class="sxs-lookup"><span data-stu-id="99935-236">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="99935-237">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="99935-237">ProcedureParameters</span></span>  
  
|<span data-ttu-id="99935-238">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-238">Restriction Name</span></span>|<span data-ttu-id="99935-239">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-239">Parameter Name</span></span>|<span data-ttu-id="99935-240">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-240">Restriction Default</span></span>|<span data-ttu-id="99935-241">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-241">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-242">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-242">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-243">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-243">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="99935-244">1</span><span class="sxs-lookup"><span data-stu-id="99935-244">1</span></span>|  
|<span data-ttu-id="99935-245">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-245">Owner</span></span>|@Owner|<span data-ttu-id="99935-246">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-246">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="99935-247">2</span><span class="sxs-lookup"><span data-stu-id="99935-247">2</span></span>|  
|<span data-ttu-id="99935-248">Nombre</span><span class="sxs-lookup"><span data-stu-id="99935-248">Name</span></span>|@Name|<span data-ttu-id="99935-249">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-249">SPECIFIC_NAME</span></span>|<span data-ttu-id="99935-250">3</span><span class="sxs-lookup"><span data-stu-id="99935-250">3</span></span>|  
|<span data-ttu-id="99935-251">Parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-251">Parameter</span></span>|@Parameter|<span data-ttu-id="99935-252">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-252">PARAMETER_NAME</span></span>|<span data-ttu-id="99935-253">4</span><span class="sxs-lookup"><span data-stu-id="99935-253">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="99935-254">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="99935-254">Procedures</span></span>  
  
|<span data-ttu-id="99935-255">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-255">Restriction Name</span></span>|<span data-ttu-id="99935-256">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-256">Parameter Name</span></span>|<span data-ttu-id="99935-257">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-257">Restriction Default</span></span>|<span data-ttu-id="99935-258">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-258">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-259">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-259">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-260">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-260">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="99935-261">1</span><span class="sxs-lookup"><span data-stu-id="99935-261">1</span></span>|  
|<span data-ttu-id="99935-262">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-262">Owner</span></span>|@Owner|<span data-ttu-id="99935-263">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-263">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="99935-264">2</span><span class="sxs-lookup"><span data-stu-id="99935-264">2</span></span>|  
|<span data-ttu-id="99935-265">Nombre</span><span class="sxs-lookup"><span data-stu-id="99935-265">Name</span></span>|@Name|<span data-ttu-id="99935-266">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-266">SPECIFIC_NAME</span></span>|<span data-ttu-id="99935-267">3</span><span class="sxs-lookup"><span data-stu-id="99935-267">3</span></span>|  
|<span data-ttu-id="99935-268">Tipo</span><span class="sxs-lookup"><span data-stu-id="99935-268">Type</span></span>|@Type|<span data-ttu-id="99935-269">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="99935-269">ROUTINE_TYPE</span></span>|<span data-ttu-id="99935-270">4</span><span class="sxs-lookup"><span data-stu-id="99935-270">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="99935-271">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="99935-271">IndexColumns</span></span>  
  
|<span data-ttu-id="99935-272">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-272">Restriction Name</span></span>|<span data-ttu-id="99935-273">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-273">Parameter Name</span></span>|<span data-ttu-id="99935-274">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-274">Restriction Default</span></span>|<span data-ttu-id="99935-275">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-275">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-276">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-276">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-277">db_name()</span><span class="sxs-lookup"><span data-stu-id="99935-277">db_name()</span></span>|<span data-ttu-id="99935-278">1</span><span class="sxs-lookup"><span data-stu-id="99935-278">1</span></span>|  
|<span data-ttu-id="99935-279">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-279">Owner</span></span>|@Owner|<span data-ttu-id="99935-280">user_name()</span><span class="sxs-lookup"><span data-stu-id="99935-280">user_name()</span></span>|<span data-ttu-id="99935-281">2</span><span class="sxs-lookup"><span data-stu-id="99935-281">2</span></span>|  
|<span data-ttu-id="99935-282">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-282">Table</span></span>|@Table|<span data-ttu-id="99935-283">o.name</span><span class="sxs-lookup"><span data-stu-id="99935-283">o.name</span></span>|<span data-ttu-id="99935-284">3</span><span class="sxs-lookup"><span data-stu-id="99935-284">3</span></span>|  
|<span data-ttu-id="99935-285">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="99935-285">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="99935-286">x.name</span><span class="sxs-lookup"><span data-stu-id="99935-286">x.name</span></span>|<span data-ttu-id="99935-287">4</span><span class="sxs-lookup"><span data-stu-id="99935-287">4</span></span>|  
|<span data-ttu-id="99935-288">Columna</span><span class="sxs-lookup"><span data-stu-id="99935-288">Column</span></span>|@Column|<span data-ttu-id="99935-289">c.name</span><span class="sxs-lookup"><span data-stu-id="99935-289">c.name</span></span>|<span data-ttu-id="99935-290">5</span><span class="sxs-lookup"><span data-stu-id="99935-290">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="99935-291">Índices</span><span class="sxs-lookup"><span data-stu-id="99935-291">Indexes</span></span>  
  
|<span data-ttu-id="99935-292">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-292">Restriction Name</span></span>|<span data-ttu-id="99935-293">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-293">Parameter Name</span></span>|<span data-ttu-id="99935-294">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-294">Restriction Default</span></span>|<span data-ttu-id="99935-295">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-295">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-296">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-296">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-297">db_name()</span><span class="sxs-lookup"><span data-stu-id="99935-297">db_name()</span></span>|<span data-ttu-id="99935-298">1</span><span class="sxs-lookup"><span data-stu-id="99935-298">1</span></span>|  
|<span data-ttu-id="99935-299">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-299">Owner</span></span>|@Owner|<span data-ttu-id="99935-300">user_name()</span><span class="sxs-lookup"><span data-stu-id="99935-300">user_name()</span></span>|<span data-ttu-id="99935-301">2</span><span class="sxs-lookup"><span data-stu-id="99935-301">2</span></span>|  
|<span data-ttu-id="99935-302">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-302">Table</span></span>|@Table|<span data-ttu-id="99935-303">o.name</span><span class="sxs-lookup"><span data-stu-id="99935-303">o.name</span></span>|<span data-ttu-id="99935-304">3</span><span class="sxs-lookup"><span data-stu-id="99935-304">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="99935-305">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="99935-305">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="99935-306">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-306">Restriction Name</span></span>|<span data-ttu-id="99935-307">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-307">Parameter Name</span></span>|<span data-ttu-id="99935-308">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-308">Restriction Default</span></span>|<span data-ttu-id="99935-309">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-309">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-310">assembly_name</span><span class="sxs-lookup"><span data-stu-id="99935-310">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="99935-311">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="99935-311">assemblies.name</span></span>|<span data-ttu-id="99935-312">1</span><span class="sxs-lookup"><span data-stu-id="99935-312">1</span></span>|  
|<span data-ttu-id="99935-313">udt_name</span><span class="sxs-lookup"><span data-stu-id="99935-313">udt_name</span></span>|@UDTName|<span data-ttu-id="99935-314">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="99935-314">types.assembly_class</span></span>|<span data-ttu-id="99935-315">2</span><span class="sxs-lookup"><span data-stu-id="99935-315">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="99935-316">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="99935-316">ForeignKeys</span></span>  
  
|<span data-ttu-id="99935-317">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-317">Restriction Name</span></span>|<span data-ttu-id="99935-318">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-318">Parameter Name</span></span>|<span data-ttu-id="99935-319">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-319">Restriction Default</span></span>|<span data-ttu-id="99935-320">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-320">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-321">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-321">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-322">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-322">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="99935-323">1</span><span class="sxs-lookup"><span data-stu-id="99935-323">1</span></span>|  
|<span data-ttu-id="99935-324">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-324">Owner</span></span>|@Owner|<span data-ttu-id="99935-325">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-325">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="99935-326">2</span><span class="sxs-lookup"><span data-stu-id="99935-326">2</span></span>|  
|<span data-ttu-id="99935-327">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-327">Table</span></span>|@Table|<span data-ttu-id="99935-328">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-328">TABLE_NAME</span></span>|<span data-ttu-id="99935-329">3</span><span class="sxs-lookup"><span data-stu-id="99935-329">3</span></span>|  
|<span data-ttu-id="99935-330">Nombre</span><span class="sxs-lookup"><span data-stu-id="99935-330">Name</span></span>|@Name|<span data-ttu-id="99935-331">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-331">CONSTRAINT_NAME</span></span>|<span data-ttu-id="99935-332">4</span><span class="sxs-lookup"><span data-stu-id="99935-332">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="99935-333">Restricciones de esquema de SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="99935-333">SQL Server 2008 Schema Restrictions</span></span>  

 <span data-ttu-id="99935-334">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="99935-334">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="99935-335">Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="99935-335">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="99935-336">No se admiten en versiones anteriores de .NET Framework y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99935-336">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="99935-337">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="99935-337">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="99935-338">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-338">Restriction Name</span></span>|<span data-ttu-id="99935-339">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-339">Parameter Name</span></span>|<span data-ttu-id="99935-340">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-340">Restriction Default</span></span>|<span data-ttu-id="99935-341">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-341">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-342">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-342">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-343">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-343">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-344">1</span><span class="sxs-lookup"><span data-stu-id="99935-344">1</span></span>|  
|<span data-ttu-id="99935-345">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-345">Owner</span></span>|@Owner|<span data-ttu-id="99935-346">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-346">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-347">2</span><span class="sxs-lookup"><span data-stu-id="99935-347">2</span></span>|  
|<span data-ttu-id="99935-348">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-348">Table</span></span>|@Table|<span data-ttu-id="99935-349">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-349">TABLE_NAME</span></span>|<span data-ttu-id="99935-350">3</span><span class="sxs-lookup"><span data-stu-id="99935-350">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="99935-351">AllColumns</span><span class="sxs-lookup"><span data-stu-id="99935-351">AllColumns</span></span>  
  
|<span data-ttu-id="99935-352">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-352">Restriction Name</span></span>|<span data-ttu-id="99935-353">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="99935-353">Parameter Name</span></span>|<span data-ttu-id="99935-354">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="99935-354">Restriction Default</span></span>|<span data-ttu-id="99935-355">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="99935-355">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="99935-356">Catálogo</span><span class="sxs-lookup"><span data-stu-id="99935-356">Catalog</span></span>|@Catalog|<span data-ttu-id="99935-357">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="99935-357">TABLE_CATALOG</span></span>|<span data-ttu-id="99935-358">1</span><span class="sxs-lookup"><span data-stu-id="99935-358">1</span></span>|  
|<span data-ttu-id="99935-359">Propietario</span><span class="sxs-lookup"><span data-stu-id="99935-359">Owner</span></span>|@Owner|<span data-ttu-id="99935-360">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="99935-360">TABLE_SCHEMA</span></span>|<span data-ttu-id="99935-361">2</span><span class="sxs-lookup"><span data-stu-id="99935-361">2</span></span>|  
|<span data-ttu-id="99935-362">Tabla</span><span class="sxs-lookup"><span data-stu-id="99935-362">Table</span></span>|@Table|<span data-ttu-id="99935-363">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-363">TABLE_NAME</span></span>|<span data-ttu-id="99935-364">3</span><span class="sxs-lookup"><span data-stu-id="99935-364">3</span></span>|  
|<span data-ttu-id="99935-365">Columna</span><span class="sxs-lookup"><span data-stu-id="99935-365">Column</span></span>|@Column|<span data-ttu-id="99935-366">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="99935-366">COLUMN_NAME</span></span>|<span data-ttu-id="99935-367">4</span><span class="sxs-lookup"><span data-stu-id="99935-367">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99935-368">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99935-368">See also</span></span>

- [<span data-ttu-id="99935-369">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99935-369">ADO.NET Overview</span></span>](ado-net-overview.md)
