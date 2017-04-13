---
title: "C&#243;mo: Crear un elemento de panel personalizado | Microsoft Docs"
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
  - "elementos Panel personalizados"
  - "Panel (control)"
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un elemento de panel personalizado
## Ejemplo  
 En este ejemplo se muestra cómo invalidar el comportamiento de diseño predeterminado del elemento <xref:System.Windows.Controls.Panel> y crear elementos de diseño personalizados derivados de <xref:System.Windows.Controls.Panel>.  
  
 En este ejemplo se define un elemento <xref:System.Windows.Controls.Panel> personalizado simple llamado `PlotPanel`, que coloca elementos secundarios según dos coordenadas x e y codificadas de forma rígida.  En este ejemplo, `x` y `y` se establecen en `50`; por consiguiente, todos los elementos secundarios se colocan en esa ubicación en los ejes x e y.  
  
 Para implementar comportamientos de <xref:System.Windows.Controls.Panel> personalizados, en el ejemplo se utilizan los métodos  <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  Cada método devuelve los datos de <xref:System.Windows.Size> necesarios para colocar y representar elementos secundarios.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Panel>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Ejemplo Create a Custom Content\-Wrapping Panel](http://go.microsoft.com/fwlink/?LinkID=159979)