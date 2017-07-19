---
title: "C&#243;mo: Aplicar una transformaci&#243;n a un elemento cuando se provoca un evento | Microsoft Docs"
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
  - "gráficos, transformaciones como respuestas a eventos"
  - "LayoutTransform (propiedad)"
  - "propiedades, LayoutTransform"
  - "propiedades, RenderTransform"
  - "RenderTransform (propiedad)"
  - "transformaciones como respuestas a eventos"
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Aplicar una transformaci&#243;n a un elemento cuando se provoca un evento
En este ejemplo se muestra cómo aplicar <xref:System.Windows.Media.ScaleTransform> cuando se provoca un evento.  El concepto que se muestra aquí es el mismo que se utiliza para aplicar otros tipos de transformaciones.  Para obtener más información sobre los tipos de transformaciones disponibles, vea la clase <xref:System.Windows.Media.Transform> o la [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Puede aplicar una transformación a un elemento de cualquiera de estas dos maneras:  
  
-   Si *no* desea que la transformación afecte al diseño, utilice la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del elemento.  
  
-   Si desea que la transformación afecte al diseño, utilice la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> del elemento.  
  
 En el ejemplo siguiente se aplica <xref:System.Windows.Media.ScaleTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de un botón.  Cuando el mouse se mueve por encima del botón, las propiedades <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> de <xref:System.Windows.Media.ScaleTransform> se establecen en `2`, lo que hace que el botón se agrande.  Cuando el mouse se aleja del botón, las propiedades <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> se establecen en `1`, lo que hace que el botón recupere su tamaño original.  
  
## Ejemplo  
 [!code-xml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)