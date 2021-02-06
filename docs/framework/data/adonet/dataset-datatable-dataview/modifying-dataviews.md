---
description: Más información acerca de cómo modificar las vistas de vista
title: Modificar objetos DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: e0f62c0b8553cd4b83c28da99b8bdec316c8a91d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651839"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="4086d-103">Modificar objetos DataView</span><span class="sxs-lookup"><span data-stu-id="4086d-103">Modifying DataViews</span></span>

<span data-ttu-id="4086d-104">Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="4086d-104">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="4086d-105">La capacidad de usar **DataView** para modificar los datos de la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de **DataView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-105">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="4086d-106">Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="4086d-106">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="4086d-107">Se establecen en **true** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4086d-107">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="4086d-108">Si **AllowNew** es **true**, puede usar el <xref:System.Data.DataView.AddNew%2A> método de **DataView** para crear un nuevo <xref:System.Data.DataRowView> .</span><span class="sxs-lookup"><span data-stu-id="4086d-108">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="4086d-109">Tenga en cuenta que una nueva fila no se agrega realmente al subyacente <xref:System.Data.DataTable> hasta que <xref:System.Data.DataRowView.EndEdit%2A> se llama al método de la **DataRowView** .</span><span class="sxs-lookup"><span data-stu-id="4086d-109">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="4086d-110">Si <xref:System.Data.DataRowView.CancelEdit%2A> se llama al método de la **DataRowView** , se descarta la nueva fila.</span><span class="sxs-lookup"><span data-stu-id="4086d-110">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="4086d-111">Tenga en cuenta también que solo puede editar una **DataRowView** a la vez.</span><span class="sxs-lookup"><span data-stu-id="4086d-111">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="4086d-112">Si llama al método **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente.</span><span class="sxs-lookup"><span data-stu-id="4086d-112">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="4086d-113">Cuando se llama a **EndEdit** , los cambios se aplican a la **DataTable** subyacente y, posteriormente, se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet** o **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="4086d-113">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="4086d-114">Si **AllowNew** es **false**, se produce una excepción si se llama al método **AddNew** de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-114">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="4086d-115">Si **AllowEdit** es **true**, puede modificar el contenido de una **DataRow** a través de la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-115">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="4086d-116">Puede confirmar los cambios en la fila subyacente mediante **DataRowView. EndEdit** o rechazar los cambios mediante **DataRowView. CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="4086d-116">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="4086d-117">Tenga en cuenta que sólo puede modificar una fila cada vez.</span><span class="sxs-lookup"><span data-stu-id="4086d-117">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="4086d-118">Si llama a los métodos **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente.</span><span class="sxs-lookup"><span data-stu-id="4086d-118">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="4086d-119">Cuando se llama a **EndEdit** , los cambios propuestos se colocan en la versión de fila **actual** de la **DataRow** subyacente y, posteriormente, se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet** o **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="4086d-119">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="4086d-120">Si **AllowEdit** es **false**, se produce una excepción si se intenta modificar un valor en **DataView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-120">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="4086d-121">Cuando se edita una **DataRowView** existente, los eventos de la **DataTable** subyacente se seguirán generando con los cambios propuestos.</span><span class="sxs-lookup"><span data-stu-id="4086d-121">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="4086d-122">Tenga en cuenta que si llama a **EndEdit** o **CancelEdit** en la **DataRow** subyacente, los cambios pendientes se aplicarán o cancelarán independientemente de si se llama a **EndEdit** o a **CancelEdit** en la **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-122">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="4086d-123">Si **AllowDelete** es **true**, puede eliminar filas de **DataView** mediante el método **Delete** del objeto **DataView** o **DataRowView** , y las filas se eliminarán de la **DataTable** subyacente.</span><span class="sxs-lookup"><span data-stu-id="4086d-123">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="4086d-124">Más adelante puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4086d-124">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="4086d-125">Si **AllowDelete** es **false**, se produce una excepción si se llama al método **Delete** de **DataView** o **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-125">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="4086d-126">En el ejemplo de código siguiente se deshabilita el uso de **DataView** para eliminar filas y se agrega una nueva fila a la tabla subyacente mediante **DataView**.</span><span class="sxs-lookup"><span data-stu-id="4086d-126">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4086d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4086d-127">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="4086d-128">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="4086d-128">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="4086d-129">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4086d-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
