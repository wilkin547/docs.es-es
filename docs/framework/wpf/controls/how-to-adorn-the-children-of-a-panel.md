---
title: "C&#243;mo: Incluir adornos en los elementos secundarios de un panel | Microsoft Docs"
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
  - "adornos, enlazar a elementos secundarios de paneles"
  - "Panel (control), enlazar etiquetas contextuales a elementos secundarios"
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Incluir adornos en los elementos secundarios de un panel
En este ejemplo se muestra cómo enlazar mediante programación un adorno a los elementos secundarios del control <xref:System.Windows.Controls.Panel> especificado.  
  
## Ejemplo  
 Para enlazar un adorno contextual a los elementos secundarios de un control <xref:System.Windows.Controls.Panel>, siga estos pasos:  
  
1.  Declare un nuevo objeto <xref:System.Windows.Documents.AdornerLayer> y llame al método `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para encontrar una capa de adornos para el elemento cuyos elementos secundarios se van a etiquetar.  
  
2.  Enumere los elementos secundarios del elemento primario y llame al método <xref:System.Windows.Documents.AdornerLayer.Add%2A> para enlazar un adorno a cada elemento secundario.  
  
 En el ejemplo siguiente se enlaza el adorno SimpleCircleAdorner \(mostrada anteriormente\) a los elementos secundarios de un control <xref:System.Windows.Controls.StackPanel> denominado *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.  
  
## Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)