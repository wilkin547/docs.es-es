---
title: "C&#243;mo: Abrir un archivo colocado en un control RichTextBox | Microsoft Docs"
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
  - "arrastrar y colocar [WPF], abrir un archivo eliminado"
  - "arrastrar y colocar [WPF], RichTextBox"
  - "RichTextBox [WPF], arrastrar y colocar"
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Abrir un archivo colocado en un control RichTextBox
En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], todos los controles <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Documents.FlowDocument> tienen funcionalidad de arrastrar y colocar integrada.  La funcionalidad integrada permite arrastrar y colocar texto dentro de los controles y entre ellos.  Sin embargo, no permite abrir un archivo colocando el archivo en el control.  Estos controles también marcan los eventos de arrastrar y colocar como controlados.  Por consiguiente, de forma predeterminada, no se pueden agregar controladores de eventos propios con el fin de proporcionar funcionalidad para abrir archivos colocados.  
  
 Si desea agregar control adicional para los eventos de arrastrar y colocar en estos controles, utilice el método <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> para agregar sus controladores de eventos para los eventos de arrastrar y colocar.  Establezca el parámetro `handledEventsToo` en `true` de modo que el controlador proporcionado se invoque para un evento enrutado ya marcado como controlado por otro elemento a lo largo de la ruta de evento.  
  
> [!TIP]
>  Puede reemplazar la funcionalidad de arrastrar y colocar integrada de <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Documents.FlowDocument> controlando las versiones preliminares de los eventos de arrastrar y colocar y marcando los eventos de vista previa como controlados.  Sin embargo, esto deshabilitará la funcionalidad de arrastrar y colocar integrada, y no se recomienda.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo agregar controladores para los eventos <xref:System.Windows.DragDrop.DragOver> y <xref:System.Windows.DragDrop.Drop> en <xref:System.Windows.Controls.RichTextBox>.  En este ejemplo se utiliza el método <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> y se establece el parámetro `handledEventsToo` en `true` para que se invoque a los controladores de eventos aunque <xref:System.Windows.Controls.RichTextBox> marque estos eventos como controlados.  El código de los controladores de eventos agrega funcionalidad para abrir un archivo de texto que se coloca en <xref:System.Windows.Controls.RichTextBox>.  
  
 Para probar este ejemplo, arrastre un archivo de texto o un archivo con formato de texto enriquecido \(RTF\) del Explorador de Windows a <xref:System.Windows.Controls.RichTextBox>.  El archivo se abrirá en <xref:System.Windows.Controls.RichTextBox>.  Si presiona Mayús antes de colocar el archivo, se abrirá el archivo como texto sin formato.  
  
 [!code-xml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]