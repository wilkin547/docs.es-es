---
title: "C&#243;mo: Ajustar el espaciado entre p&#225;rrafos | Microsoft Docs"
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
  - "documentos, ajustar el espaciado entre párrafos"
  - "párrafos, espaciado entre"
  - "espaciado entre párrafos"
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Ajustar el espaciado entre p&#225;rrafos
En este ejemplo se muestra cómo ajustar o eliminar el espaciado entre los párrafos en el contenido dinámico.  
  
 En el contenido dinámico, el espacio adicional que aparece entre los párrafos es el resultado de los márgenes establecidos para estos párrafos; así pues, el espaciado entre los párrafos se puede controlar ajustando los márgenes de esos párrafos.  Para eliminar totalmente el espaciado adicional entre dos párrafos, establezca los márgenes de los párrafos en **0**.  Para conseguir un espaciado uniforme entre los párrafos en un objeto <xref:System.Windows.Documents.FlowDocument> completo, se utilizan estilos para establecer un valor de margen uniforme para todos los párrafos contenidos en el objeto <xref:System.Windows.Documents.FlowDocument>.  
  
 Es importante tener en cuenta que los márgenes de dos párrafos adyacentes se "contraerán" para respetar el mayor de los dos márgenes, en lugar de duplicarlo.  Así pues, si dos párrafos adyacentes tienen, márgenes de 20 y 40 píxeles, respectivamente, el espacio resultante entre los párrafos será de 40 píxeles, el mayor de los dos valores de margen.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan estilos para establecer el margen para todos los elementos <xref:System.Windows.Documents.Paragraph> de un objeto <xref:System.Windows.Documents.FlowDocument> en **0**, lo que, en realidad, elimina el espaciado adicional entre los párrafos de <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-xml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]