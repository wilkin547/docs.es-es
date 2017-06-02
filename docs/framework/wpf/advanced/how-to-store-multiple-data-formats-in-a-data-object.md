---
title: "C&#243;mo: Almacenar varios formatos de datos en un objeto de datos | Microsoft Docs"
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
  - "DataFormats (clase) [WPF], almacenar varios formatos"
  - "DataObject (clase) [WPF], almacenar varios formatos"
  - "arrastrar y colocar [WPF], almacenar varios formatos"
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Almacenar varios formatos de datos en un objeto de datos
En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> para agregar datos a un objeto de datos en varios formatos.  
  
## Ejemplo  
  
### Descripción  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## Vea también  
 <xref:System.Windows.IDataObject>   
 [Información general sobre la función de arrastrar y colocar](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)