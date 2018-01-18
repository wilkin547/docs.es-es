---
title: Crear un objeto DataTable
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 94fa5507d71fef557baadc6ee8979efeee4acf40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable"></a><span data-ttu-id="db068-102">Crear un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="db068-102">Creating a DataTable</span></span>
<span data-ttu-id="db068-103">Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="db068-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="db068-104">Puede crear un **DataTable** objeto mediante el uso adecuado **DataTable** constructor.</span><span class="sxs-lookup"><span data-stu-id="db068-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="db068-105">Puede agregarlo a la **conjunto de datos** mediante el uso de la **agregar** método para agregarlo a la **DataTable** del objeto **tablas** colección.</span><span class="sxs-lookup"><span data-stu-id="db068-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="db068-106">También puede crear **DataTable** objetos dentro de un **conjunto de datos** mediante el uso de la **rellenar** o **FillSchema** métodos de la  **DataAdapter** objeto, o desde un predefinido o deducido esquema XML con el **ReadXml**, **ReadXmlSchema**, o **InferXmlSchema** métodos de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="db068-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="db068-107">Tenga en cuenta que, después de haber agregado un **DataTable** como un miembro de la **tablas** colección de un **conjunto de datos**, no se puede agregar a la colección de tablas de ningún otro **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="db068-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="db068-108">Cuando crea un **DataTable**, no tiene un esquema (es decir, una estructura).</span><span class="sxs-lookup"><span data-stu-id="db068-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="db068-109">Para definir el esquema de la tabla, debe crear y agregar <xref:System.Data.DataColumn> objetos a la **columnas** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="db068-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="db068-110">También puede definir una columna de clave principal para la tabla y crear y agregar **restricción** objetos a la **restricciones** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="db068-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="db068-111">Después de haber definido el esquema para un **DataTable**, puede agregar filas de datos a la tabla agregando **DataRow** objetos a la **filas** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="db068-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="db068-112">No se debe proporcionar un valor para el <xref:System.Data.DataTable.TableName%2A> propiedad cuando se crea un **DataTable**; puede especificar la propiedad en otro momento, o puede dejar vacío.</span><span class="sxs-lookup"><span data-stu-id="db068-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="db068-113">Sin embargo, cuando se agrega una tabla sin un **TableName** valor a un **conjunto de datos**, la tabla recibirá un nombre predeterminado incremental de tabla*N*, comenzando por "Table" para Table0.</span><span class="sxs-lookup"><span data-stu-id="db068-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db068-114">Se recomienda evitar la "tabla*N*" convención de nomenclatura al proporcionar un **TableName** valor, porque el nombre proporcionado puede entrar en conflicto con un nombre de tabla predeterminado existente en el **conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="db068-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="db068-115">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="db068-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="db068-116">En el ejemplo siguiente se crea una instancia de un **DataTable** objeto y le asigna el nombre "Customers".</span><span class="sxs-lookup"><span data-stu-id="db068-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="db068-117">En el ejemplo siguiente se crea una instancia de un **DataTable** agregándolo a la **tablas** colección de un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="db068-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="db068-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="db068-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="db068-119">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="db068-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="db068-120">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="db068-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="db068-121">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="db068-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="db068-122">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="db068-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="db068-123">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="db068-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
