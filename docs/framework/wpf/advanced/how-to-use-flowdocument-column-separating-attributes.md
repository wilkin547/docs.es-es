---
title: "C&#243;mo: Usar atributos de separaci&#243;n de columnas de FlowDocument | Microsoft Docs"
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
  - "atributos de separación de columnas"
  - "documentos, FlowDocument (atributos de separación de columnas)"
  - "FlowDocument (atributos de separación de columnas)"
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Usar atributos de separaci&#243;n de columnas de FlowDocument
En este ejemplo se muestra cómo utilizar las características de separación de columnas de <xref:System.Windows.Documents.FlowDocument>.  
  
## Ejemplo  
 En el ejemplo siguiente se define un objeto <xref:System.Windows.Documents.FlowDocument> y se establecen los atributos <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>.  <xref:System.Windows.Documents.FlowDocument> contiene un párrafo único de contenido de ejemplo.  
  
 [!code-xml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 En la ilustración siguiente se muestran los efectos de los atributos <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> en un <xref:System.Windows.Documents.FlowDocument> representado.  
  
 ![Captura de pantalla: FlowDocument dentro de columna](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")