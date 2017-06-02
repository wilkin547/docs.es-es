---
title: "C&#243;mo: Crear un control Expander con un control ScrollViewer | Microsoft Docs"
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
  - "controles [WPF], Expander"
  - "controles [WPF], ScrollViewer"
  - "Expander (control), crear"
  - "ScrollViewer (control), con el control Expander"
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un control Expander con un control ScrollViewer
En este ejemplo se muestra cómo crear un control <xref:System.Windows.Controls.Expander> que incluye contenido complejo, como una imagen y texto.  En el ejemplo también se agrega el contenido de <xref:System.Windows.Controls.Expander> a un control <xref:System.Windows.Controls.ScrollViewer>.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo crear un objeto <xref:System.Windows.Controls.Expander>.  En el ejemplo se utiliza un control <xref:System.Windows.Controls.Primitives.BulletDecorator>, que contiene una imagen y texto, para definir la propiedad <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.  Un control <xref:System.Windows.Controls.ScrollViewer> proporciona un método para desplazar el contenido expandido.  
  
 Observe que el ejemplo establece la propiedad <xref:System.Windows.FrameworkElement.Height%2A> de <xref:System.Windows.Controls.ScrollViewer>, no del contenido.  Si <xref:System.Windows.FrameworkElement.Height%2A> se establece para el contenido, <xref:System.Windows.Controls.ScrollViewer> no permite al usuario desplazar el contenido.  La propiedad <xref:System.Windows.FrameworkElement.Width%2A> se establece para el control <xref:System.Windows.Controls.Expander> y este valor se aplica a la propiedad <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y al contenido expandido.  
  
 [!code-xml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## Vea también  
 <xref:System.Windows.Controls.Expander>   
 [Información general sobre el control Expander](../../../../docs/framework/wpf/controls/expander-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)