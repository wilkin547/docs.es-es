---
title: "C&#243;mo: Desplazarse por contenido utilizando la interfaz IScrollInfo | Microsoft Docs"
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
  - "IScrollInfo (interfaz)"
  - "desplazarse por el contenido"
  - "ScrollViewer (control), desplazarse por el contenido"
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Desplazarse por contenido utilizando la interfaz IScrollInfo
En este ejemplo se muestra cómo desplazar contenido utilizando la interfaz <xref:System.Windows.Controls.Primitives.IScrollInfo>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran las características de la interfaz <xref:System.Windows.Controls.Primitives.IScrollInfo>.  El ejemplo crea un elemento <xref:System.Windows.Controls.StackPanel> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] anidado en un objeto <xref:System.Windows.Controls.ScrollViewer> primario.  Los elementos secundarios del objeto <xref:System.Windows.Controls.StackPanel> se pueden desplazar lógicamente utilizando los métodos definidos por la interfaz <xref:System.Windows.Controls.Primitives.IScrollInfo>y convertir a la instancia de <xref:System.Windows.Controls.StackPanel> \(`sp1`\) en código.  
  
 [!code-xml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Cada objeto <xref:System.Windows.Controls.Button> del archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] desencadena un método personalizado asociado que controla el comportamiento del desplazamiento en <xref:System.Windows.Controls.StackPanel>.  En el ejemplo siguiente se muestra cómo utilizar los métodos <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>; también muestra genéricamente cómo utilizar todos los métodos de posición que define la clase <xref:System.Windows.Controls.Primitives.IScrollInfo>.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## Vea también  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 <xref:System.Windows.Controls.StackPanel>   
 [Información general sobre ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)