---
title: "C&#243;mo: Recuperar datos en un formato concreto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataFormats (clase) [WPF], recuperar datos"
  - "DataObject (clase) [WPF], recuperar datos"
  - "arrastrar y colocar [WPF], recuperar datos"
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Recuperar datos en un formato concreto
En los ejemplos siguientes se muestra cómo recuperar datos de un objeto de datos en un formato especificado.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente, se usa la sobrecarga de <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> para comprobar primero si un formato de datos especificado está disponible \(nativamente o de autoconversión\). Si el formato especificado está disponible, en el ejemplo se recuperan los datos mediante el método <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## Ejemplo  
  
### Descripción  
 En el código de ejemplo siguiente, se usa la sobrecarga del método <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> para comprobar primero si un formato de datos especificado está disponible nativamente \(se filtran los formatos de datos de autoconversión\). Si el formato especificado está disponible, en el ejemplo se recuperan los datos mediante el método <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## Vea también  
 <xref:System.Windows.IDataObject>   
 [Información general sobre la función de arrastrar y colocar](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)