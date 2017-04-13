---
title: "C&#243;mo: Buscar elementos generados por un objeto DataTemplate | Microsoft Docs"
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
  - "PlantillaDeDatos"
  - "buscar elementos de plantilla de datos"
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Buscar elementos generados por un objeto DataTemplate
En este ejemplo, se muestra cómo buscar elementos generados por un objeto <xref:System.Windows.DataTemplate>.  
  
## Ejemplo  
 En este ejemplo, hay un control <xref:System.Windows.Controls.ListBox> enlazado a algunos datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]:  
  
 [!code-xml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 El control <xref:System.Windows.Controls.ListBox> utiliza el siguiente objeto <xref:System.Windows.DataTemplate>:  
  
 [!code-xml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Si desea recuperar el elemento <xref:System.Windows.Controls.TextBlock> generado por el objeto <xref:System.Windows.DataTemplate> de un elemento <xref:System.Windows.Controls.ListBoxItem> determinado, debe obtener el elemento <xref:System.Windows.Controls.ListBoxItem>, hallar el objeto <xref:System.Windows.Controls.ContentPresenter> contenido en ese <xref:System.Windows.Controls.ListBoxItem> y, a continuación, llamar al método <xref:System.Windows.FrameworkTemplate.FindName%2A> del objeto <xref:System.Windows.DataTemplate> establecido para ese objeto <xref:System.Windows.Controls.ContentPresenter>.  En el ejemplo siguiente se muestra cómo realizar estos pasos.  Con fines de demostración, en este ejemplo se crea un cuadro de mensaje que muestra el contenido de texto de <xref:System.Windows.DataTemplate>, el bloque de texto generado.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 A continuación se muestra la implementación de `FindVisualChild`, que utiliza los métodos de <xref:System.Windows.Media.VisualTreeHelper>:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## Vea también  
 [Cómo: Buscar elementos generados por un objeto ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)