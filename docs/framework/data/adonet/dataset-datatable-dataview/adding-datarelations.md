---
title: Agregar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: fde1e2ace09e31234d199876ae7f063e01e7a7e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203971"
---
# <a name="adding-datarelations"></a><span data-ttu-id="db665-102">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="db665-102">Adding DataRelations</span></span>
<span data-ttu-id="db665-103">En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="db665-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="db665-104">Los argumentos necesarios para crear una **DataRelation** son un nombre para la **DataRelation** que se va a crear y una matriz de una o varias <xref:System.Data.DataColumn> referencias a las columnas que actúan como columnas primarias y secundarias de la relación.</span><span class="sxs-lookup"><span data-stu-id="db665-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="db665-105">Después de crear una **DataRelation**, puede usarla para desplazarse entre las tablas y recuperar los valores.</span><span class="sxs-lookup"><span data-stu-id="db665-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="db665-106">Agregar una **DataRelation** a <xref:System.Data.DataSet> agrega, <xref:System.Data.UniqueConstraint> de forma predeterminada, a la tabla primaria y <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="db665-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="db665-107">Para obtener más información sobre estas restricciones predeterminadas, consulte [restricciones de DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="db665-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="db665-108">En el ejemplo de código siguiente se crea una DataRelation <xref:System.Data.DataTable> con dos objetos <xref:System.Data.DataSet>en un.</span><span class="sxs-lookup"><span data-stu-id="db665-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="db665-109">Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos.</span><span class="sxs-lookup"><span data-stu-id="db665-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="db665-110">En el ejemplo se agrega una única **DataRelation** a la <xref:System.Data.DataSet>colección Relations de.</span><span class="sxs-lookup"><span data-stu-id="db665-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="db665-111">El primer argumento del ejemplo especifica el nombre de la **DataRelation** que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="db665-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="db665-112">El segundo argumento establece la **DataColumn** primaria y el tercer argumento establece la **DataColumn**secundaria.</span><span class="sxs-lookup"><span data-stu-id="db665-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="db665-113">Una **DataRelation** también tiene una propiedad **anidada** que, cuando se establece en **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria cuando se escriben como elementos <xref:System.Data.DataSet.WriteXml%2A> XML mediante.</span><span class="sxs-lookup"><span data-stu-id="db665-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="db665-114">Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).</span><span class="sxs-lookup"><span data-stu-id="db665-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db665-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="db665-115">See also</span></span>

- [<span data-ttu-id="db665-116">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="db665-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="db665-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="db665-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
