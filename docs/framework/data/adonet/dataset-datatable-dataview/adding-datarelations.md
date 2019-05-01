---
title: Agregar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 9cefc97e571f315a6a644e0a058d4283168ecb9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034528"
---
# <a name="adding-datarelations"></a><span data-ttu-id="0b93f-102">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="0b93f-102">Adding DataRelations</span></span>
<span data-ttu-id="0b93f-103">En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="0b93f-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="0b93f-104">Los argumentos necesarios para crear un **DataRelation** son un nombre para el **DataRelation** va a crear y una matriz de uno o varios <xref:System.Data.DataColumn> referencias a las columnas que actúan como los primarios y secundarios columnas de la relación.</span><span class="sxs-lookup"><span data-stu-id="0b93f-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="0b93f-105">Después de haber creado un **DataRelation**, puede usar para navegar entre las tablas y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="0b93f-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="0b93f-106">Agregar un **DataRelation** a un <xref:System.Data.DataSet> agrega de forma predeterminada, un <xref:System.Data.UniqueConstraint> a la tabla primaria y una <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="0b93f-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="0b93f-107">Para obtener más información acerca de estas restricciones predeterminadas, vea [restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="0b93f-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="0b93f-108">En el ejemplo de código siguiente se crea un **DataRelation** usando dos <xref:System.Data.DataTable> objetos en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0b93f-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0b93f-109">Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos.</span><span class="sxs-lookup"><span data-stu-id="0b93f-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="0b93f-110">El ejemplo agrega una sola **DataRelation** a la **relaciones** colección de la <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0b93f-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0b93f-111">El primer argumento en el ejemplo especifica el nombre de la **DataRelation** va a crear.</span><span class="sxs-lookup"><span data-stu-id="0b93f-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="0b93f-112">El segundo argumento establece el elemento primario **DataColumn** y el tercer argumento establece el elemento secundario **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="0b93f-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="0b93f-113">Un **DataRelation** también tiene un **Nested** propiedad que, cuando se establece en **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria Cuando se escriben como elementos XML mediante <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="0b93f-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="0b93f-114">Para obtener más información, vea [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).</span><span class="sxs-lookup"><span data-stu-id="0b93f-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b93f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b93f-115">See also</span></span>

- [<span data-ttu-id="0b93f-116">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="0b93f-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="0b93f-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0b93f-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
