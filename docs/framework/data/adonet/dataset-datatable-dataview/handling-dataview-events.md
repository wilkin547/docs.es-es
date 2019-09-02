---
title: Controlar eventos de DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b3a1077bff9bf457b4aef0b05357d4a9260f8973
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204822"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="02bfd-102">Controlar eventos de DataView</span><span class="sxs-lookup"><span data-stu-id="02bfd-102">Handling DataView Events</span></span>
<span data-ttu-id="02bfd-103">Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista.</span><span class="sxs-lookup"><span data-stu-id="02bfd-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="02bfd-104">Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria.</span><span class="sxs-lookup"><span data-stu-id="02bfd-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="02bfd-105">El evento **ListChanged** también le notifica si la lista de filas que está viendo ha cambiado significativamente debido a la aplicación de un nuevo criterio de ordenación o un filtro.</span><span class="sxs-lookup"><span data-stu-id="02bfd-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="02bfd-106">El evento **ListChanged** implementa el <xref:System.ComponentModel> delegado **ListChangedEventHandler** del espacio de nombres y toma como entrada un <xref:System.ComponentModel.ListChangedEventArgs> objeto.</span><span class="sxs-lookup"><span data-stu-id="02bfd-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="02bfd-107">Puede determinar el tipo de cambio que se ha producido mediante <xref:System.ComponentModel.ListChangedType> el valor de enumeración en la propiedad **ListChangedType** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="02bfd-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="02bfd-108">En el caso de los cambios que implican agregar, eliminar o mover filas, se puede tener acceso al nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada mediante la propiedad **NewIndex** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="02bfd-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="02bfd-109">En el caso de una fila movida, se puede tener acceso al índice anterior de la fila movida mediante la propiedad **OldIndex** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="02bfd-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="02bfd-110">El objeto **DataViewManager** también expone un evento **ListChanged** para recibir una notificación si se ha agregado o quitado una tabla, o si se ha realizado un cambio en la colección Relations del **conjunto**de objetos subyacente.</span><span class="sxs-lookup"><span data-stu-id="02bfd-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="02bfd-111">En el ejemplo de código siguiente se muestra cómo agregar un controlador de eventos **ListChanged** .</span><span class="sxs-lookup"><span data-stu-id="02bfd-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02bfd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="02bfd-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="02bfd-113">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="02bfd-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="02bfd-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="02bfd-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
