---
title: "C&#243;mo: Personalizar el tama&#241;o de un control de posici&#243;n en un objeto ScrollBar | Microsoft Docs"
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
  - "personalizar tamaño del control de posición"
  - "ScrollBar (control)"
  - "tamaño del control de posición"
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Personalizar el tama&#241;o de un control de posici&#243;n en un objeto ScrollBar
En este tema se explica cómo establecer el control <xref:System.Windows.Controls.Primitives.Thumb> de un objeto <xref:System.Windows.Controls.Primitives.ScrollBar> en un tamaño fijo, y cómo especificar un tamaño mínimo para el control <xref:System.Windows.Controls.Primitives.Thumb> de un objeto <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## Ejemplo  
  
## Descripción  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un control <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño fijo.  En el ejemplo se establece la propiedad <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> del control <xref:System.Windows.Controls.Primitives.Thumb> en <xref:System.Double.NaN> y se establece el alto de <xref:System.Windows.Controls.Primitives.Thumb>.  Para crear un objeto <xref:System.Windows.Controls.Primitives.ScrollBar> horizontal con un control <xref:System.Windows.Controls.Primitives.Thumb> de ancho fijo, establezca el ancho de <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## Código  
 [!code-xml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## Descripción  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un control <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño mínimo.  En el ejemplo siguiente se establece el valor de <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.  Para crear un objeto <xref:System.Windows.Controls.Primitives.ScrollBar> horizontal con un control <xref:System.Windows.Controls.Primitives.Thumb> de ancho mínimo, establezca <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## Código  
 [!code-xml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## Vea también  
 [Estilos y plantillas de ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)