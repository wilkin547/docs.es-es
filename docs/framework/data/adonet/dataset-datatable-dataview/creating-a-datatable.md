---
title: Crear un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 64ba7a8e6bd6361e14d1f16576e377575b088bbe
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205139"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="d9de6-102">Crear un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="d9de6-102">Creating a DataTable</span></span>
<span data-ttu-id="d9de6-103">Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d9de6-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d9de6-104">Puede crear un objeto **DataTable** mediante el constructor de **DataTable** adecuado.</span><span class="sxs-lookup"><span data-stu-id="d9de6-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="d9de6-105">Puede agregarlo al **conjunto** de objetos mediante el método **Add** para agregarlo a la colección de **tablas** del objeto **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="d9de6-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="d9de6-106">También puede crear objetos **DataTable** dentro de un **conjunto de DataSet** mediante los métodos **Fill** o **FillSchema** del objeto **DataAdapter** o desde un esquema XML predefinido o deducido mediante el **ReadXml**, **ReadXmlSchema** o métodos **InferXmlSchema** del conjunto de **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d9de6-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="d9de6-107">Tenga en cuenta que después de haber agregado un **DataTable** como miembro de la colección tables de un **DataSet**, no puede agregarlo a la colección de tablas de ningún otro **conjunto**de tipos.</span><span class="sxs-lookup"><span data-stu-id="d9de6-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="d9de6-108">La primera vez que se crea un **objeto DataTable**, no tiene un esquema (es decir, una estructura).</span><span class="sxs-lookup"><span data-stu-id="d9de6-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="d9de6-109">Para definir el esquema de la tabla, debe crear y agregar <xref:System.Data.DataColumn> objetos a la colección **Columns** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d9de6-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="d9de6-110">También puede definir una columna de clave principal para la tabla y crear y agregar objetos de **restricción** a la colección **Constraints** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d9de6-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="d9de6-111">Después de haber definido el esquema para un **DataTable**, puede Agregar filas de datos a la tabla agregando objetos **DataRow** a la colección **Rows** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d9de6-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="d9de6-112">No es necesario proporcionar un valor para la <xref:System.Data.DataTable.TableName%2A> propiedad cuando se crea un **objeto DataTable**; puede especificar la propiedad en otro momento o dejarla vacía.</span><span class="sxs-lookup"><span data-stu-id="d9de6-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="d9de6-113">Sin embargo, cuando se agrega una tabla sin un valor **TableName** a un **conjunto**de valores, se asigna a la tabla un nombre predeterminado incremental de la tabla*N*, que empieza por "Table" para Table0.</span><span class="sxs-lookup"><span data-stu-id="d9de6-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9de6-114">Se recomienda evitar la Convención de nomenclatura "Table*N*" al proporcionar un valor **TableName** , ya que el nombre proporcionado puede entrar en conflicto con un nombre de tabla predeterminado existente en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d9de6-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="d9de6-115">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d9de6-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="d9de6-116">En el ejemplo siguiente se crea una instancia de un objeto **DataTable** y se le asigna el nombre "Customers".</span><span class="sxs-lookup"><span data-stu-id="d9de6-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="d9de6-117">En el ejemplo siguiente se crea una instancia de un **objeto DataTable** agregándolo a la colección tables de un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d9de6-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9de6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9de6-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="d9de6-119">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="d9de6-119">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="d9de6-120">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d9de6-120">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="d9de6-121">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="d9de6-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d9de6-122">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="d9de6-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d9de6-123">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="d9de6-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
