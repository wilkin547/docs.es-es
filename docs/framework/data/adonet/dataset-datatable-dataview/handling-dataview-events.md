---
title: Controlar eventos de DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 9e67aef2a39a04adfdcc036c008aa80c9151c14b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762564"
---
# <a name="handling-dataview-events"></a>Controlar eventos de DataView
Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista. Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria. El **ListChanged** evento también le notifica si la lista de filas que está viendo ha cambiado considerablemente por la aplicación de un nuevo criterio de ordenación o un filtro.  
  
 El **ListChanged** evento implementa la **ListChangedEventHandler** delegado de la <xref:System.ComponentModel> espacio de nombres y toma como entrada un <xref:System.ComponentModel.ListChangedEventArgs> objeto. Puede determinar qué tipo de cambio producido mediante el <xref:System.ComponentModel.ListChangedType> valor de enumeración en el **ListChangedType** propiedad de la **ListChangedEventArgs** objeto. Para los cambios que implican agregar, eliminar o mover filas, el nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada son accesibles mediante la **NewIndex** propiedad de la **ListChangedEventArgs** objeto. En el caso de una fila movida, al índice anterior de la fila movida son accesibles mediante la **OldIndex** propiedad de la **ListChangedEventArgs** objeto.  
  
 El **DataViewManager** también expone un **ListChanged** evento para notificarle si se ha agregado o quitado una tabla, o si se ha realizado un cambio en el **relaciones** colección de la subyacente **conjunto de datos**.  
  
 En el ejemplo de código siguiente se muestra cómo agregar un **ListChanged** controlador de eventos.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
