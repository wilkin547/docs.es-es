---
title: Controlar eventos de DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 2a67cb040c5d438d17ad91d41e97f24f3166262b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204546"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="1eb04-102">Controlar eventos de DataView</span><span class="sxs-lookup"><span data-stu-id="1eb04-102">Handling DataView Events</span></span>

<span data-ttu-id="1eb04-103">Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista.</span><span class="sxs-lookup"><span data-stu-id="1eb04-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="1eb04-104">Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria.</span><span class="sxs-lookup"><span data-stu-id="1eb04-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="1eb04-105">El evento **ListChanged** también le notifica si la lista de filas que está viendo ha cambiado significativamente debido a la aplicación de un nuevo criterio de ordenación o un filtro.</span><span class="sxs-lookup"><span data-stu-id="1eb04-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="1eb04-106">El evento **ListChanged** implementa el delegado **ListChangedEventHandler** del espacio de <xref:System.ComponentModel> nombres y toma como entrada un <xref:System.ComponentModel.ListChangedEventArgs> objeto.</span><span class="sxs-lookup"><span data-stu-id="1eb04-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="1eb04-107">Puede determinar el tipo de cambio que se ha producido mediante el <xref:System.ComponentModel.ListChangedType> valor de enumeración en la propiedad **ListChangedType** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="1eb04-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="1eb04-108">En el caso de los cambios que implican agregar, eliminar o mover filas, se puede tener acceso al nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada mediante la propiedad **NewIndex** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="1eb04-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="1eb04-109">En el caso de una fila movida, se puede tener acceso al índice anterior de la fila movida mediante la propiedad **OldIndex** del objeto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="1eb04-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="1eb04-110">El **objeto** **DataViewManager** también expone un evento **ListChanged** para recibir una notificación si se ha agregado o quitado una tabla, o si se ha realizado un cambio en la colección **Relations** del conjunto de objetos subyacente.</span><span class="sxs-lookup"><span data-stu-id="1eb04-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="1eb04-111">En el ejemplo de código siguiente se muestra cómo agregar un controlador de eventos **ListChanged** .</span><span class="sxs-lookup"><span data-stu-id="1eb04-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1eb04-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1eb04-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="1eb04-113">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="1eb04-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="1eb04-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1eb04-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
