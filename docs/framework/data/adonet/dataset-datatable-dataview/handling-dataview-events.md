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
# <a name="handling-dataview-events"></a>Controlar eventos de DataView

Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista. Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria. El evento **ListChanged** también le notifica si la lista de filas que está viendo ha cambiado significativamente debido a la aplicación de un nuevo criterio de ordenación o un filtro.  
  
 El evento **ListChanged** implementa el delegado **ListChangedEventHandler** del espacio de <xref:System.ComponentModel> nombres y toma como entrada un <xref:System.ComponentModel.ListChangedEventArgs> objeto. Puede determinar el tipo de cambio que se ha producido mediante el <xref:System.ComponentModel.ListChangedType> valor de enumeración en la propiedad **ListChangedType** del objeto **ListChangedEventArgs** . En el caso de los cambios que implican agregar, eliminar o mover filas, se puede tener acceso al nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada mediante la propiedad **NewIndex** del objeto **ListChangedEventArgs** . En el caso de una fila movida, se puede tener acceso al índice anterior de la fila movida mediante la propiedad **OldIndex** del objeto **ListChangedEventArgs** .  
  
 El **objeto** **DataViewManager** también expone un evento **ListChanged** para recibir una notificación si se ha agregado o quitado una tabla, o si se ha realizado un cambio en la colección **Relations** del conjunto de objetos subyacente.  
  
 En el ejemplo de código siguiente se muestra cómo agregar un controlador de eventos **ListChanged** .  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [Objetos DataView](dataviews.md)
- [Información general de ADO.NET](../ado-net-overview.md)
