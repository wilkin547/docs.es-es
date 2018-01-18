---
title: Modificar objetos DataView
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
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c31f256bb86f007a9d083370d116464607cde236
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="modifying-dataviews"></a><span data-ttu-id="aa4b5-102">Modificar objetos DataView</span><span class="sxs-lookup"><span data-stu-id="aa4b5-102">Modifying DataViews</span></span>
<span data-ttu-id="aa4b5-103">Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="aa4b5-104">La capacidad para usar el **DataView** modificar datos en la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de la **DataView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="aa4b5-105">Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="aa4b5-106">Se establecen al **true** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="aa4b5-107">Si **AllowNew** es **true**, puede usar el <xref:System.Data.DataView.AddNew%2A> método de la **DataView** para crear un nuevo <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="aa4b5-108">Tenga en cuenta que una nueva fila no se agrega realmente a subyacente <xref:System.Data.DataTable> hasta que el <xref:System.Data.DataRowView.EndEdit%2A> método de la **DataRowView** se llama.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="aa4b5-109">Si el <xref:System.Data.DataRowView.CancelEdit%2A> método de la **DataRowView** es llama, se descartará la nueva fila.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="aa4b5-110">Tenga en cuenta también que se puede editar sólo uno **DataRowView** a la vez.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="aa4b5-111">Si se llama a la **AddNew** o **BeginEdit** método de la **DataRowView** mientras hay una fila pendiente, **EndEdit** se llamará implícitamente en el fila pendiente.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="aa4b5-112">Cuando **EndEdit** es llama, los cambios se aplican al subyacente **DataTable** y más tarde se pueden confirmar o rechazar mediante los **AcceptChanges** o  **RejectChanges** métodos de la **DataTable**, **conjunto de datos**, o **DataRow** objeto.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="aa4b5-113">Si **AllowNew** es **false**, se produce una excepción si se llama a la **AddNew** método de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa4b5-114">Si **AllowEdit** es **true**, puede modificar el contenido de un **DataRow** a través de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="aa4b5-115">Puede confirmar los cambios en la fila subyacente mediante **DataRowView.EndEdit** o rechazar los cambios mediante **DataRowView.CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="aa4b5-116">Tenga en cuenta que sólo puede modificar una fila cada vez.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="aa4b5-117">Si se llama a la **AddNew** o **BeginEdit** métodos de la **DataRowView** mientras hay una fila pendiente, **EndEdit** se llamará implícitamente en la fila pendiente.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="aa4b5-118">Cuando **EndEdit** se llama, los cambios propuestos se colocan en la **actual** versión de fila de subyacente **DataRow** y más tarde se pueden confirmar o rechazar mediante los  **AcceptChanges** o **RejectChanges** métodos de la **DataTable**, **conjunto de datos**, o **DataRow** objeto.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="aa4b5-119">Si **AllowEdit** es **false**, se produce una excepción si intenta modificar un valor en el **DataView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="aa4b5-120">Cuando una existente **DataRowView** se está editando, eventos de subyacente **DataTable** seguirán provocándose con los cambios propuestos.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="aa4b5-121">Tenga en cuenta que si se llama a **EndEdit** o **CancelEdit** en subyacente **DataRow**, pendiente cambios se aplicarán o se cancelarán independientemente de si  **EndEdit** o **CancelEdit** se llama en el **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa4b5-122">Si **AllowDelete** es **true**, puede eliminar filas de la **DataView** mediante el uso de la **eliminar** método de la **DataView**  o **DataRowView** objeto y las filas se eliminan de subyacente **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="aa4b5-123">Más tarde puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="aa4b5-124">Si **AllowDelete** es **false**, se produce una excepción si se llama a la **eliminar** método de la **DataView** o  **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="aa4b5-125">En el ejemplo de código siguiente se deshabilita el uso de la **DataView** para eliminar filas y se agrega una nueva fila a la tabla subyacente mediante la **DataView**.</span><span class="sxs-lookup"><span data-stu-id="aa4b5-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa4b5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa4b5-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="aa4b5-127">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="aa4b5-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="aa4b5-128">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="aa4b5-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
