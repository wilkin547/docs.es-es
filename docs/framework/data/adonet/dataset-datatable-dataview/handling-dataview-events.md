---
title: Controlar eventos de DataView
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
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1f12dc41421090615e640fac4cc7bfb0fa08bb00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="handling-dataview-events"></a><span data-ttu-id="191f2-102">Controlar eventos de DataView</span><span class="sxs-lookup"><span data-stu-id="191f2-102">Handling DataView Events</span></span>
<span data-ttu-id="191f2-103">Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista.</span><span class="sxs-lookup"><span data-stu-id="191f2-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="191f2-104">Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria.</span><span class="sxs-lookup"><span data-stu-id="191f2-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="191f2-105">El **ListChanged** evento también le notifica si la lista de filas que está viendo ha cambiado considerablemente por la aplicación de un nuevo criterio de ordenación o un filtro.</span><span class="sxs-lookup"><span data-stu-id="191f2-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="191f2-106">El **ListChanged** evento implementa la **ListChangedEventHandler** delegado de la <xref:System.ComponentModel> espacio de nombres y toma como entrada un <xref:System.ComponentModel.ListChangedEventArgs> objeto.</span><span class="sxs-lookup"><span data-stu-id="191f2-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="191f2-107">Puede determinar qué tipo de cambio producido mediante el <xref:System.ComponentModel.ListChangedType> valor de enumeración en el **ListChangedType** propiedad de la **ListChangedEventArgs** objeto.</span><span class="sxs-lookup"><span data-stu-id="191f2-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="191f2-108">Para los cambios que implican agregar, eliminar o mover filas, el nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada son accesibles mediante la **NewIndex** propiedad de la **ListChangedEventArgs** objeto.</span><span class="sxs-lookup"><span data-stu-id="191f2-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="191f2-109">En el caso de una fila movida, al índice anterior de la fila movida son accesibles mediante la **OldIndex** propiedad de la **ListChangedEventArgs** objeto.</span><span class="sxs-lookup"><span data-stu-id="191f2-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="191f2-110">El **DataViewManager** también expone un **ListChanged** evento para notificarle si se ha agregado o quitado una tabla, o si se ha realizado un cambio en el **relaciones** colección de la subyacente **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="191f2-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="191f2-111">En el ejemplo de código siguiente se muestra cómo agregar un **ListChanged** controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="191f2-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="191f2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="191f2-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="191f2-113">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="191f2-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="191f2-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="191f2-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
