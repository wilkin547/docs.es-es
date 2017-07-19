---
title: "C&#243;mo: Determinar si un formato de datos est&#225; presente en un objeto de datos | Microsoft Docs"
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
  - "formatos de datos [WPF], determinar si existen"
  - "DataFormats (clase) [WPF]"
  - "arrastrar y colocar [WPF], buscar formatos existentes"
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Determinar si un formato de datos est&#225; presente en un objeto de datos
En los ejemplos siguientes se muestra cómo utilizar las diversas sobrecargas del método <xref:System.Windows.DataObject.GetDataPresent%2A> para consultar si un formato de datos determinado se encuentra en un objeto de datos.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente, se usa la sobrecarga del método <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> para consultar la presencia de un formato de datos concreto por cadena del descriptor.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente, se usa la sobrecarga del método <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> para consultar la presencia de un formato de datos concreto por tipo.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente, se usa la sobrecarga del método <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> para consultar los datos por cadena del descriptor y especificar cómo tratar los formatos de datos de autoconversión.  
  
### Código  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## Vea también  
 <xref:System.Windows.IDataObject>