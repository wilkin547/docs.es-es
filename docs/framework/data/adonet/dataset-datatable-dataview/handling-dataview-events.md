---
title: "Tratamiento de eventos DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Tratamiento de eventos DataView
Puede utilizar el evento <xref:System.Data.DataView.ListChanged> de la <xref:System.Data.DataView> para determinar si se ha actualizado una vista.  Entre las actualizaciones que generan el evento se incluyen la agregación de una fila a la tabla subyacente, así como su eliminación o modificación; la agregación de una columna al esquema de la tabla subyacente o su eliminación y la modificación de una relación primaria o secundaria.  El evento **ListChanged** también le notifica si la lista de filas que está viendo ha cambiado considerablemente por la aplicación de un nuevo criterio de ordenación o de un filtro.  
  
 El evento **ListChanged** implementa el delegado **ListChangedEventHandler** del espacio de nombres <xref:System.ComponentModel> y toma como entrada un objeto <xref:System.ComponentModel.ListChangedEventArgs>.  Puede determinar el tipo de cambio producido mediante el valor de enumeración <xref:System.ComponentModel.ListChangedType> en la propiedad **ListChangedType** del objeto **ListChangedEventArgs**.  Para los cambios que implican agregar, eliminar o mover filas, se puede tener acceso al nuevo índice de la fila agregada o movida y al índice anterior de la fila eliminada mediante la propiedad **NewIndex** del objeto **ListChangedEventArgs**.  En el caso de una fila movida, se puede tener acceso al índice anterior de la fila movida mediante la propiedad **OldIndex** del objeto **ListChangedEventArgs**.  
  
 **DataViewManager** también expone un evento **ListChanged** para notificarle si se ha agregado o quitado una tabla, o si se ha realizado un cambio en la colección **Relations** del **DataSet** subyacente.  
  
 En el siguiente ejemplo de código se muestra cómo agregar un controlador de eventos **ListChanged**.  
  
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
  
## Vea también  
 <xref:System.Data.DataView>   
 <xref:System.ComponentModel.ListChangedEventHandler>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)