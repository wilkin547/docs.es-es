---
title: Restricciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563434"
---
# <a name="schema-restrictions"></a><span data-ttu-id="f2a06-102">Restricciones de esquema</span><span class="sxs-lookup"><span data-stu-id="f2a06-102">Schema Restrictions</span></span>
<span data-ttu-id="f2a06-103">El segundo parámetro opcional de la **GetSchema** método es devuelven las restricciones que se usan para limitar la cantidad de información de esquema y se pasa a la **GetSchema** método como una matriz de cadenas .</span><span class="sxs-lookup"><span data-stu-id="f2a06-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="f2a06-104">La posición en la matriz determina los valores que puede pasar, y es equivalente al número de restricciones.</span><span class="sxs-lookup"><span data-stu-id="f2a06-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="f2a06-105">Por ejemplo, en la tabla siguiente se describen las restricciones que admite la colección de esquemas "Tables" utilizando el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2a06-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="f2a06-106">Las restricciones adicionales para las colecciones de esquemas de SQL Server se muestran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f2a06-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="f2a06-107">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-107">Restriction Name</span></span>|<span data-ttu-id="f2a06-108">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-108">Parameter Name</span></span>|<span data-ttu-id="f2a06-109">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-109">Restriction Default</span></span>|<span data-ttu-id="f2a06-110">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-111">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-111">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-112">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-113">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-113">1</span></span>|  
|<span data-ttu-id="f2a06-114">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-114">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-116">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-116">2</span></span>|  
|<span data-ttu-id="f2a06-117">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-117">Table</span></span>|@Name|<span data-ttu-id="f2a06-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-118">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-119">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-119">3</span></span>|  
|<span data-ttu-id="f2a06-120">TableType</span><span class="sxs-lookup"><span data-stu-id="f2a06-120">TableType</span></span>|@TableType|<span data-ttu-id="f2a06-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f2a06-121">TABLE_TYPE</span></span>|<span data-ttu-id="f2a06-122">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="f2a06-123">Especificación de los valores de restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="f2a06-124">Para utilizar una de las restricciones de la colección de esquemas "Tables", basta con crear una matriz de cadenas con cuatro elementos y, después, colocar un valor en el elemento que coincida con el número de restricción.</span><span class="sxs-lookup"><span data-stu-id="f2a06-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="f2a06-125">Por ejemplo restringir las tablas devuelto por la **GetSchema** método sólo a esas tablas en el esquema "Sales", establezca el segundo elemento de la matriz en "Ventas" antes de pasarlo a la **GetSchema** método.</span><span class="sxs-lookup"><span data-stu-id="f2a06-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a06-126">Las colecciones con restricciones para `SqlClient` y `OracleClient` tienen una columna `ParameterName` adicional.</span><span class="sxs-lookup"><span data-stu-id="f2a06-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="f2a06-127">La columna de valor predeterminado de restricción sigue ahí para la compatibilidad con versiones anteriores, pero actualmente se omite.</span><span class="sxs-lookup"><span data-stu-id="f2a06-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="f2a06-128">Para reducir el riesgo de un ataque de inyección de SQL al especificar valores de restricción, es necesario utilizar consultas parametrizadas en lugar de sustitución de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f2a06-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a06-129">El número de elementos de la matriz debe ser menor o igual que el número de restricciones admitidas en la colección de esquemas especificada o se iniciará una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="f2a06-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="f2a06-130">Puede haber un número de restricciones inferior al máximo.</span><span class="sxs-lookup"><span data-stu-id="f2a06-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="f2a06-131">Se supone que las restricciones que faltan serán nulas (sin restricciones).</span><span class="sxs-lookup"><span data-stu-id="f2a06-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="f2a06-132">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de restricciones admitidas mediante una llamada a la **GetSchema** método con el nombre de la colección de esquemas de restricciones, que es "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="f2a06-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="f2a06-133">Esto devolverá una <xref:System.Data.DataTable> con una lista de los nombres de colecciones, los nombres de restricciones, los valores predeterminados de restricción y los números de restricciones.</span><span class="sxs-lookup"><span data-stu-id="f2a06-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f2a06-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2a06-134">Example</span></span>  
 <span data-ttu-id="f2a06-135">Los ejemplos siguientes muestran cómo usar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos .NET Framework para SQL Server <xref:System.Data.SqlClient.SqlConnection> clase para recuperar información de esquema de todas las tablas contenidas en el **AdventureWorks**base de datos de ejemplo y restringir la información devuelta a sólo las tablas en el esquema "Sales":</span><span class="sxs-lookup"><span data-stu-id="f2a06-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="f2a06-136">Restricciones de esquema de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2a06-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="f2a06-137">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2a06-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="f2a06-138">Usuarios</span><span class="sxs-lookup"><span data-stu-id="f2a06-138">Users</span></span>  
  
|<span data-ttu-id="f2a06-139">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-139">Restriction Name</span></span>|<span data-ttu-id="f2a06-140">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-140">Parameter Name</span></span>|<span data-ttu-id="f2a06-141">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-141">Restriction Default</span></span>|<span data-ttu-id="f2a06-142">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="f2a06-143">User_Name</span></span>|@Name|<span data-ttu-id="f2a06-144">name</span><span class="sxs-lookup"><span data-stu-id="f2a06-144">name</span></span>|<span data-ttu-id="f2a06-145">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="f2a06-146">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="f2a06-146">Databases</span></span>  
  
|<span data-ttu-id="f2a06-147">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-147">Restriction Name</span></span>|<span data-ttu-id="f2a06-148">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-148">Parameter Name</span></span>|<span data-ttu-id="f2a06-149">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-149">Restriction Default</span></span>|<span data-ttu-id="f2a06-150">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-151">nombre</span><span class="sxs-lookup"><span data-stu-id="f2a06-151">Name</span></span>|@Name|<span data-ttu-id="f2a06-152">nombre</span><span class="sxs-lookup"><span data-stu-id="f2a06-152">Name</span></span>|<span data-ttu-id="f2a06-153">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="f2a06-154">Tablas</span><span class="sxs-lookup"><span data-stu-id="f2a06-154">Tables</span></span>  
  
|<span data-ttu-id="f2a06-155">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-155">Restriction Name</span></span>|<span data-ttu-id="f2a06-156">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-156">Parameter Name</span></span>|<span data-ttu-id="f2a06-157">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-157">Restriction Default</span></span>|<span data-ttu-id="f2a06-158">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-159">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-159">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-160">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-161">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-161">1</span></span>|  
|<span data-ttu-id="f2a06-162">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-162">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-164">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-164">2</span></span>|  
|<span data-ttu-id="f2a06-165">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-165">Table</span></span>|@Name|<span data-ttu-id="f2a06-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-166">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-167">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-167">3</span></span>|  
|<span data-ttu-id="f2a06-168">TableType</span><span class="sxs-lookup"><span data-stu-id="f2a06-168">TableType</span></span>|@TableType|<span data-ttu-id="f2a06-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f2a06-169">TABLE_TYPE</span></span>|<span data-ttu-id="f2a06-170">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="f2a06-171">Columnas</span><span class="sxs-lookup"><span data-stu-id="f2a06-171">Columns</span></span>  
  
|<span data-ttu-id="f2a06-172">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-172">Restriction Name</span></span>|<span data-ttu-id="f2a06-173">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-173">Parameter Name</span></span>|<span data-ttu-id="f2a06-174">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-174">Restriction Default</span></span>|<span data-ttu-id="f2a06-175">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-176">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-176">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-177">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-178">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-178">1</span></span>|  
|<span data-ttu-id="f2a06-179">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-179">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-181">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-181">2</span></span>|  
|<span data-ttu-id="f2a06-182">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-182">Table</span></span>|@Table|<span data-ttu-id="f2a06-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-183">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-184">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-184">3</span></span>|  
|<span data-ttu-id="f2a06-185">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a06-185">Column</span></span>|@Column|<span data-ttu-id="f2a06-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-186">COLUMN_NAME</span></span>|<span data-ttu-id="f2a06-187">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="f2a06-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="f2a06-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="f2a06-189">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-189">Restriction Name</span></span>|<span data-ttu-id="f2a06-190">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-190">Parameter Name</span></span>|<span data-ttu-id="f2a06-191">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-191">Restriction Default</span></span>|<span data-ttu-id="f2a06-192">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-193">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-193">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-194">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-195">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-195">1</span></span>|  
|<span data-ttu-id="f2a06-196">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-196">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-198">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-198">2</span></span>|  
|<span data-ttu-id="f2a06-199">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-199">Table</span></span>|@Table|<span data-ttu-id="f2a06-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-200">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-201">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-201">3</span></span>|  
|<span data-ttu-id="f2a06-202">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a06-202">Column</span></span>|@Column|<span data-ttu-id="f2a06-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-203">COLUMN_NAME</span></span>|<span data-ttu-id="f2a06-204">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="f2a06-205">Vistas</span><span class="sxs-lookup"><span data-stu-id="f2a06-205">Views</span></span>  
  
|<span data-ttu-id="f2a06-206">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-206">Restriction Name</span></span>|<span data-ttu-id="f2a06-207">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-207">Parameter Name</span></span>|<span data-ttu-id="f2a06-208">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-208">Restriction Default</span></span>|<span data-ttu-id="f2a06-209">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-210">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-210">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-211">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-212">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-212">1</span></span>|  
|<span data-ttu-id="f2a06-213">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-213">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-215">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-215">2</span></span>|  
|<span data-ttu-id="f2a06-216">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-216">Table</span></span>|@Table|<span data-ttu-id="f2a06-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-217">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-218">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="f2a06-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="f2a06-219">ViewColumns</span></span>  
  
|<span data-ttu-id="f2a06-220">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-220">Restriction Name</span></span>|<span data-ttu-id="f2a06-221">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-221">Parameter Name</span></span>|<span data-ttu-id="f2a06-222">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-222">Restriction Default</span></span>|<span data-ttu-id="f2a06-223">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-224">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-224">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-225">VIEW_CATALOG</span></span>|<span data-ttu-id="f2a06-226">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-226">1</span></span>|  
|<span data-ttu-id="f2a06-227">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-227">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="f2a06-229">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-229">2</span></span>|  
|<span data-ttu-id="f2a06-230">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-230">Table</span></span>|@Table|<span data-ttu-id="f2a06-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-231">VIEW_NAME</span></span>|<span data-ttu-id="f2a06-232">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-232">3</span></span>|  
|<span data-ttu-id="f2a06-233">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a06-233">Column</span></span>|@Column|<span data-ttu-id="f2a06-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-234">COLUMN_NAME</span></span>|<span data-ttu-id="f2a06-235">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="f2a06-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="f2a06-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="f2a06-237">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-237">Restriction Name</span></span>|<span data-ttu-id="f2a06-238">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-238">Parameter Name</span></span>|<span data-ttu-id="f2a06-239">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-239">Restriction Default</span></span>|<span data-ttu-id="f2a06-240">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-241">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-241">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="f2a06-243">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-243">1</span></span>|  
|<span data-ttu-id="f2a06-244">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-244">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="f2a06-246">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-246">2</span></span>|  
|<span data-ttu-id="f2a06-247">nombre</span><span class="sxs-lookup"><span data-stu-id="f2a06-247">Name</span></span>|@Name|<span data-ttu-id="f2a06-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="f2a06-249">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-249">3</span></span>|  
|<span data-ttu-id="f2a06-250">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-250">Parameter</span></span>|@Parameter|<span data-ttu-id="f2a06-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-251">PARAMETER_NAME</span></span>|<span data-ttu-id="f2a06-252">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="f2a06-253">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f2a06-253">Procedures</span></span>  
  
|<span data-ttu-id="f2a06-254">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-254">Restriction Name</span></span>|<span data-ttu-id="f2a06-255">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-255">Parameter Name</span></span>|<span data-ttu-id="f2a06-256">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-256">Restriction Default</span></span>|<span data-ttu-id="f2a06-257">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-258">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="f2a06-260">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-260">1</span></span>|  
|<span data-ttu-id="f2a06-261">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-261">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="f2a06-263">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-263">2</span></span>|  
|<span data-ttu-id="f2a06-264">nombre</span><span class="sxs-lookup"><span data-stu-id="f2a06-264">Name</span></span>|@Name|<span data-ttu-id="f2a06-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="f2a06-266">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-266">3</span></span>|  
|<span data-ttu-id="f2a06-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="f2a06-267">Type</span></span>|@Type|<span data-ttu-id="f2a06-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="f2a06-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="f2a06-269">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="f2a06-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="f2a06-270">IndexColumns</span></span>  
  
|<span data-ttu-id="f2a06-271">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-271">Restriction Name</span></span>|<span data-ttu-id="f2a06-272">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-272">Parameter Name</span></span>|<span data-ttu-id="f2a06-273">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-273">Restriction Default</span></span>|<span data-ttu-id="f2a06-274">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-275">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-275">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="f2a06-276">db_name()</span></span>|<span data-ttu-id="f2a06-277">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-277">1</span></span>|  
|<span data-ttu-id="f2a06-278">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-278">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="f2a06-279">user_name()</span></span>|<span data-ttu-id="f2a06-280">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-280">2</span></span>|  
|<span data-ttu-id="f2a06-281">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-281">Table</span></span>|@Table|<span data-ttu-id="f2a06-282">o.name</span><span class="sxs-lookup"><span data-stu-id="f2a06-282">o.name</span></span>|<span data-ttu-id="f2a06-283">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-283">3</span></span>|  
|<span data-ttu-id="f2a06-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="f2a06-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="f2a06-285">x.name</span><span class="sxs-lookup"><span data-stu-id="f2a06-285">x.name</span></span>|<span data-ttu-id="f2a06-286">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-286">4</span></span>|  
|<span data-ttu-id="f2a06-287">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a06-287">Column</span></span>|@Column|<span data-ttu-id="f2a06-288">c.name</span><span class="sxs-lookup"><span data-stu-id="f2a06-288">c.name</span></span>|<span data-ttu-id="f2a06-289">5</span><span class="sxs-lookup"><span data-stu-id="f2a06-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="f2a06-290">Índices</span><span class="sxs-lookup"><span data-stu-id="f2a06-290">Indexes</span></span>  
  
|<span data-ttu-id="f2a06-291">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-291">Restriction Name</span></span>|<span data-ttu-id="f2a06-292">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-292">Parameter Name</span></span>|<span data-ttu-id="f2a06-293">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-293">Restriction Default</span></span>|<span data-ttu-id="f2a06-294">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-295">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-295">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="f2a06-296">db_name()</span></span>|<span data-ttu-id="f2a06-297">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-297">1</span></span>|  
|<span data-ttu-id="f2a06-298">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-298">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="f2a06-299">user_name()</span></span>|<span data-ttu-id="f2a06-300">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-300">2</span></span>|  
|<span data-ttu-id="f2a06-301">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-301">Table</span></span>|@Table|<span data-ttu-id="f2a06-302">o.name</span><span class="sxs-lookup"><span data-stu-id="f2a06-302">o.name</span></span>|<span data-ttu-id="f2a06-303">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="f2a06-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="f2a06-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="f2a06-305">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-305">Restriction Name</span></span>|<span data-ttu-id="f2a06-306">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-306">Parameter Name</span></span>|<span data-ttu-id="f2a06-307">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-307">Restriction Default</span></span>|<span data-ttu-id="f2a06-308">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="f2a06-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="f2a06-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="f2a06-310">assemblies.name</span></span>|<span data-ttu-id="f2a06-311">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-311">1</span></span>|  
|<span data-ttu-id="f2a06-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="f2a06-312">udt_name</span></span>|@UDTName|<span data-ttu-id="f2a06-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="f2a06-313">types.assembly_class</span></span>|<span data-ttu-id="f2a06-314">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="f2a06-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="f2a06-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="f2a06-316">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-316">Restriction Name</span></span>|<span data-ttu-id="f2a06-317">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-317">Parameter Name</span></span>|<span data-ttu-id="f2a06-318">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-318">Restriction Default</span></span>|<span data-ttu-id="f2a06-319">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-320">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-320">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="f2a06-322">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-322">1</span></span>|  
|<span data-ttu-id="f2a06-323">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-323">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="f2a06-325">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-325">2</span></span>|  
|<span data-ttu-id="f2a06-326">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-326">Table</span></span>|@Table|<span data-ttu-id="f2a06-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-327">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-328">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-328">3</span></span>|  
|<span data-ttu-id="f2a06-329">nombre</span><span class="sxs-lookup"><span data-stu-id="f2a06-329">Name</span></span>|@Name|<span data-ttu-id="f2a06-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="f2a06-331">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="f2a06-332">Restricciones de esquema de SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="f2a06-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="f2a06-333">En la tabla siguiente se muestran las restricciones de las colecciones de esquemas de SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f2a06-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="f2a06-334">Estas restricciones son válidas a partir de la versión 3.5 SP1 de .NET Framework y SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f2a06-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="f2a06-335">No se admiten en versiones anteriores de .NET Framework y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2a06-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="f2a06-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="f2a06-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="f2a06-337">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-337">Restriction Name</span></span>|<span data-ttu-id="f2a06-338">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-338">Parameter Name</span></span>|<span data-ttu-id="f2a06-339">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-339">Restriction Default</span></span>|<span data-ttu-id="f2a06-340">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-341">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-341">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-342">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-343">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-343">1</span></span>|  
|<span data-ttu-id="f2a06-344">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-344">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-346">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-346">2</span></span>|  
|<span data-ttu-id="f2a06-347">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-347">Table</span></span>|@Table|<span data-ttu-id="f2a06-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-348">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-349">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="f2a06-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="f2a06-350">AllColumns</span></span>  
  
|<span data-ttu-id="f2a06-351">Nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-351">Restriction Name</span></span>|<span data-ttu-id="f2a06-352">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="f2a06-352">Parameter Name</span></span>|<span data-ttu-id="f2a06-353">Valor predeterminado de la restricción</span><span class="sxs-lookup"><span data-stu-id="f2a06-353">Restriction Default</span></span>|<span data-ttu-id="f2a06-354">Número de restricciones</span><span class="sxs-lookup"><span data-stu-id="f2a06-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="f2a06-355">Catálogo</span><span class="sxs-lookup"><span data-stu-id="f2a06-355">Catalog</span></span>|@Catalog|<span data-ttu-id="f2a06-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f2a06-356">TABLE_CATALOG</span></span>|<span data-ttu-id="f2a06-357">1</span><span class="sxs-lookup"><span data-stu-id="f2a06-357">1</span></span>|  
|<span data-ttu-id="f2a06-358">Propietario</span><span class="sxs-lookup"><span data-stu-id="f2a06-358">Owner</span></span>|@Owner|<span data-ttu-id="f2a06-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="f2a06-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="f2a06-360">2</span><span class="sxs-lookup"><span data-stu-id="f2a06-360">2</span></span>|  
|<span data-ttu-id="f2a06-361">Tabla</span><span class="sxs-lookup"><span data-stu-id="f2a06-361">Table</span></span>|@Table|<span data-ttu-id="f2a06-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-362">TABLE_NAME</span></span>|<span data-ttu-id="f2a06-363">3</span><span class="sxs-lookup"><span data-stu-id="f2a06-363">3</span></span>|  
|<span data-ttu-id="f2a06-364">Columna</span><span class="sxs-lookup"><span data-stu-id="f2a06-364">Column</span></span>|@Column|<span data-ttu-id="f2a06-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="f2a06-365">COLUMN_NAME</span></span>|<span data-ttu-id="f2a06-366">4</span><span class="sxs-lookup"><span data-stu-id="f2a06-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2a06-367">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2a06-367">See Also</span></span>  
 [<span data-ttu-id="f2a06-368">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f2a06-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
