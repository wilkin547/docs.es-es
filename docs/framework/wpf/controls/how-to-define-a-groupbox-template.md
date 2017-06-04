---
title: "C&#243;mo: Definir una plantilla de un control GroupBox | Microsoft Docs"
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
  - "controles, GroupBox"
  - "GroupBox (control), crear plantillas"
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Definir una plantilla de un control GroupBox
En este ejemplo se muestra cómo crear una plantilla para un control <xref:System.Windows.Controls.GroupBox>.  
  
## Ejemplo  
 En el ejemplo siguiente se define una plantilla de control <xref:System.Windows.Controls.GroupBox> utilizando un control <xref:System.Windows.Controls.Grid> para el diseño.  En la plantilla se utiliza <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde del control <xref:System.Windows.Controls.GroupBox> de modo que el borde no oculte el contenido de <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.  
  
 [!code-xml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## Vea también  
 <xref:System.Windows.Controls.GroupBox>   
 [GroupBox How\-to Topics](http://msdn.microsoft.com/es-es/7692e155-a4c6-428c-b7e0-64b3740daca7)