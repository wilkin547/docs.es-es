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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf3b02227de5068a031cedb73269148c7d5262a0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
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
