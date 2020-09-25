---
title: Agregar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202388"
---
# <a name="adding-datarelations"></a><span data-ttu-id="3b864-102">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="3b864-102">Adding DataRelations</span></span>

<span data-ttu-id="3b864-103">En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="3b864-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="3b864-104">Los argumentos necesarios para crear una **DataRelation** son un nombre para la **DataRelation** que se va a crear y una matriz de una o varias <xref:System.Data.DataColumn> referencias a las columnas que actúan como columnas primarias y secundarias de la relación.</span><span class="sxs-lookup"><span data-stu-id="3b864-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="3b864-105">Después de crear una **DataRelation**, puede usarla para desplazarse entre las tablas y recuperar los valores.</span><span class="sxs-lookup"><span data-stu-id="3b864-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="3b864-106">Agregar una **DataRelation** a <xref:System.Data.DataSet> agrega, de forma predeterminada, <xref:System.Data.UniqueConstraint> a la tabla primaria y <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="3b864-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="3b864-107">Para obtener más información sobre estas restricciones predeterminadas, consulte [restricciones de DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="3b864-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="3b864-108">En el ejemplo de código siguiente se crea una **DataRelation** con dos <xref:System.Data.DataTable> objetos en un <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="3b864-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="3b864-109">Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos.</span><span class="sxs-lookup"><span data-stu-id="3b864-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="3b864-110">En el ejemplo se agrega una única **DataRelation** a la colección **Relations** de <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="3b864-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="3b864-111">El primer argumento del ejemplo especifica el nombre de la **DataRelation** que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3b864-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="3b864-112">El segundo argumento establece la **DataColumn** primaria y el tercer argumento establece la **DataColumn**secundaria.</span><span class="sxs-lookup"><span data-stu-id="3b864-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="3b864-113">Una **DataRelation** también tiene una propiedad **anidada** que, cuando se establece en **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria cuando se escriben como elementos XML mediante <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="3b864-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="3b864-114">Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).</span><span class="sxs-lookup"><span data-stu-id="3b864-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b864-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b864-115">See also</span></span>

- [<span data-ttu-id="3b864-116">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="3b864-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="3b864-117">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3b864-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
