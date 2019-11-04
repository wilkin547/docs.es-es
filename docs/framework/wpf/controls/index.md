---
title: Controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 42596c8adf1b8b27f250fa7a3cf6cc173a63e2eb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459450"
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] incluye muchos de los componentes de interfaz de usuario comunes que se usan en casi todas las aplicaciones de Windows, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>y <xref:System.Windows.Controls.ListBox>. Históricamente, estos objetos se han denominado controles. Aunque el SDK de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sigue usando el término "control" para referirse a cualquier clase que represente un objeto visible en una aplicación, es importante tener en cuenta que una clase no necesita heredar de la clase <xref:System.Windows.Controls.Control> para tener una presencia visible. Las clases que heredan de la clase <xref:System.Windows.Controls.Control> contienen un <xref:System.Windows.Controls.ControlTemplate>, que permite al consumidor de un control cambiar radicalmente la apariencia del control sin tener que crear una nueva subclase.  En este tema se describe cómo se utilizan normalmente los controles (tanto los que heredan de la clase <xref:System.Windows.Controls.Control> como los que no) en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede Agregar un control a una aplicación mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos etiquetas, dos cuadros de texto y dos botones, en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Por motivos de brevedad, la creación de la <xref:System.Windows.Controls.Grid>, `grid1`, se ha excluido del ejemplo. `grid1` tiene las mismas definiciones de columna y fila que se muestran en el ejemplo anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
- Cambiar el valor de una propiedad del control.  
  
- Cree un <xref:System.Windows.Style> para el control.  
  
- Cree un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que le permiten cambiar el modo en que aparece el control, como el <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button>. Puede establecer las propiedades de valor en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en el código. En el ejemplo siguiente se establecen las propiedades <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>y <xref:System.Windows.Controls.Control.FontWeight%2A> en un <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece la posibilidad de especificar la apariencia de los controles de forma mayorista, en lugar de establecer las propiedades en cada instancia de la aplicación mediante la creación de un <xref:System.Windows.Style>. En el ejemplo siguiente se crea un <xref:System.Windows.Style> que se aplica a cada <xref:System.Windows.Controls.Button> de la aplicación. las definiciones de <xref:System.Windows.Style> se definen normalmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un <xref:System.Windows.ResourceDictionary>, como la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> del <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo a ciertos controles de un tipo específico asignando una clave al estilo y especificando esa clave en la `Style` propiedad del control.  Para obtener más información sobre los estilos, vea [aplicar estilos y plantillas](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 Una <xref:System.Windows.Style> permite establecer propiedades en varios controles a la vez, pero en ocasiones puede ser conveniente personalizar la apariencia de un <xref:System.Windows.Controls.Control> más allá de lo que se puede hacer creando una <xref:System.Windows.Style>. Las clases que heredan de la clase <xref:System.Windows.Controls.Control> tienen un <xref:System.Windows.Controls.ControlTemplate>, que define la estructura y la apariencia de una <xref:System.Windows.Controls.Control>. La propiedad <xref:System.Windows.Controls.Control.Template%2A> de una <xref:System.Windows.Controls.Control> es pública, por lo que puede asignar a una <xref:System.Windows.Controls.Control> un <xref:System.Windows.Controls.ControlTemplate> que sea diferente de su valor predeterminado. A menudo, se puede especificar un nuevo <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Control> en lugar de heredar de un control para personalizar la apariencia de un <xref:System.Windows.Controls.Control>.  
  
 Tenga en cuenta el control muy común <xref:System.Windows.Controls.Button>.  El comportamiento principal de un <xref:System.Windows.Controls.Button> es permitir que una aplicación realice alguna acción cuando el usuario hace clic en él.  De forma predeterminada, el <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, es posible que quiera aprovechar el comportamiento de un <xref:System.Windows.Controls.Button>, es decir, controlar el evento click del botón, pero puede cambiar la apariencia del botón más allá de lo que puede hacer si cambia las propiedades del botón.  En este caso, puede crear un nuevo <xref:System.Windows.Controls.ControlTemplate>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button>.  El <xref:System.Windows.Controls.ControlTemplate> crea un <xref:System.Windows.Controls.Button> con esquinas redondeadas y un fondo degradado.  El <xref:System.Windows.Controls.ControlTemplate> contiene una <xref:System.Windows.Controls.Border> cuya <xref:System.Windows.Controls.Border.Background%2A> es una <xref:System.Windows.Media.LinearGradientBrush> con dos objetos <xref:System.Windows.Media.GradientStop>.  La primera <xref:System.Windows.Media.GradientStop> utiliza el enlace de datos para enlazar la propiedad <xref:System.Windows.Media.GradientStop.Color%2A> de la <xref:System.Windows.Media.GradientStop> al color del fondo del botón.  Cuando establezca la propiedad <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button>, el color de ese valor se utilizará como primer <xref:System.Windows.Media.GradientStop>. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md). En el ejemplo también se crea un <xref:System.Windows.Trigger> que cambia la apariencia del <xref:System.Windows.Controls.Button> cuando se `true`<xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A>.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> La propiedad <xref:System.Windows.Controls.Control.Background%2A> de la <xref:System.Windows.Controls.Button> debe establecerse en un <xref:System.Windows.Media.SolidColorBrush> para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse al evento de un control mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o código, pero solo puede controlar un evento en el código.  En el ejemplo siguiente se muestra cómo suscribirse al evento `Click` de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo siguiente se controla el evento de `Click` de una <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de las clases que heredan de la clase <xref:System.Windows.Controls.Control> tienen la capacidad de incluir contenido enriquecido. Por ejemplo, un <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, un <xref:System.Windows.Controls.Image>o un <xref:System.Windows.Controls.Panel>.  Las siguientes clases proporcionan compatibilidad con contenido enriquecido y actúan como clases base para la mayoría de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>y <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>y <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>y <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>: algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>y <xref:System.Windows.Controls.ToolBar>.  

 Para obtener más información sobre estas clases base, vea [modelo de contenido de WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Agrupar controles por categoría](controls-by-category.md)
- [Biblioteca de controles](control-library.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Entrada](../advanced/input-wpf.md)
- [Habilitar un comando](../advanced/how-to-enable-a-command.md)
- [Tutoriales: Crear un botón animado personalizado](walkthroughs-create-a-custom-animated-button.md)
- [Control Customization](control-customization.md) (Personalización de controles)
