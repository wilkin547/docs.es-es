---
title: "C&#243;mo: Buscar elementos generados por un objeto ControlTemplate | Microsoft Docs"
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
  - "ControlTemplates [WPF], buscar elementos"
  - "buscar elementos de ControlTemplate"
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Buscar elementos generados por un objeto ControlTemplate
En este ejemplo, se muestra cómo buscar elementos generados por un objeto <xref:System.Windows.Controls.ControlTemplate>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un estilo que crea un objeto <xref:System.Windows.Controls.ControlTemplate> simple para la clase <xref:System.Windows.Controls.Button>:  
  
 [!code-xml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Para buscar un elemento dentro de la plantilla una vez aplicada, puede llamar al método <xref:System.Windows.FrameworkTemplate.FindName%2A> de <xref:System.Windows.Controls.Control.Template%2A>.  En el ejemplo siguiente se crea un cuadro de mensaje que muestra el valor de ancho real de <xref:System.Windows.Controls.Grid> dentro de la plantilla de control:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## Vea también  
 [Buscar elementos generados por un objeto DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)