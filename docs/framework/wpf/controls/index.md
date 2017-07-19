---
title: Controles | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7652a2e64cdc107546ac3ea51178a3542606bd43
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="controls"></a>Controles
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se distribuye con muchos de los componentes de interfaz de usuario comunes que se utilizan en casi todas las aplicaciones Windows, como              <xref:System.Windows.Controls.Button>,              <xref:System.Windows.Controls.Label>,              <xref:System.Windows.Controls.TextBox>,              <xref:System.Windows.Controls.Menu> y              <xref:System.Windows.Controls.ListBox>. Históricamente, estos objetos se han denominado controles. Mientras que en el SDK de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se continúa usando el término "control" para referirse a cualquier clase que represente un objeto visible de una aplicación, es importante advertir que una clase no necesita heredar de la clase              <xref:System.Windows.Controls.Control> para tener una presencia visible. Las clases que heredan de la clase              <xref:System.Windows.Controls.Control> contienen un objeto              <xref:System.Windows.Controls.ControlTemplate>, que permite al consumidor de un control cambiar radicalmente el aspecto de este sin tener que crear una nueva subclase.  En este tema se describen los usos más comunes de los controles (tanto los que heredan de la clase              <xref:System.Windows.Controls.Control> como los que no) en              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede agregar un control a una aplicación usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos etiquetas, dos cuadros de texto y dos botones, en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Todos los controles se pueden crear de igual forma.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Para mayor brevedad, la creación de                  <xref:System.Windows.Controls.Grid>,                  `grid1`, se ha excluido del ejemplo.                   `grid1` tiene las mismas definiciones de columnas y filas que en el ejemplo anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)] [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
-   Cambiar el valor de una propiedad del control.  
  
-   Crear un elemento                          <xref:System.Windows.Style> para el control.  
  
-   Crear un elemento                          <xref:System.Windows.Controls.ControlTemplate> nuevo para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que permiten cambiar el aspecto del control, como                          <xref:System.Windows.Controls.Control.Background%2A> de                          <xref:System.Windows.Controls.Button>. Puede establecer las propiedades del valor tanto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como con código. En el ejemplo siguiente se establecen las propiedades                           <xref:System.Windows.Controls.Control.Background%2A>,                          <xref:System.Windows.Controls.Control.FontSize%2A> y                          <xref:System.Windows.Controls.Control.FontWeight%2A> de                          <xref:System.Windows.Controls.Button> en                          [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)] [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite especificar la apariencia de los controles de manera global, en lugar de establecer las propiedades en cada instancia de la aplicación, si se crea una clase                          <xref:System.Windows.Style>.                           En el ejemplo siguiente                          se crea un objeto                          <xref:System.Windows.Style> aplicable a cada clase                          <xref:System.Windows.Controls.Button> de la aplicación.                          Las definiciones <xref:System.Windows.Style> suelen definirse en                          [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en                          <xref:System.Windows.ResourceDictionary>, como la propiedad                          <xref:System.Windows.FrameworkElement.Resources%2A> de                          <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo solo a determinados controles de un tipo específico; para ello asigne una clave al estilo y especifique esa clave en la propiedad `Style` del control.  Para más información acerca de los estilos, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 <xref:System.Windows.Style> permite establecer las propiedades en varios controles a la vez, pero en ocasiones puede ser conveniente personalizar la apariencia de un objeto                           <xref:System.Windows.Controls.Control> más allá de lo que se puede hacer creando un elemento                          <xref:System.Windows.Style>. Las clases que heredan de la clase                          <xref:System.Windows.Controls.Control> tienen un elemento                          <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y la apariencia de                          <xref:System.Windows.Controls.Control>. La propiedad                          <xref:System.Windows.Controls.Control.Template%2A> de                          <xref:System.Windows.Controls.Control> es pública, por lo que puede proporcionar una clase                          <xref:System.Windows.Controls.Control> en                          <xref:System.Windows.Controls.ControlTemplate> que sea distinta de la predeterminada. A menudo, puede especificar una nueva clase                          <xref:System.Windows.Controls.ControlTemplate> para                          <xref:System.Windows.Controls.Control> en lugar de heredar de un control para personalizar la apariencia de                          <xref:System.Windows.Controls.Control>.  
  
 Considere un control muy común,                          <xref:System.Windows.Controls.Button>.  El comportamiento primario de                          <xref:System.Windows.Controls.Button> es permitir que una aplicación realice una acción cuando el usuario hace clic en él.  De forma predeterminada,                          <xref:System.Windows.Controls.Button> de                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al programar una aplicación, es posible que quiera aprovechar el comportamiento de                          <xref:System.Windows.Controls.Button>, es decir, controlar el evento de hacer clic en el botón, pero que desee cambiar el aspecto del botón más allá de lo que es posible cambiando las propiedades de este.  En este caso puede crear una nueva clase                          <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se crea                          <xref:System.Windows.Controls.ControlTemplate> para                          <xref:System.Windows.Controls.Button>.  La clase                          <xref:System.Windows.Controls.ControlTemplate> crea                          <xref:System.Windows.Controls.Button> con esquinas redondeadas y un fondo degradado.  La clase                          <xref:System.Windows.Controls.ControlTemplate> contiene                          <xref:System.Windows.Controls.Border>, cuya propiedad                          <xref:System.Windows.Controls.Border.Background%2A> es                          <xref:System.Windows.Media.LinearGradientBrush> con dos objetos                          <xref:System.Windows.Media.GradientStop>.  El primer                          <xref:System.Windows.Media.GradientStop> usa enlaces de datos que enlazan la propiedad                          <xref:System.Windows.Media.GradientStop.Color%2A> de                          <xref:System.Windows.Media.GradientStop> al color de fondo del botón.  Si establece la propiedad                          <xref:System.Windows.Controls.Control.Background%2A> de                          <xref:System.Windows.Controls.Button>, el color de dicho valor se usará como el primer                          <xref:System.Windows.Media.GradientStop>. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md). En el ejemplo también se crea una clase                          <xref:System.Windows.Trigger> que cambia la apariencia de                          <xref:System.Windows.Controls.Button> cuando                          <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es                          `true`.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  La propiedad                              <xref:System.Windows.Controls.Control.Background%2A> de                              <xref:System.Windows.Controls.Button> debe establecerse en                              <xref:System.Windows.Media.SolidColorBrush> para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse a un evento de un control mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código, pero los eventos únicamente se pueden controlar mediante código.  En el ejemplo siguiente se muestra cómo suscribirse al evento                  `Click` de                  <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)] [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo siguiente se controla el evento                  `Click` de                  <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)] [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de las clases que heredan de la clase                  <xref:System.Windows.Controls.Control> tienen la capacidad de incluir contenido enriquecido. Por ejemplo, una clase                  <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, una clase                  <xref:System.Windows.Controls.Image> o una clase                   <xref:System.Windows.Controls.Panel>.  Las clases siguientes proporcionan compatibilidad con el contenido enriquecido y actúan como clases base para la mayoría de los controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>-- Algunos ejemplos de clases que heredan de esta clase son                          <xref:System.Windows.Controls.Label>,                          <xref:System.Windows.Controls.Button> y                          <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>-- Algunos ejemplos de clases que heredan de esta clase son                          <xref:System.Windows.Controls.ListBox>,                          <xref:System.Windows.Controls.Menu> y                          <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>-- Algunos ejemplos de clases que heredan de esta clase son                          <xref:System.Windows.Controls.TabItem>,                          <xref:System.Windows.Controls.GroupBox> y                          <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que heredan de esta clase son                          <xref:System.Windows.Controls.MenuItem>,                          <xref:System.Windows.Controls.TreeViewItem> y                          <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Para más información sobre estas clases base, consulte [WPF Content Model](../../../../docs/framework/wpf/controls/wpf-content-model.md) (Modelo de contenido de WPF).  
  
## <a name="see-also"></a>Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Agrupar controles por categoría](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Biblioteca de controles](../../../../docs/framework/wpf/controls/control-library.md)   
 [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md)  (Introducción a las plantillas de datos)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Input](../../../../docs/framework/wpf/advanced/input-wpf.md)  (Entrada)  
 [Enable a Command](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  (Habilitación de un comando)  
 [Walkthroughs: Create a Custom Animated Button](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  (Tutoriales: Creación de un botón animado personalizado)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)
