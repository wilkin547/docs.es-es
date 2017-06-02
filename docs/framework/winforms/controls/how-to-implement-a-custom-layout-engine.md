---
title: "C&#243;mo: Implementar un motor de dise&#241;o personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "FlowLayoutPanel (control) [Windows Forms], motor de diseño"
  - "motor de diseño, personalizado"
  - "motor de diseño, implementar"
  - "LayoutEngine (clase)"
  - "TableLayoutPanel (control) [Windows Forms], motor de diseño"
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Implementar un motor de dise&#241;o personalizado
En el ejemplo de código siguiente se muestra cómo crear un motor de diseño personalizado que realiza un diseño de flujo simple.  El código implementa un control de panel denominado `DemoFlowPanel`, que reemplaza la propiedad <xref:System.Windows.Forms.Control.LayoutEngine%2A> para proporcionar una instancia de la clase `DemoFlowLayout`.  
  
## Ejemplo  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Forms.Layout.LayoutEngine>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=fullName>