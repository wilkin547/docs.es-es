---
title: Controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: faa1fbad85acf5788c10de7750c6a7c32b535bf5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957030"
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]se suministra con muchos de los componentes de interfaz de usuario comunes que se usan en casi todas las <xref:System.Windows.Controls.Button>aplicaciones de <xref:System.Windows.Controls.TextBox>Windows <xref:System.Windows.Controls.Menu>, como <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Label>,, y. Históricamente, estos objetos se han denominado controles. Aunque el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK sigue usando el término "control" para referirse a cualquier clase que represente un objeto visible en una aplicación, es importante tener en cuenta que una clase no necesita heredar de la <xref:System.Windows.Controls.Control> clase para tener una presencia visible. Las clases que heredan <xref:System.Windows.Controls.Control> de la clase <xref:System.Windows.Controls.ControlTemplate>contienen un, que permite al consumidor de un control cambiar radicalmente la apariencia del control sin tener que crear una nueva subclase.  <xref:System.Windows.Controls.Control> En[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]este tema se describe cómo se usan habitualmente los controles (tanto los que heredan de la clase como los que no).  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede Agregar un control a una aplicación [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mediante el código o.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos etiquetas, dos cuadros de texto y dos botones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], en. Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Por motivos de brevedad, la creación <xref:System.Windows.Controls.Grid>de `grid1`,, se ha excluido del ejemplo. `grid1`tiene las mismas definiciones de columnas y filas que las que se [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] muestran en el ejemplo anterior.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
- Cambiar el valor de una propiedad del control.  
  
- Cree un <xref:System.Windows.Style> para el control.  
  
- Cree un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que le permiten cambiar el modo en que aparece el control, como <xref:System.Windows.Controls.Control.Background%2A> el de <xref:System.Windows.Controls.Button>un. Puede establecer las propiedades de valor en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] el código y. En el ejemplo siguiente se <xref:System.Windows.Controls.Control.Background%2A>establecen <xref:System.Windows.Controls.Control.FontSize%2A>las propiedades <xref:System.Windows.Controls.Control.FontWeight%2A> , y en <xref:System.Windows.Controls.Button> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]de.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le ofrece la posibilidad de especificar la apariencia de los controles de forma mayorista, en lugar de establecer las propiedades en cada instancia de la aplicación <xref:System.Windows.Style>, mediante la creación de un. En el ejemplo siguiente se <xref:System.Windows.Style> crea un que se aplica <xref:System.Windows.Controls.Button> a cada en la aplicación. <xref:System.Windows.Style>las definiciones se definen normalmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en <xref:System.Windows.ResourceDictionary>en, como la <xref:System.Windows.FrameworkElement.Resources%2A> propiedad de <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo a ciertos controles de un tipo específico asignando una clave al estilo y especificando esa clave en la `Style` propiedad del control.  Para obtener más información sobre los estilos, vea [aplicar estilos y plantillas](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 Permite establecer propiedades en varios controles a la vez, pero a veces es posible que desee personalizar la apariencia de una <xref:System.Windows.Controls.Control> más allá de lo que se puede hacer creando un <xref:System.Windows.Style>. <xref:System.Windows.Style> Las clases que heredan <xref:System.Windows.Controls.Control> de la clase <xref:System.Windows.Controls.ControlTemplate>tienen un, que define la <xref:System.Windows.Controls.Control>estructura y la apariencia de. La <xref:System.Windows.Controls.Control.Template%2A> propiedad <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> de es pública, por lo que puede proporcionar un objeto que sea diferente de su valor predeterminado. <xref:System.Windows.Controls.Control> A menudo, se puede especificar <xref:System.Windows.Controls.ControlTemplate> un nuevo <xref:System.Windows.Controls.Control> para un en lugar de heredar de un control para personalizar la apariencia <xref:System.Windows.Controls.Control>de un.  
  
 Tenga en cuenta el control muy <xref:System.Windows.Controls.Button>común,.  El comportamiento principal de un <xref:System.Windows.Controls.Button> es permitir que una aplicación realice alguna acción cuando el usuario hace clic en él.  <xref:System.Windows.Controls.Button> De forma predeterminada, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, es posible que quiera aprovechar el comportamiento de una <xref:System.Windows.Controls.Button>, es decir, controlar el evento de clic del botón, pero puede cambiar la apariencia del botón más allá de lo que puede hacer si cambia las propiedades del botón.  En este caso, puede crear un nuevo <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.ControlTemplate> crea un <xref:System.Windows.Controls.Button>para un.  <xref:System.Windows.Controls.ControlTemplate> Crea un<xref:System.Windows.Controls.Button> con esquinas redondeadas y un fondo degradado.  <xref:System.Windows.Controls.ControlTemplate> Contiene un <xref:System.Windows.Controls.Border> cuya es<xref:System.Windows.Controls.Border.Background%2A> un con<xref:System.Windows.Media.LinearGradientBrush> dos<xref:System.Windows.Media.GradientStop> objetos.  El primero <xref:System.Windows.Media.GradientStop> usa el enlace de datos para <xref:System.Windows.Media.GradientStop.Color%2A> enlazar la <xref:System.Windows.Media.GradientStop> propiedad del al color del fondo del botón.  Al establecer la <xref:System.Windows.Controls.Control.Background%2A> propiedad <xref:System.Windows.Controls.Button>de, el color de ese valor se utilizará como primer <xref:System.Windows.Media.GradientStop>. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md). En el ejemplo también se <xref:System.Windows.Trigger> crea un que cambia la apariencia <xref:System.Windows.Controls.Button> de <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cuando `true`es.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> La <xref:System.Windows.Controls.Control.Background%2A> propiedad <xref:System.Windows.Controls.Button> de debeestablecerseenparaqueel<xref:System.Windows.Media.SolidColorBrush> ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse al evento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de un control mediante o el código, pero solo puede controlar un evento en el código.  En el ejemplo siguiente se muestra cómo suscribirse `Click` al evento de <xref:System.Windows.Controls.Button>un.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo siguiente se `Click` controla el evento <xref:System.Windows.Controls.Button>de un.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de las clases que <xref:System.Windows.Controls.Control> heredan de la clase tienen la capacidad de incluir contenido enriquecido. Por ejemplo, un <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena <xref:System.Windows.Controls.Image>, o <xref:System.Windows.Controls.Panel>.  Las siguientes clases proporcionan compatibilidad con contenido enriquecido y actúan como clases base para la mayoría de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]de.  
  
- <xref:System.Windows.Controls.ContentControl>--Algunos ejemplos de clases que heredan de esta clase <xref:System.Windows.Controls.Label>son <xref:System.Windows.Controls.Button>, y <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>--Algunos ejemplos de clases que heredan de esta clase <xref:System.Windows.Controls.ListBox>son <xref:System.Windows.Controls.Menu>, y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--Algunos ejemplos de clases que heredan de esta clase <xref:System.Windows.Controls.TabItem>son <xref:System.Windows.Controls.GroupBox>, y <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que heredan de esta clase <xref:System.Windows.Controls.MenuItem>son <xref:System.Windows.Controls.TreeViewItem>, y <xref:System.Windows.Controls.ToolBar>.  

 Para obtener más información sobre estas clases base, vea [modelo de contenido de WPF](wpf-content-model.md).  
  
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
