---
title: Controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 0727bb8ac4f0ff25640ae6f8e292d89f903e4eb5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627323"
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se distribuye con muchos de los componentes de interfaz de usuario comunes que se utilizan en casi todas las aplicaciones Windows, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, y <xref:System.Windows.Controls.ListBox>. Históricamente, estos objetos se han denominado controles. Mientras el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK continúa usando el término "control" para referirse a cualquier clase que representa un objeto visible de una aplicación, es importante tener en cuenta que una clase no necesita heredar de la <xref:System.Windows.Controls.Control> clase para tener una presencia visible. Las clases que heredan de la <xref:System.Windows.Controls.Control> clase contienen un <xref:System.Windows.Controls.ControlTemplate>, que permite al consumidor de un control cambiar radicalmente el aspecto del control sin tener que crear una nueva subclase.  Este tema se describe cómo los controles (tanto los que heredan de la <xref:System.Windows.Controls.Control> clase y los que no) se suelen usar en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede agregar un control a una aplicación mediante el uso [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crea seis controles: dos etiquetas, dos cuadros de texto y dos botones, en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Para mayor brevedad, la creación de la <xref:System.Windows.Controls.Grid>, `grid1`, se ha excluido del ejemplo. `grid1` tiene las mismas definiciones de columna y fila, tal como se muestra en la anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
- Cambiar el valor de una propiedad del control.  
  
- Crear un <xref:System.Windows.Style> para el control.  
  
- Cree un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que le permiten cambiar el aspecto del control, como el <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button>. Puede establecer las propiedades de valor tanto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el código. El ejemplo siguiente se establece la <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, y <xref:System.Windows.Controls.Control.FontWeight%2A> propiedades en un <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le ofrece la capacidad de especificar la apariencia de controles de manera global, en lugar de establecer las propiedades en cada instancia de la aplicación, mediante la creación de un <xref:System.Windows.Style>. En el ejemplo siguiente se crea un <xref:System.Windows.Style> que se aplica a cada <xref:System.Windows.Controls.Button> en la aplicación. <xref:System.Windows.Style> las definiciones suelen definirse en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un <xref:System.Windows.ResourceDictionary>, como el <xref:System.Windows.FrameworkElement.Resources%2A> propiedad de la <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo solo a determinados controles de un tipo específico mediante la asignación de una clave al estilo y especifique esa clave en el `Style` propiedad del control.  Para obtener más información sobre los estilos, consulte [aplicar estilos y plantillas](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 Un <xref:System.Windows.Style> le permite establecer propiedades en varios controles a la vez, pero a veces desea personalizar la apariencia de un <xref:System.Windows.Controls.Control> más allá de lo que puede hacer mediante la creación de un <xref:System.Windows.Style>. Las clases que heredan de la <xref:System.Windows.Controls.Control> clase tiene un <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y la apariencia de un <xref:System.Windows.Controls.Control>. El <xref:System.Windows.Controls.Control.Template%2A> propiedad de un <xref:System.Windows.Controls.Control> es pública, por lo que puede dar un <xref:System.Windows.Controls.Control> un <xref:System.Windows.Controls.ControlTemplate> que es diferente del predeterminado. A menudo puede especificar un nuevo <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Control> en lugar de heredar de un control para personalizar la apariencia de un <xref:System.Windows.Controls.Control>.  
  
 Considere la posibilidad de los controles comunes, <xref:System.Windows.Controls.Button>.  El comportamiento primario de un <xref:System.Windows.Controls.Button> consiste en habilitar una aplicación para realizar alguna acción cuando el usuario hace clic en él.  De forma predeterminada, el <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, es posible que desee aprovechar las ventajas del comportamiento de un <xref:System.Windows.Controls.Button>: es decir, mediante el control del botón, haga clic en eventos, pero puede cambiar la apariencia del botón más allá de lo que puede hacer cambiando las propiedades del botón.  En este caso, puede crear un nuevo <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button>.  El <xref:System.Windows.Controls.ControlTemplate> crea un <xref:System.Windows.Controls.Button> con esquinas redondeadas y fondo degradado.  El <xref:System.Windows.Controls.ControlTemplate> contiene un <xref:System.Windows.Controls.Border> cuyo <xref:System.Windows.Controls.Border.Background%2A> es un <xref:System.Windows.Media.LinearGradientBrush> con dos <xref:System.Windows.Media.GradientStop> objetos.  La primera <xref:System.Windows.Media.GradientStop> usa el enlace de datos para enlazar el <xref:System.Windows.Media.GradientStop.Color%2A> propiedad de la <xref:System.Windows.Media.GradientStop> el color de fondo del botón.  Al establecer el <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.Button>, el color de ese valor se usará como el primer <xref:System.Windows.Media.GradientStop>. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md). El ejemplo también se crea un <xref:System.Windows.Trigger> que cambia la apariencia de la <xref:System.Windows.Controls.Button> cuando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  El <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.Button> debe establecerse en un <xref:System.Windows.Media.SolidColorBrush> para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse a eventos de un control mediante el uso [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código, pero solo puede controlar un evento en el código.  El ejemplo siguiente muestra cómo suscribirse a la `Click` eventos de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 El ejemplo siguiente se controla el `Click` eventos de un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de las clases que heredan de la <xref:System.Windows.Controls.Control> clase tiene la capacidad para incluir contenido enriquecido. Por ejemplo, un <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, un <xref:System.Windows.Controls.Image>, o un <xref:System.Windows.Controls.Panel>.  Las clases siguientes proporcionan compatibilidad con contenido enriquecido y actúan como clases base para la mayoría de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, y <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, y <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, y <xref:System.Windows.Controls.ToolBar>.  

 Para obtener más información acerca de estas clases base, vea [modelo de contenido de WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Agrupar controles por categoría](controls-by-category.md)
- [Biblioteca de controles](control-library.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Entrada](../advanced/input-wpf.md)
- [Habilitar un comando](../advanced/how-to-enable-a-command.md)
- [Tutoriales: Crear un botón animado personalizado](walkthroughs-create-a-custom-animated-button.md)
- [Control Customization](control-customization.md) (Personalización de controles)
