---
title: "Informaci&#243;n general de informaci&#243;n sobre herramientas | Microsoft Docs"
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
  - "controles, Información sobre herramientas"
  - "ToolTip (control), acerca del control ToolTip"
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Informaci&#243;n general de informaci&#243;n sobre herramientas
Una información sobre herramientas es una pequeña ventana emergente que aparece cuando el usuario detiene el puntero del mouse sobre un elemento, por ejemplo sobre un control <xref:System.Windows.Controls.Button>.  En este tema se presenta la información sobre herramientas y se aborda cómo crear y personalizar el contenido de la información sobre herramientas.  
  
   
  
<a name="what_is_a_tooltip"></a>   
## ¿Qué es la información sobre herramientas?  
 Cuando el usuario mueve el puntero del mouse sobre un elemento que tiene información sobre herramientas, aparece una ventana que contiene el contenido de la información sobre herramientas \(por ejemplo, contenido de texto que describe la función de un control\) durante un periodo específico de tiempo.  Si el usuario aleja el puntero del mouse del control, la ventana desaparece porque el contenido de la información sobre herramientas no puede recibir el foco.  
  
 El contenido de la información sobre herramientas puede constar de una o varias líneas de texto, imágenes, formas u otro contenido visual.  Para definir la información sobre herramientas de un control, establezca una de las propiedades siguientes en el contenido de la información sobre herramientas.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>  
  
 La propiedad que utilice depende de si el control que define la información sobre herramientas hereda de la clase <xref:System.Windows.FrameworkContentElement> o <xref:System.Windows.FrameworkElement>.  
  
<a name="create_tooltip"></a>   
## Crear una información sobre herramientas  
 En el ejemplo siguiente se muestra cómo crear una información sobre herramientas simple estableciendo la propiedad <xref:System.Windows.FrameworkElement.ToolTip%2A> de un control <xref:System.Windows.Controls.Button> en una cadena de texto.  
  
 [!code-xml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 También puede definir la información sobre herramientas como un objeto <xref:System.Windows.Controls.ToolTip>.  En el ejemplo siguiente se utiliza [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar un objeto <xref:System.Windows.Controls.ToolTip> como la información sobre herramientas de un elemento <xref:System.Windows.Controls.TextBox>.  Observe que en el ejemplo se especifica el objeto <xref:System.Windows.Controls.ToolTip> estableciendo la propiedad <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=fullName>.  
  
 [!code-xml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 En el ejemplo siguiente se utiliza código para generar un objeto <xref:System.Windows.Controls.ToolTip>.  En el ejemplo se crea un objeto <xref:System.Windows.Controls.ToolTip> \(`tt`\) que se asocia a un control <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 También puede crear contenido de información sobre herramientas que no se defina como un objeto <xref:System.Windows.Controls.ToolTip> incluyendo el contenido de la información sobre herramientas en un elemento de diseño, como un control <xref:System.Windows.Controls.DockPanel>.  En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.FrameworkElement.ToolTip%2A> de un control <xref:System.Windows.Controls.TextBox> en contenido incluido en un control <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-xml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## Utilizar las propiedades de las clases ToolTip y ToolTipService  
 Puede personalizar el contenido de la información sobre herramientas estableciendo propiedades visuales y aplicando estilos.  Si define el contenido de la información sobre herramientas como un objeto <xref:System.Windows.Controls.ToolTip>, podrá establecer las propiedades visuales del objeto <xref:System.Windows.Controls.ToolTip>.  De lo contrario, debe establecer las [propiedades asociadas](GTMT) equivalentes en la clase <xref:System.Windows.Controls.ToolTipService>.  
  
 Si desea ver un ejemplo de cómo establecer las propiedades para especificar la posición del contenido de la información sobre herramientas utilizando las propiedades <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService>, vea [Situar una información sobre herramientas](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## Aplicar estilos a una información sobre herramientas  
 Puede aplicar estilos a un control <xref:System.Windows.Controls.ToolTip> definiendo un objeto <xref:System.Windows.Style> personalizado.  En el ejemplo siguiente se define un objeto <xref:System.Windows.Style> denominado `Simple` que muestra cómo desplazar la posición del objeto <xref:System.Windows.Controls.ToolTip> y cambiar su apariencia estableciendo las propiedades <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## Utilizar las propiedades de intervalo de tiempo de ToolTipService  
 La clase <xref:System.Windows.Controls.ToolTipService> proporciona las propiedades siguientes para establecer los tiempos de presentación de la información sobre herramientas: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Utilice las propiedades <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> para especificar el tiempo, normalmente breve, que debe transcurrir hasta que aparezca un control <xref:System.Windows.Controls.ToolTip> y también para especificar cuánto tiempo permanece visible el control <xref:System.Windows.Controls.ToolTip>.  Para obtener más información, vea [How to: Delay the Display of a ToolTip](http://msdn.microsoft.com/es-es/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).  
  
 La propiedad <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> determina si la información sobre herramientas de los diferentes controles aparece sin retraso inicial al moverse rápidamente el puntero del mouse entre ellos.  Para obtener más información sobre la propiedad <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, vea [Usar la propiedad BetweenShowDelay](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 En el ejemplo siguiente se muestra cómo establecer estas propiedades para una información sobre herramientas.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## Vea también  
 <xref:System.Windows.Controls.ToolTipService>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipEventArgs>   
 <xref:System.Windows.Controls.ToolTipEventHandler>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)