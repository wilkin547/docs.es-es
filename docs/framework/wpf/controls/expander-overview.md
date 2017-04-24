---
title: "Informaci&#243;n general sobre el control Expander | Microsoft Docs"
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
  - "controles, Expander"
  - "Expander (control), acerca de Expander (control)"
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Informaci&#243;n general sobre el control Expander
Un control <xref:System.Windows.Controls.Expander> proporciona una manera de proporcionar contenido en un área ampliable que se parece una ventana e incluye un encabezado.  
  
   
  
<a name="CreatinganExpanderinXAML"></a>   
## Crear un ampliador sencillo  
 En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.Expander> sencillo.  En este ejemplo se crea un control <xref:System.Windows.Controls.Expander> que se parece al de la ilustración anterior.  
  
 [!code-xml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Las propiedades <xref:System.Windows.Controls.ContentControl.Content%2A> y <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> de un control <xref:System.Windows.Controls.Expander> también pueden incluir contenido complejo, como objetos <xref:System.Windows.Controls.RadioButton> e <xref:System.Windows.Controls.Image>.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## Establecer la dirección del área de contenido ampliable  
 Puede establecer el área de contenido de un control <xref:System.Windows.Controls.Expander> de modo que se expanda en cuatro direcciones \(<xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection> o <xref:System.Windows.Controls.ExpandDirection>\) mediante la propiedad <xref:System.Windows.Controls.ExpandDirection>.  Cuando se contrae el área de contenido, sólo aparecen el encabezado \(<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>\) del control <xref:System.Windows.Controls.Expander> y su botón de alternancia.  Para expandir o contraer el área de contenido, se usa como botón de alternancia un control <xref:System.Windows.Controls.Button> que muestra una flecha de dirección.  Cuando se expande el control <xref:System.Windows.Controls.Expander>, intenta mostrar todos su contenido en un área similar a una ventana.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## Controlar el tamaño de un ampliador en un panel  
 Si un control <xref:System.Windows.Controls.Expander> está dentro de un control de diseño que hereda de un control <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.StackPanel>, no especifique la propiedad <xref:System.Windows.FrameworkElement.Height%2A> en <xref:System.Windows.Controls.Expander> cuando la propiedad <xref:System.Windows.Controls.Expander.ExpandDirection%2A> esté establecida en <xref:System.Windows.Controls.ExpandDirection> o en <xref:System.Windows.Controls.ExpandDirection>.  De igual forma, no especifique la propiedad <xref:System.Windows.FrameworkElement.Width%2A> en un control <xref:System.Windows.Controls.Expander> cuando la propiedad <xref:System.Windows.Controls.Expander.ExpandDirection%2A> esté establecida en <xref:System.Windows.Controls.ExpandDirection> o <xref:System.Windows.Controls.ExpandDirection>.  
  
 Si establece dimensiones en un control <xref:System.Windows.Controls.Expander> en la dirección en que se muestra el contenido ampliado, <xref:System.Windows.Controls.Expander> asume el control del área usada por el contenido y muestra un borde alrededor de ella.  Este borde aparece aunque el contenido esté contraído.  Para establecer el tamaño del área de contenido ampliada, establezca las dimensiones en el contenido del control <xref:System.Windows.Controls.Expander>. Opcionalmente, si desea disponer de la función de desplazamiento, establézcalas en el control <xref:System.Windows.Controls.ScrollViewer> que encierra el contenido.  
  
 Cuando un control <xref:System.Windows.Controls.Expander> es el último elemento de un control <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] establece automáticamente las dimensiones de <xref:System.Windows.Controls.Expander> en un tamaño igual al área restante de <xref:System.Windows.Controls.DockPanel>.  Para evitar este comportamiento predeterminado, establezca la propiedad <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> del objeto <xref:System.Windows.Controls.DockPanel> en `false` o asegúrese de que <xref:System.Windows.Controls.Expander> no sea el último elemento del control <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## Crear contenido desplazable  
 Si el contenido es demasiado grande para el tamaño del área de contenido, puede ajustar el contenido del control <xref:System.Windows.Controls.Expander> en un control <xref:System.Windows.Controls.ScrollViewer> para proporcionar contenido desplazable.  El control <xref:System.Windows.Controls.Expander> no proporciona automáticamente la función de desplazamiento.  En la ilustración siguiente se muestra un control <xref:System.Windows.Controls.Expander> que contiene un control <xref:System.Windows.Controls.ScrollViewer>.  
  
 **Control Expander en un control ScrollViewer**  
  
 ![Expander con ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 Cuando coloque un control <xref:System.Windows.Controls.Expander> en un control <xref:System.Windows.Controls.ScrollViewer>, establezca la propiedad de dimensión de <xref:System.Windows.Controls.ScrollViewer> que corresponda a la dirección en la que se abre el contenido de <xref:System.Windows.Controls.Expander> en el tamaño del área de contenido de <xref:System.Windows.Controls.Expander>.  Por ejemplo, si establece la propiedad <xref:System.Windows.Controls.Expander.ExpandDirection%2A> de <xref:System.Windows.Controls.Expander> en <xref:System.Windows.Controls.ExpandDirection> \(el área de contenido se abre hacia abajo\), establezca la propiedad <xref:System.Windows.FrameworkElement.Height%2A> del control <xref:System.Windows.Controls.ScrollViewer> en el alto necesario para el área de contenido.  Si en lugar de ello establece la dimensión de alto en el propio contenido, <xref:System.Windows.Controls.ScrollViewer> no reconoce este valor y, por consiguiente, no proporciona contenido desplazable.  
  
 En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.Expander> que incluye contenido complejo y un control <xref:System.Windows.Controls.ScrollViewer>.  En este ejemplo se crea un control <xref:System.Windows.Controls.Expander> parecido al de la ilustración del principio de esta sección.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## Usar las propiedades de alineación  
 Puede alinear el contenido estableciendo las propiedades <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> del control <xref:System.Windows.Controls.Expander>.  Cuando se establecen estas propiedades, la alineación se aplica al encabezado y también al contenido ampliado.  
  
## Vea también  
 <xref:System.Windows.Controls.Expander>   
 <xref:System.Windows.Controls.ExpandDirection>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)