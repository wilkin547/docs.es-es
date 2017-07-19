---
title: "C&#243;mo: Hacer una prueba de posicionamiento en Viewport3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "elementos visuales 3D, prueba de posicionamiento de"
  - "prueba de visitas, para elementos visuales 3D"
  - "Viewport3D"
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Hacer una prueba de posicionamiento en Viewport3D
En este ejemplo se muestra cómo realizar la prueba de posicionamiento en los objetos visuales 3D en <xref:System.Windows.Controls.Viewport3D>.  
  
 Dado que <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> devuelve información 2D y 3D, es posible recorrer en iteración los resultados de pruebas para leer únicamente los resultados 3D.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 El comportamiento de prueba de posicionamiento \(<xref:System.Windows.Media.HitTestResultBehavior>\) del código siguiente determina cómo se procesan los resultados de pruebas de posicionamiento.  `UpdateResultInfo` y `UpdateMaterial` son métodos definidos localmente.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## Vea también  
 [3\-D Hit Testing Sample](http://go.microsoft.com/fwlink/?LinkID=159959)