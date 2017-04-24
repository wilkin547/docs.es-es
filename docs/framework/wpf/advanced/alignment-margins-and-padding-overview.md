---
title: "Informaci&#243;n general sobre alineaci&#243;n, m&#225;rgenes y relleno | Microsoft Docs"
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
  - "alinear"
  - "clases, FrameworkElement"
  - "FrameworkElement (clase)"
  - "márgenes"
  - "relleno"
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Informaci&#243;n general sobre alineaci&#243;n, m&#225;rgenes y relleno
La clase <xref:System.Windows.FrameworkElement> expone varias propiedades que se utilizan para colocar los elementos secundarios de forma precisa.  En este tema se analizan cuatro de las propiedades más importantes: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Es importante comprender los efectos de estas propiedades, ya que proporcionan la base para controlar la posición de los elementos en las aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## Introducción al posicionamiento de los elementos  
 Hay numerosas maneras de colocar los elementos mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sin embargo, lograr el diseño ideal va más allá de la simple elección del elemento <xref:System.Windows.Controls.Panel> adecuado.  El control preciso de la posición requiere estar familiarizado con las propiedades <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  
  
 En la ilustración siguiente se muestra un escenario de diseño que utiliza varias propiedades de posición.  
  
 ![Ejemplo WPF Positioning Properties](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.png "layout\_margins\_padding\_alignment\_graphic1")  
  
 A primera vista, podría parecer que los elementos <xref:System.Windows.Controls.Button> de esta ilustración están colocados de forma aleatoria.  Sin embargo, sus posiciones están controladas precisamente por medio de una combinación de márgenes, alineaciones y relleno.  
  
 En el ejemplo siguiente se describe cómo crear el diseño de la ilustración anterior.  Un elemento <xref:System.Windows.Controls.Border> encapsula un elemento <xref:System.Windows.Controls.StackPanel>primario, con un valor <xref:System.Windows.Controls.Border.Padding%2A> de 15 [píxeles independientes del dispositivo](GTMT).  Esto se debe a la banda <xref:System.Windows.Media.Brushes.LightBlue%2A> estrecha que rodea al elemento <xref:System.Windows.Controls.StackPanel> secundario.  Los elementos secundarios de <xref:System.Windows.Controls.StackPanel> se utilizan para mostrar cada una de las diversas propiedades de posición que se detallan en este tema.  Se usan tres elementos <xref:System.Windows.Controls.Button> para demostrar las propiedades <xref:System.Windows.FrameworkElement.Margin%2A> y <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 En el diagrama siguiente se proporciona una vista en primer plano de las distintas propiedades de posición que se utilizan en el ejemplo anterior.  En las secciones siguientes de este tema se describe con mayor detalle cómo utilizar cada propiedad de posición.  
  
 ![Propiedades de posición con llamadas de pantalla](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.png "layout\_margins\_padding\_alignment\_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## Introducción a las propiedades de alineación  
 Las propiedades <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> describen cómo debería colocarse un elemento secundario dentro del espacio de diseño asignado del elemento primario.  Al combinar estas propiedades, puede colocar los elementos secundarios de forma precisa.  Por ejemplo, los elementos secundarios de <xref:System.Windows.Controls.DockPanel> pueden especificar cuatro alineaciones horizontales diferentes: <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment> o <xref:System.Windows.HorizontalAlignment> para rellenar el espacio disponible.  Para la posición vertical existen valores similares.  
  
> [!NOTE]
>  Las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> establecidas explícitamente en un elemento tienen prioridad sobre el valor de propiedad <xref:System.Windows.HorizontalAlignment>.  Al intentar establecer <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>y <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en un valor de `Stretch`, la solicitud de `Stretch` se pasa por alto.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### Propiedad HorizontalAlignment  
 La propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> declara las características de alineación horizontal que se aplican a los elementos secundarios.  En la tabla siguiente se muestra cada uno de los valores posibles de la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment>|Los elementos secundarios se alinean a la izquierda del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment>|Los elementos secundarios se alinean al centro del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment>|Los elementos secundarios se alinean a la derecha del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment> \(valor predeterminado\)|Los elementos secundarios se ajustan para rellenar el espacio de diseño asignado del elemento primario.  Los valores explícitos de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> tienen prioridad.|  
  
 En el ejemplo siguiente se muestra cómo aplicar la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> a elementos <xref:System.Windows.Controls.Button>.  Se muestra cada valor de atributo, para ilustrar mejor los distintos comportamientos de representación.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 El código anterior produce un diseño similar a la imagen siguiente.  Los efectos de posicionamiento de cada valor de <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> se ven en la ilustración.  
  
 ![Ejemplo HorizontalAlignment](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.png "layout\_horizontal\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### Propiedad VerticalAlignment  
 La propiedad <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> describe las características de alineación vertical que se aplican a los elementos secundarios.  En la tabla siguiente se muestra cada uno de los valores posibles para la propiedad <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|<xref:System.Windows.VerticalAlignment>|Los elementos secundarios se alinean con la parte superior del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment>|Los elementos secundarios se alinean al centro del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment>|Los elementos secundarios se alinean con la parte inferior del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment> \(valor predeterminado\)|Los elementos secundarios se ajustan para rellenar el espacio de diseño asignado del elemento primario.  Los valores explícitos de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> tienen prioridad.|  
  
 En el ejemplo siguiente se muestra cómo aplicar la propiedad <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a elementos <xref:System.Windows.Controls.Button>.  Se muestra cada valor de atributo, para ilustrar mejor los distintos comportamientos de representación.  En este ejemplo, se usa como elemento primario un elemento <xref:System.Windows.Controls.Grid> con líneas de cuadrícula visibles, para ilustrar mejor el comportamiento de cada valor de propiedad en el diseño.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 El código anterior produce un diseño similar a la imagen siguiente.  Los efectos de posicionamiento de cada valor de <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> se ven en la ilustración.  
  
 ![Ejemplo de propiedad VerticalAlignment](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.png "layout\_vertical\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## Introducción a las propiedades de margen  
 La propiedad <xref:System.Windows.FrameworkElement.Margin%2A> describe la distancia entre un elemento y su elemento secundario o del mismo nivel.  Los valores de <xref:System.Windows.FrameworkElement.Margin%2A> pueden ser uniformes, mediante el uso de sintaxis como `Margin="20"`.  Con esta sintaxis, se aplicaría al elemento un valor de <xref:System.Windows.FrameworkElement.Margin%2A> uniforme de 20 [píxeles independientes del dispositivo](GTMT).  Los valores de <xref:System.Windows.FrameworkElement.Margin%2A> también pueden adoptar la forma de cuatro valores distintos, cada uno de los cuales describiría un margen distinto para aplicar a la izquierda, a la parte superior, a la derecha y a la parte inferior \(en ese orden\), como `Margin="0,10,5,25"`.  El uso apropiado de la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> permite obtener un control muy preciso de la posición de representación de un elemento y la posición de representación de sus elementos contiguos y secundarios.  
  
> [!NOTE]
>  Un margen distinto de cero aplica espacio fuera del <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> del elemento.  
  
 En el ejemplo siguiente se muestra cómo aplicar márgenes uniformes alrededor de un grupo de elementos <xref:System.Windows.Controls.Button>.  La separación de los elementos <xref:System.Windows.Controls.Button> es uniforme, con un búfer de margen de diez píxeles en cada dirección.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 En muchos casos no es apropiado un margen uniforme.  Si es así, se puede aplicar un espacio no uniforme.  En el ejemplo siguiente se muestra cómo aplicar un espacio de margen no uniforme a los elementos secundarios.  Los márgenes se describen por este orden: izquierdo, superior, derecho, inferior.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## Introducción a la propiedad de relleno  
 El relleno es similar a <xref:System.Windows.FrameworkElement.Margin%2A> en muchos aspectos.  La propiedad Padding se expone sólo en algunas clases, principalmente por comodidad: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control> y <xref:System.Windows.Controls.TextBlock> son ejemplos de clases que exponen una propiedad Padding.  La propiedad <xref:System.Windows.Controls.Border.Padding%2A> amplia el tamaño eficaz de un elemento secundario según el valor <xref:System.Windows.Thickness> especificado.  
  
 En el ejemplo siguiente se muestra cómo aplicar <xref:System.Windows.Controls.Border.Padding%2A> a un elemento <xref:System.Windows.Controls.Border> primario.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## Utilizar alineación, márgenes y relleno en una aplicación  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> ofrecen el control de posicionamiento necesario para crear una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] compleja.  Puede utilizar los efectos de cada propiedad para cambiar la posición de los elementos secundarios, lo que proporciona flexibilidad para lograr aplicaciones y experiencias de usuario dinámicas.  
  
 En el ejemplo siguiente se muestra cada uno de los conceptos que se detallan en este tema.  Partiendo de la infraestructura del primer ejemplo de este tema, en este ejemplo se agrega un elemento <xref:System.Windows.Controls.Grid> como elemento secundario del elemento <xref:System.Windows.Controls.Border> que veíamos en el primer ejemplo.  La propiedad <xref:System.Windows.Controls.Border.Padding%2A> se aplica al elemento primario <xref:System.Windows.Controls.Border>.  Se usa <xref:System.Windows.Controls.Grid> para dividir el espacio entre tres elementos <xref:System.Windows.Controls.StackPanel> secundarios.  Se vuelven a usar elementos <xref:System.Windows.Controls.Button> para mostrar los distintos efectos de <xref:System.Windows.FrameworkElement.Margin%2A> y <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  Se agregan elementos <xref:System.Windows.Controls.TextBlock> a cada <xref:System.Windows.Controls.ColumnDefinition> para mejorar la definición de las distintas propiedades aplicadas a los elementos <xref:System.Windows.Controls.Button> en cada columna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Cuando se compila, la aplicación anterior produce una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] similar a la de la ilustración siguiente.  Los efectos de los distintos valores de propiedad son evidentes en el espacio entre los elementos y los valores de propiedad significativos para los elementos de cada columna se muestran dentro de elementos <xref:System.Windows.Controls.TextBlock>.  
  
 ![Varias propiedades de posición en una aplicación](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.png "layout\_margins\_padding\_aligment\_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## Pasos adicionales  
 Las propiedades de posición definidas por la clase <xref:System.Windows.FrameworkElement> proporcionan un control preciso de la posición de los elementos en las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Ahora dispone de varias técnicas que puede utilizar para colocar mejor los elementos mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Existen recursos adicionales que explican con mayor detalle el diseño en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El tema [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md) contiene información más detallada sobre los diversos elementos <xref:System.Windows.Controls.Panel>.  El tema [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) presenta técnicas avanzadas que recurren a elementos de diseño para colocar los componentes y enlazar sus acciones a orígenes de datos.  
  
## Vea también  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.Margin%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)   
 [Ejemplo WPF Layout Gallery](http://go.microsoft.com/fwlink/?LinkID=160054)