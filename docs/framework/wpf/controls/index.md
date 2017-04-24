---
title: "Controles | Microsoft Docs"
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
  - "controles [WPF], acerca de los controles WPF"
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Controles
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se distribuye con muchos de los componentes de interfaz de usuario comunes que se utilizan en casi todas las aplicaciones Windows, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> y <xref:System.Windows.Controls.ListBox>.  Históricamente, estos objetos se denominan controles.  Aunque en el SDK de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se continúa usando el término "control" para denominar genéricamente cualquier clase que representa un objeto visible de una aplicación, es importante tener en cuenta que una clase no necesita heredar de la clase <xref:System.Windows.Controls.Control> para tener una presencia visible.  Las clases que heredan de la clase <xref:System.Windows.Controls.Control> contienen una <xref:System.Windows.Controls.ControlTemplate>, que permite al consumidor de un control cambiar radicalmente el aspecto de éste sin tener que crear una nueva subclase.  En este tema se describen los usos más comunes de los controles \(tanto los que heredan de la clase <xref:System.Windows.Controls.Control> como los que no\) en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="creating_an_instance_of_a_control"></a>   
## Crear una instancia de un control  
 Puede agregar un control a una aplicación mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos etiquetas, dos cuadros de texto y dos botones, en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Todos los controles se pueden crear de igual forma.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código.  Para mayor brevedad, la creación de <xref:System.Windows.Controls.Grid>, `grid1` se ha excluido del ejemplo.  `grid1` tiene las mismas definiciones de columnas y filas que en el ejemplo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## Cambiar el aspecto de un control  
 Es común cambiar el aspecto de un control para ajustarlo a la apariencia y funcionamiento de la aplicación.  Puede cambiar el aspecto de un control realizando una de las acciones siguientes, dependiendo de lo que desea lograr:  
  
-   Cambiar el valor de una propiedad del control.  
  
-   Crear un <xref:System.Windows.Style> para el control.  
  
-   Crear una nueva <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### Cambiar el valor de una propiedad de un control  
 Muchos controles tienen propiedades que permiten cambiar el aspecto del control, como el fondo \(<xref:System.Windows.Controls.Control.Background%2A>\) de un botón \(<xref:System.Windows.Controls.Button>\).  Puede establecer las propiedades de valor en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y mediante código.  En el ejemplo siguiente se establecen las propiedades <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontWeight%2A> de un <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite especificar el aspecto de los controles de manera global, en lugar de establecer las propiedades en cada instancia de la aplicación, si se crea una clase <xref:System.Windows.Style>.  En el ejemplo siguiente se crea una clase <xref:System.Windows.Style> que se aplica a cada control <xref:System.Windows.Controls.Button> en la aplicación. Las definiciones de <xref:System.Windows.Style> se suelen definir en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en una clase <xref:System.Windows.ResourceDictionary>, como la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> de la clase <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo únicamente a determinados controles de un tipo específico asignando una clave al estilo y especificando esa la clave en la propiedad `Style` del control.  Para obtener más información acerca de los estilos, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### Crear una plantilla de control  
 <xref:System.Windows.Style> permite establecer las propiedades en varios controles a la vez, pero en ocasiones puede ser conveniente personalizar el aspecto de un <xref:System.Windows.Controls.Control> más allá de lo que se puede hacer creando un <xref:System.Windows.Style>.  Las clases que heredan de la clase <xref:System.Windows.Controls.Control> tienen una <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y el aspecto de un <xref:System.Windows.Controls.Control>.  La propiedad <xref:System.Windows.Controls.Control.Template%2A> de <xref:System.Windows.Controls.Control> es pública, por lo que puede dar una <xref:System.Windows.Controls.ControlTemplate> a un <xref:System.Windows.Controls.Control> diferente de la predeterminada.  Con frecuencia, se puede especificar una <xref:System.Windows.Controls.ControlTemplate> nueva para un <xref:System.Windows.Controls.Control> en lugar de heredar de un control para personalizar el aspecto de <xref:System.Windows.Controls.Control>.  
  
 Tomemos uno de los controles comunes, <xref:System.Windows.Controls.Button>.  El comportamiento primario de <xref:System.Windows.Controls.Button> es permitir que una aplicación realice una acción cuando el usuario hace clic en él.  De manera predeterminada, el control <xref:System.Windows.Controls.Button> aparece en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como un rectángulo elevado.  Al programar una aplicación, puede que quiera aprovechar el comportamiento de <xref:System.Windows.Controls.Button>, es decir, controlar el evento de hacer clic en el botón, pero que desee cambiar el aspecto del botón más allá de lo que es posible cambiando las propiedades del mismo.  En este caso, puede crear una nueva <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Controls.ControlTemplate> para un control <xref:System.Windows.Controls.Button>.  <xref:System.Windows.Controls.ControlTemplate> crea <xref:System.Windows.Controls.Button> con esquinas redondeadas y fondo degradado.  <xref:System.Windows.Controls.ControlTemplate> contiene un <xref:System.Windows.Controls.Border> cuyo <xref:System.Windows.Controls.Border.Background%2A> es <xref:System.Windows.Media.LinearGradientBrush> con dos objetos <xref:System.Windows.Media.GradientStop>.  El primer <xref:System.Windows.Media.GradientStop> utiliza el enlace de datos para enlazar la propiedad <xref:System.Windows.Media.GradientStop.Color%2A> de <xref:System.Windows.Media.GradientStop> al color de fondo del botón.  Al establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button>, el color de ese valor se utilizará como primer <xref:System.Windows.Media.GradientStop>.  Para obtener más información sobre el enlace de datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  En el ejemplo también se crea un <xref:System.Windows.Trigger> que cambia el aspecto de <xref:System.Windows.Controls.Button> cuando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es `true`.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> debe estar establecida en <xref:System.Windows.Media.SolidColorBrush> para que ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## Suscribirse a eventos  
 Puede suscribirse a un evento de un control mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código, pero los eventos únicamente se pueden controlar mediante código.  En el ejemplo siguiente se muestra cómo suscribirse al evento `Click` de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo siguiente se controla el evento `Click` de un control <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## Contenido enriquecido en los controles  
 La mayoría de las clases que heredan de la clase <xref:System.Windows.Controls.Control> tienen la capacidad de incluir contenido enriquecido.  Por ejemplo, un control <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, una <xref:System.Windows.Controls.Image>o un <xref:System.Windows.Controls.Panel>.  Las clases siguientes proporcionan compatibilidad con el contenido enriquecido y actúan como clases base para la mayoría de los controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu> y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox> y <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem> y <xref:System.Windows.Controls.ToolBar>.  
  
 Para obtener más información sobre estas clases base, vea [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Agrupar controles por categoría](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Biblioteca de controles](../../../../docs/framework/wpf/controls/control-library.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Entrada](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [Habilitar un comando](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [Tutoriales: Crear un botón animado personalizado](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)