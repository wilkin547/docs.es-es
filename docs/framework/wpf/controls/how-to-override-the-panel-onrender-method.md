---
title: "C&#243;mo: Invalidar el m&#233;todo OnRender de un objeto Panel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "overriding OnRender method"
  - "Panel control, overriding OnRender method"
  - "OnRender method"
  - "controls, Panel, overriding OnRender method"
helpviewer_keywords: 
  - "OnRender (método), reemplazar"
  - "invalidar el método OnRender del control Panel"
  - "Panel (control), invalidar el método OnRender"
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Invalidar el m&#233;todo OnRender de un objeto Panel
En este ejemplo se muestra cómo invalidar el método <xref:System.Windows.Controls.Panel.OnRender%2A> de <xref:System.Windows.Controls.Panel> para agregar efectos gráficos personalizados a un elemento del diseño.  
  
## Ejemplo  
 Utilice el método <xref:System.Windows.Controls.Panel.OnRender%2A> para agregar efectos gráficos a un elemento Panel representado.  Por ejemplo, puede utilizar este método para agregar un borde personalizado o efectos de fondo.  Un objeto <xref:System.Windows.Media.DrawingContext> se pasa como argumento, lo que proporciona métodos para dibujar formas, texto, imágenes o vídeos.  Como resultado, este método resulta útil para personalizar los objetos Panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Panel>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Ejemplo Custom Radial Panel](http://go.microsoft.com/fwlink/?LinkID=159982)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)