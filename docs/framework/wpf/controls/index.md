---
title: Controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 11c9c2cdd9e485fb87f5d8ead7790ded0428f7dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se suministra con muchos de los componentes de interfaz de usuario comunes que se utilizan en casi todas las aplicaciones Windows, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, y <xref:System.Windows.Controls.ListBox>. Históricamente, estos objetos se han denominado controles. Mientras el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK continúa usando el término "control" para denominar genéricamente cualquier clase que representa un objeto visible en una aplicación, es importante tener en cuenta que no es necesario heredar de una clase la <xref:System.Windows.Controls.Control> clase para tener una presencia visible. Las clases que heredan de la <xref:System.Windows.Controls.Control> clase contienen un <xref:System.Windows.Controls.ControlTemplate>, que permite al consumidor de un control cambiar radicalmente la apariencia del control sin tener que crear una nueva subclase.  Este tema se describe cómo controles (tanto los que heredan de la <xref:System.Windows.Controls.Control> clase y aquellos que no lo hacen) suelen utilizarse en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede agregar un control a una aplicación mediante el uso [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crea seis controles: dos etiquetas, dos cuadros de texto y dos botones en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Por razones de brevedad, la creación de la <xref:System.Windows.Controls.Grid>, `grid1`, se ha excluido del ejemplo. `grid1` tiene las mismas definiciones de columna y fila, tal y como se muestra anteriormente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
-   Cambiar el valor de una propiedad del control.  
  
-   Crear un <xref:System.Windows.Style> para el control.  
  
-   Crear un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que le permiten cambiar el aspecto del control, como el <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button>. Puede establecer las propiedades de valor en ambas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el código. El ejemplo siguiente se establece la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, y <xref:System.Windows.Controls.Control.FontWeight%2A> propiedades en un <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece la posibilidad de especificar la apariencia de los controles por mayor, en lugar de establecer propiedades en cada instancia de la aplicación, mediante la creación de un <xref:System.Windows.Style>. En el ejemplo siguiente se crea un <xref:System.Windows.Style> que se aplica a cada <xref:System.Windows.Controls.Button> en la aplicación. <xref:System.Windows.Style> las definiciones se definen normalmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un <xref:System.Windows.ResourceDictionary>, como el <xref:System.Windows.FrameworkElement.Resources%2A> propiedad de la <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo únicamente a determinados controles de un tipo específico asignando una clave al estilo y especificando esa la clave en el `Style` propiedad del control.  Para obtener más información sobre los estilos, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 A <xref:System.Windows.Style> le permite establecer propiedades en varios controles a la vez, pero a veces desea personalizar la apariencia de un <xref:System.Windows.Controls.Control> más allá de lo que puede hacer mediante la creación de un <xref:System.Windows.Style>. Las clases que heredan de la <xref:System.Windows.Controls.Control> clase tiene un <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y la apariencia de un <xref:System.Windows.Controls.Control>. El <xref:System.Windows.Controls.Control.Template%2A> propiedad de un <xref:System.Windows.Controls.Control> es pública, por lo que puede dar un <xref:System.Windows.Controls.Control> un <xref:System.Windows.Controls.ControlTemplate> que es diferente de su valor predeterminado. A menudo es posible especificar un nuevo <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Control> en lugar de heredar de un control para personalizar la apariencia de un <xref:System.Windows.Controls.Control>.  
  
 Tenga en cuenta los controles comunes, <xref:System.Windows.Controls.Button>.  El comportamiento principal de un <xref:System.Windows.Controls.Button> consiste en habilitar una aplicación para realizar alguna acción cuando el usuario hace clic en él.  De forma predeterminada, el <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, puede aprovechar las ventajas del comportamiento de un <xref:System.Windows.Controls.Button>: es decir, mediante el control del botón click (evento), pero puede cambiar la apariencia del botón más allá de lo que puede hacer cambiando las propiedades del botón.  En este caso, puede crear un nuevo <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button>.  El <xref:System.Windows.Controls.ControlTemplate> crea un <xref:System.Windows.Controls.Button> con esquinas redondeadas y un fondo degradado.  El <xref:System.Windows.Controls.ControlTemplate> contiene un <xref:System.Windows.Controls.Border> cuyo <xref:System.Windows.Controls.Border.Background%2A> es un <xref:System.Windows.Media.LinearGradientBrush> con dos <xref:System.Windows.Media.GradientStop> objetos.  La primera <xref:System.Windows.Media.GradientStop> usa el enlace de datos para enlazar la <xref:System.Windows.Media.GradientStop.Color%2A> propiedad de la <xref:System.Windows.Media.GradientStop> el color de fondo del botón.  Al establecer el <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.Button>, el color de ese valor se usará como la primera <xref:System.Windows.Media.GradientStop>. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md). El ejemplo también crea un <xref:System.Windows.Trigger> que cambia la apariencia de la <xref:System.Windows.Controls.Button> cuando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es `true`.  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  El <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.Button> debe establecerse en un <xref:System.Windows.Media.SolidColorBrush> para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse a eventos de un control utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código, pero solo puede controlar un evento en el código.  En el ejemplo siguiente se muestra cómo suscribirse a la `Click` eventos de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 El siguiente ejemplo se controla el `Click` eventos de un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 Mayoría de las clases que heredan de la <xref:System.Windows.Controls.Control> clase tiene la capacidad para contener contenido enriquecido. Por ejemplo, un <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, un <xref:System.Windows.Controls.Image>, o un <xref:System.Windows.Controls.Panel>.  Las clases siguientes proporcionan compatibilidad con contenido enriquecido y actúan como clases base para la mayoría de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, y <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, y <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, y <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Para obtener más información acerca de estas clases base, vea [modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Agrupar controles por categoría](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [Biblioteca de controles](../../../../docs/framework/wpf/controls/control-library.md)  
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Entrada](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [Habilitar un comando](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [Tutoriales: Crear un botón animado personalizado](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)
