---
title: "C&#243;mo: Cambiar la propiedad FlowDirection de contenido mediante programaci&#243;n | Microsoft Docs"
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
  - "documentos, cambiar la propiedad FlowDirection mediante programación"
  - "FlowDirection (propiedad), cambiar mediante programación"
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Cambiar la propiedad FlowDirection de contenido mediante programaci&#243;n
En este ejemplo se muestra cómo cambiar mediante programación la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> de un control <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## Ejemplo  
 Se crean dos elementos <xref:System.Windows.Controls.Button>, cada uno de los cuales representa uno de los valores posibles de <xref:System.Windows.FlowDirection>.  Cuando se hace clic en un botón, el valor de propiedad asociado se aplica al contenido de un control <xref:System.Windows.Controls.FlowDocumentReader> llamado `tf1`.  El valor de propiedad se escribe también en un control <xref:System.Windows.Controls.TextBlock> llamado `txt1`.  
  
 [!code-xml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## Ejemplo  
 Los eventos asociados a los clics del botón definidos más arriba se administran en un archivo de código subyacente [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)].  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]