---
title: "C&#243;mo: Mostrar los formatos de datos en un objeto de datos | Microsoft Docs"
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
  - "formatos de datos [WPF], mostrar"
  - "DataFormats (clase) [WPF]"
  - "arrastrar y colocar [WPF], mostrar formatos de datos"
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Mostrar los formatos de datos en un objeto de datos
En los ejemplos siguientes se muestra cómo utilizar las sobrecargas del método <xref:System.Windows.DataObject.GetFormats%2A> para obtener una matriz de cadenas que representan cada formato de datos que está disponible en un objeto de datos.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se utiliza la sobrecarga de <xref:System.Windows.DataObject.GetFormats%2A> para obtener una matriz de cadenas que representan todos los formatos de datos disponibles en un objeto de datos \(tanto nativos como autoconvertibles\).  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se utiliza la sobrecarga de <xref:System.Windows.DataObject.GetFormats%2A> para obtener una matriz de cadenas que representan únicamente los formatos de datos disponibles en un objeto de datos \(se filtran los formatos de datos autoconvertibles\).  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## Vea también  
 <xref:System.Windows.IDataObject>   
 [Información general sobre la función de arrastrar y colocar](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)