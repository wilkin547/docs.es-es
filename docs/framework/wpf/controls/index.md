---
title: Controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2aab0fc8adaf17a8e9820a6269a740ef09540cda
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646485"
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]se incluye con muchos de los componentes de interfaz <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label>de <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Menu>usuario comunes que se utilizan en casi todas las aplicaciones de Windows, como , , , y <xref:System.Windows.Controls.ListBox>. Históricamente, estos objetos se han denominado controles. Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el SDK sigue usando el término "control" para significar libremente cualquier clase que represente un objeto visible en <xref:System.Windows.Controls.Control> una aplicación, es importante tener en cuenta que una clase no necesita heredar de la clase para tener una presencia visible. Las clases <xref:System.Windows.Controls.Control> que heredan de la clase contienen un <xref:System.Windows.Controls.ControlTemplate>, lo que permite al consumidor de un control cambiar radicalmente la apariencia del control sin tener que crear una nueva subclase.  En este tema se describe cómo se <xref:System.Windows.Controls.Control> usan normalmente los controles (tanto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]los que heredan de la clase como los que no) en .  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede agregar un control a una [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] aplicación mediante código o mediante uno de ellos.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]etiquetas, dos cuadros de texto y dos botones, en . Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Por brevedad, la creación <xref:System.Windows.Controls.Grid> `grid1`de la , , se ha excluido de la muestra. `grid1`tiene las mismas definiciones de columna y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fila como se muestra en el ejemplo anterior.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
- Cambiar el valor de una propiedad del control.  
  
- Cree <xref:System.Windows.Style> a para el control.  
  
- Cree un <xref:System.Windows.Controls.ControlTemplate> nuevo para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que permiten cambiar la forma <xref:System.Windows.Controls.Control.Background%2A> en <xref:System.Windows.Controls.Button>que aparece el control, como el de un archivo . Puede establecer las propiedades [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de valor tanto en el código como en el código. En el ejemplo <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.FontSize%2A>siguiente <xref:System.Windows.Controls.Control.FontWeight%2A> se establecen las propiedades , , y en un <xref:System.Windows.Controls.Button> archivo in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le da la capacidad de especificar la apariencia de los controles al por <xref:System.Windows.Style>mayor, en lugar de establecer propiedades en cada instancia de la aplicación, mediante la creación de un archivo . En el ejemplo <xref:System.Windows.Style> siguiente se <xref:System.Windows.Controls.Button> crea un que se aplica a cada uno en la aplicación. <xref:System.Windows.Style>las definiciones se [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definen <xref:System.Windows.ResourceDictionary>normalmente <xref:System.Windows.FrameworkElement.Resources%2A> en un <xref:System.Windows.FrameworkElement>archivo , como la propiedad de la .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo solo a determinados controles de un tipo específico asignando una clave al estilo y especificando esa clave en la `Style` propiedad del control.  Para obtener más información acerca de los estilos, vea [Estilo y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 A <xref:System.Windows.Style> le permite establecer propiedades en varios controles a la vez, pero <xref:System.Windows.Controls.Control> a veces es <xref:System.Windows.Style>posible que desee personalizar la apariencia de un más allá de lo que puede hacer mediante la creación de un archivo . Las clases <xref:System.Windows.Controls.Control> que heredan de la clase tienen un <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y la apariencia de un <xref:System.Windows.Controls.Control>archivo . La <xref:System.Windows.Controls.Control.Template%2A> propiedad <xref:System.Windows.Controls.Control> de a es public, <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> por lo que puede dar un que es diferente de su valor predeterminado. A menudo puede <xref:System.Windows.Controls.ControlTemplate> especificar <xref:System.Windows.Controls.Control> un nuevo for a en lugar de <xref:System.Windows.Controls.Control>heredar de un control para personalizar la apariencia de un archivo .  
  
 Considere el control <xref:System.Windows.Controls.Button>muy común, .  El comportamiento principal <xref:System.Windows.Controls.Button> de a es permitir que una aplicación realice alguna acción cuando el usuario hace clic en ella.  De forma <xref:System.Windows.Controls.Button> predeterminada, el in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, es posible que desee aprovechar el comportamiento de un <xref:System.Windows.Controls.Button>-- es decir, controlando el evento click del botón), pero puede cambiar la apariencia del botón más allá de lo que puede hacer cambiando las propiedades del botón.  En este caso, puede <xref:System.Windows.Controls.ControlTemplate>crear un nuevo archivo .  
  
 En el ejemplo <xref:System.Windows.Controls.ControlTemplate> siguiente <xref:System.Windows.Controls.Button>se crea un for a .  Crea <xref:System.Windows.Controls.ControlTemplate> una <xref:System.Windows.Controls.Button> esquina con esquinas redondeadas y un fondo degradado.  Contiene <xref:System.Windows.Controls.ControlTemplate> un <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> cuyo <xref:System.Windows.Media.LinearGradientBrush> es <xref:System.Windows.Media.GradientStop> un con dos objetos.  El <xref:System.Windows.Media.GradientStop> primero usa el <xref:System.Windows.Media.GradientStop.Color%2A> enlace de <xref:System.Windows.Media.GradientStop> datos para enlazar la propiedad del al color del fondo del botón.  Al establecer <xref:System.Windows.Controls.Control.Background%2A> la propiedad <xref:System.Windows.Controls.Button>de la , el color de <xref:System.Windows.Media.GradientStop>ese valor se utilizará como el primer archivo . Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md). El ejemplo también <xref:System.Windows.Trigger> crea un que <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia `true`la apariencia de la cuando es .  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> La <xref:System.Windows.Controls.Control.Background%2A> propiedad <xref:System.Windows.Controls.Button> de la debe <xref:System.Windows.Media.SolidColorBrush> establecerse en un para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse al evento de un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control mediante código o uno, pero solo puede controlar un evento en el código.  En el ejemplo siguiente se `Click` muestra <xref:System.Windows.Controls.Button>cómo suscribirse al evento de un archivo .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo `Click` siguiente <xref:System.Windows.Controls.Button>se controla el evento de un archivo .  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de <xref:System.Windows.Controls.Control> las clases que heredan de la clase tienen la capacidad de contener contenido enriquecido. Por ejemplo, <xref:System.Windows.Controls.Label> a puede contener cualquier objeto, <xref:System.Windows.Controls.Image>como <xref:System.Windows.Controls.Panel>una cadena, un , o un archivo .  Las clases siguientes proporcionan compatibilidad con contenido enriquecido y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]actúan como clases base para la mayoría de los controles de .  
  
- <xref:System.Windows.Controls.ContentControl>-- Algunos ejemplos de clases <xref:System.Windows.Controls.Label>que <xref:System.Windows.Controls.Button>heredan de esta clase son , , y <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>-- Algunos ejemplos de clases <xref:System.Windows.Controls.ListBox>que <xref:System.Windows.Controls.Menu>heredan de esta clase son , , y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- Algunos ejemplos de clases <xref:System.Windows.Controls.TabItem>que <xref:System.Windows.Controls.GroupBox>heredan de esta clase son , , y <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.TreeViewItem>heredan <xref:System.Windows.Controls.ToolBar>de esta clase son , , y .  

 Para obtener más información acerca de estas clases base, vea [WPF Content Model](wpf-content-model.md).  
  
## <a name="see-also"></a>Consulte también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Agrupar controles por categoría](controls-by-category.md)
- [Biblioteca de controles](control-library.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Entrada](../advanced/input-wpf.md)
- [Habilitar un comando](../advanced/how-to-enable-a-command.md)
- [Tutoriales: Crear un botón animado personalizado](walkthroughs-create-a-custom-animated-button.md)
- [Personalización de controles](control-customization.md)
