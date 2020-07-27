---
title: Controles
description: Obtenga información sobre Windows Presentation Foundation componentes comunes de la interfaz de usuario, denominados controles, pero que podrían no heredar de la clase control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: c3d9d3a38cf5f84e21df195e113e264e5a4ac025
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165842"
---
# <a name="controls"></a>Controles
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]se suministra con muchos de los componentes de interfaz de usuario comunes que se usan en casi todas las aplicaciones de Windows, como,,, <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Menu> y <xref:System.Windows.Controls.ListBox> . Históricamente, estos objetos se han denominado controles. Aunque el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK sigue usando el término "control" para referirse a cualquier clase que represente un objeto visible en una aplicación, es importante tener en cuenta que una clase no necesita heredar de la <xref:System.Windows.Controls.Control> clase para tener una presencia visible. Las clases que heredan de la clase <xref:System.Windows.Controls.Control> contienen un objeto <xref:System.Windows.Controls.ControlTemplate>, lo que permite al consumidor de un control cambiar radicalmente el aspecto de este sin tener que crear una nueva subclase.  En este tema se describe cómo se usan habitualmente los controles (tanto los que heredan de la <xref:System.Windows.Controls.Control> clase como los que no) [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Creación de una instancia de un control  
 Puede Agregar un control a una aplicación mediante el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código o.  En el ejemplo siguiente se muestra cómo crear una aplicación simple que pide al usuario su nombre y su apellido.  En este ejemplo se crean seis controles: dos etiquetas, dos cuadros de texto y dos botones, en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Todos los controles se pueden crear de igual forma.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente se crea la misma aplicación mediante código. Por motivos de brevedad, la creación de <xref:System.Windows.Controls.Grid> ,, se ha `grid1` excluido del ejemplo. `grid1`tiene las mismas definiciones de columnas y filas que las que se muestran en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo anterior.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Cambio de la apariencia de un control  
 Es común cambiar la apariencia de un control para ajustarlo a la apariencia de la aplicación. Puede cambiar la apariencia de un control mediante una de las acciones siguientes, dependiendo de lo que desea realizar:  
  
- Cambiar el valor de una propiedad del control.  
  
- Cree un <xref:System.Windows.Style> para el control.  
  
- Cree un nuevo <xref:System.Windows.Controls.ControlTemplate> para el control.  
  
### <a name="changing-a-controls-property-value"></a>Cambiar el valor de propiedad de un control  
 Muchos controles tienen propiedades que le permiten cambiar el modo en que aparece el control, como el <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button> . Puede establecer las propiedades de valor en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] código y. En el ejemplo siguiente se establecen las <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.FontSize%2A> propiedades, y <xref:System.Windows.Controls.Control.FontWeight%2A> en un <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 En el ejemplo siguiente se establecen las mismas propiedades mediante código.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Crear un estilo para un control  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le ofrece la posibilidad de especificar la apariencia de los controles de forma mayorista, en lugar de establecer las propiedades en cada instancia de la aplicación, mediante la creación de un <xref:System.Windows.Style> . En el ejemplo siguiente se crea un <xref:System.Windows.Style> que se aplica a cada <xref:System.Windows.Controls.Button> en la aplicación. <xref:System.Windows.Style>las definiciones se definen normalmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en <xref:System.Windows.ResourceDictionary> , como la <xref:System.Windows.FrameworkElement.Resources%2A> propiedad de <xref:System.Windows.FrameworkElement> .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 También puede aplicar un estilo a ciertos controles de un tipo específico asignando una clave al estilo y especificando esa clave en la `Style` propiedad del control.  Para más información acerca de los estilos, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
### <a name="creating-a-controltemplate"></a>Creación de una plantilla de control  
 <xref:System.Windows.Style>Permite establecer propiedades en varios controles a la vez, pero a veces es posible que desee personalizar la apariencia de una <xref:System.Windows.Controls.Control> más allá de lo que se puede hacer creando un <xref:System.Windows.Style> . Las clases que heredan de la <xref:System.Windows.Controls.Control> clase tienen un <xref:System.Windows.Controls.ControlTemplate> , que define la estructura y la apariencia de <xref:System.Windows.Controls.Control> . La <xref:System.Windows.Controls.Control.Template%2A> propiedad de <xref:System.Windows.Controls.Control> es pública, por lo que puede proporcionar un <xref:System.Windows.Controls.Control> objeto <xref:System.Windows.Controls.ControlTemplate> que sea diferente de su valor predeterminado. A menudo, se puede especificar un nuevo <xref:System.Windows.Controls.ControlTemplate> para un en <xref:System.Windows.Controls.Control> lugar de heredar de un control para personalizar la apariencia de un <xref:System.Windows.Controls.Control> .  
  
 Tenga en cuenta el control muy común, <xref:System.Windows.Controls.Button> .  El comportamiento principal de un <xref:System.Windows.Controls.Button> es permitir que una aplicación realice alguna acción cuando el usuario hace clic en él.  De forma predeterminada, <xref:System.Windows.Controls.Button> en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparece como un rectángulo elevado.  Al desarrollar una aplicación, es posible que quiera aprovechar el comportamiento de una, es <xref:System.Windows.Controls.Button> decir, controlar el evento de clic del botón, pero puede cambiar la apariencia del botón más allá de lo que puede hacer si cambia las propiedades del botón.  En este caso, puede crear un nuevo <xref:System.Windows.Controls.ControlTemplate> .  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Button> .  <xref:System.Windows.Controls.ControlTemplate>Crea un <xref:System.Windows.Controls.Button> con esquinas redondeadas y un fondo degradado.  <xref:System.Windows.Controls.ControlTemplate>Contiene un <xref:System.Windows.Controls.Border> cuya <xref:System.Windows.Controls.Border.Background%2A> es un <xref:System.Windows.Media.LinearGradientBrush> con dos <xref:System.Windows.Media.GradientStop> objetos.  El primero <xref:System.Windows.Media.GradientStop> usa el enlace de datos para enlazar la <xref:System.Windows.Media.GradientStop.Color%2A> propiedad del <xref:System.Windows.Media.GradientStop> al color del fondo del botón.  Al establecer la <xref:System.Windows.Controls.Control.Background%2A> propiedad de <xref:System.Windows.Controls.Button> , el color de ese valor se utilizará como primer <xref:System.Windows.Media.GradientStop> . Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md). En el ejemplo también se crea un <xref:System.Windows.Trigger> que cambia la apariencia de <xref:System.Windows.Controls.Button> cuando <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> es `true` .  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> La <xref:System.Windows.Controls.Control.Background%2A> propiedad de <xref:System.Windows.Controls.Button> debe establecerse en <xref:System.Windows.Media.SolidColorBrush> para que el ejemplo funcione correctamente.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Puede suscribirse al evento de un control mediante o el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] código, pero solo puede controlar un evento en el código.  En el ejemplo siguiente se muestra cómo suscribirse al `Click` evento de un <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 En el ejemplo siguiente se controla el `Click` evento de un <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Contenido enriquecido en los controles  
 La mayoría de las clases que heredan de la <xref:System.Windows.Controls.Control> clase tienen la capacidad de incluir contenido enriquecido. Por ejemplo, un <xref:System.Windows.Controls.Label> puede contener cualquier objeto, como una cadena, <xref:System.Windows.Controls.Image> o <xref:System.Windows.Controls.Panel> .  Las siguientes clases proporcionan compatibilidad con contenido enriquecido y actúan como clases base para la mayoría de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  
  
- <xref:System.Windows.Controls.ContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.ToolTip> .  
  
- <xref:System.Windows.Controls.ItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.Menu> y <xref:System.Windows.Controls.Primitives.StatusBar> .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.TabItem> , <xref:System.Windows.Controls.GroupBox> y <xref:System.Windows.Controls.Expander> .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Algunos ejemplos de clases que heredan de esta clase son <xref:System.Windows.Controls.MenuItem> , <xref:System.Windows.Controls.TreeViewItem> y <xref:System.Windows.Controls.ToolBar> .  

 Para obtener más información sobre estas clases base, vea [modelo de contenido de WPF](wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Agrupar controles por categoría](controls-by-category.md)
- [Biblioteca de controles](control-library.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Entrada](../advanced/input-wpf.md)
- [Habilitar un comando](../advanced/how-to-enable-a-command.md)
- [Tutoriales: Crear un botón animado personalizado](walkthroughs-create-a-custom-animated-button.md)
- [Personalización de controles](control-customization.md)
