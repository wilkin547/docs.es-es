---
title: Crear un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d496167b7bce31491402414c43ae0bcdee423b89
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786510"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="95e51-102">Crear un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="95e51-102">Creating a DataSet</span></span>
<span data-ttu-id="95e51-103">Puede crear una instancia de <xref:System.Data.DataSet> llamando al constructor <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="95e51-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="95e51-104">Si lo desea, especifique un nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="95e51-104">Optionally specify a name argument.</span></span> <span data-ttu-id="95e51-105">Si no especifica ningún nombre para el <xref:System.Data.DataSet>, se establecerá el nombre "NewDataSet".</span><span class="sxs-lookup"><span data-stu-id="95e51-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="95e51-106">También es posible crear un nuevo <xref:System.Data.DataSet> basado en un <xref:System.Data.DataSet>existente.</span><span class="sxs-lookup"><span data-stu-id="95e51-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="95e51-107">El nuevo <xref:System.Data.DataSet> puede ser una copia exacta del <xref:System.Data.DataSet> existente; un clon del <xref:System.Data.DataSet> que copia la estructura relacional o el esquema, pero que no contiene ningún dato del <xref:System.Data.DataSet> existente; o un subconjunto del <xref:System.Data.DataSet>, que contiene solamente las filas modificadas del <xref:System.Data.DataSet> existente mediante el método <xref:System.Data.DataSet.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="95e51-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="95e51-108">Para obtener más información, vea [copiar el contenido del conjunto](copying-dataset-contents.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="95e51-108">For more information, see [Copying DataSet Contents](copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="95e51-109">En el siguiente ejemplo de código se muestra cómo construir una instancia de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="95e51-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="95e51-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="95e51-110">See also</span></span>

- [<span data-ttu-id="95e51-111">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="95e51-111">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="95e51-112">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="95e51-112">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="95e51-113">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95e51-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
