---
title: Información general sobre alineación, márgenes y relleno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145480"
---
# <a name="alignment-margins-and-padding-overview"></a>Información general sobre alineación, márgenes y relleno
La <xref:System.Windows.FrameworkElement> clase expone varias propiedades que se utilizan para colocar con precisión los elementos secundarios. En este tema se describen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>cuatro <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>de <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>las propiedades más importantes: , , , y . Es importante comprender los efectos de estas propiedades, ya que proporcionan la base para controlar la posición de los elementos de las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Introducción al posicionamiento de elementos  
 Existen numerosas maneras de posicionar elementos mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Sin embargo, lograr un diseño <xref:System.Windows.Controls.Panel> ideal va más allá de simplemente elegir el elemento correcto. El control preciso del posicionamiento <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>requiere <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>una <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> comprensión de las propiedades , , , y.  
  
 La siguiente ilustración muestra un escenario de diseño que usa varias propiedades de posicionamiento.  
  
 ![Ejemplo WPF Positioning Properties](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 A primera vista, los <xref:System.Windows.Controls.Button> elementos de esta ilustración pueden parecer colocados aleatoriamente. Sin embargo, sus posiciones se controlan realmente de forma precisa mediante una combinación de márgenes, alineaciones y relleno.  
  
 En el ejemplo siguiente se describe cómo crear el diseño de la ilustración anterior. Un <xref:System.Windows.Controls.Border> elemento encapsula <xref:System.Windows.Controls.StackPanel>un elemento <xref:System.Windows.Controls.Border.Padding%2A> primario, con un valor de 15 píxeles independientes del dispositivo. Esto explica la <xref:System.Windows.Media.Brushes.LightBlue%2A> banda estrecha que <xref:System.Windows.Controls.StackPanel>rodea al niño. Elementos secundarios <xref:System.Windows.Controls.StackPanel> de la se utilizan para ilustrar cada una de las diversas propiedades de posicionamiento que se detallan en este tema. Se <xref:System.Windows.Controls.Button> utilizan tres elementos <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> para demostrar las propiedades y.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 En el siguiente diagrama se proporciona una vista de primer plano de las distintas propiedades de posicionamiento que se usan en el ejemplo anterior. En las siguientes secciones de este tema se describe con más detalle cómo usar cada propiedad de posicionamiento.  
  
 ![Propiedades de posicionamiento con salidas de&#45;de llamadas de pantalla](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Explicación de las propiedades Alignment  
 Las <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedades y describen cómo se debe colocar un elemento secundario dentro del espacio de diseño asignado de un elemento primario. Al usar estas propiedades juntas, puede posicionar los elementos secundarios con precisión. Por ejemplo, los <xref:System.Windows.Controls.DockPanel> elementos secundarios de a <xref:System.Windows.HorizontalAlignment.Left> <xref:System.Windows.HorizontalAlignment.Right>pueden <xref:System.Windows.HorizontalAlignment.Center>especificar cuatro <xref:System.Windows.HorizontalAlignment.Stretch> alineaciones horizontales diferentes: , , o , o para rellenar el espacio disponible. Para el posicionamiento vertical existen valores similares.  
  
> [!NOTE]
> Las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> set explícitamente de <xref:System.Windows.HorizontalAlignment.Stretch> un elemento tienen prioridad sobre el valor de propiedad. Intentar establecer <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y `Stretch` un valor `Stretch` de resultados en los resultados de la solicitud que se omite.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>Propiedad HorizontalAlignment  
 La <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad declara las características de alineación horizontal que se aplicarán a los elementos secundarios. En la tabla siguiente se muestra <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> cada uno de los valores posibles de la propiedad.  
  
|Member|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Los elementos secundarios se alinean a la izquierda del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Los elementos secundarios se alinean en el centro del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Los elementos secundarios se alinean a la derecha del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Valor predeterminado)|Los elementos secundarios se ajustan para rellenar el espacio de diseño asignado del elemento primario. Los <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valores explícitos y los valores tienen prioridad.|  
  
 En el ejemplo siguiente <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> se <xref:System.Windows.Controls.Button> muestra cómo aplicar la propiedad a los elementos. Se muestran todos los valores de atributo para ilustrar mejor los distintos comportamientos de representación.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 El código anterior produce un diseño similar al de la siguiente imagen. Los efectos de <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> posicionamiento de cada valor son visibles en la ilustración.  
  
 ![Ejemplo HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>Propiedad VerticalAlignment  
 La <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad describe las características de alineación vertical que se aplican a los elementos secundarios. En la tabla siguiente se muestra <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> cada uno de los valores posibles para la propiedad.  
  
|Member|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Los elementos secundarios se alinean en la parte superior del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment.Center>|Los elementos secundarios se alinean en el centro del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Los elementos secundarios se alinean en la parte inferior del espacio de diseño asignado del elemento primario.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Valor predeterminado)|Los elementos secundarios se ajustan para rellenar el espacio de diseño asignado del elemento primario. Los <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valores explícitos y los valores tienen prioridad.|  
  
 En el ejemplo siguiente <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> se <xref:System.Windows.Controls.Button> muestra cómo aplicar la propiedad a los elementos. Se muestran todos los valores de atributo para ilustrar mejor los distintos comportamientos de representación. Para los fines de <xref:System.Windows.Controls.Grid> este ejemplo, un elemento con líneas de cuadrícula visibles se utiliza como elemento primario, para ilustrar mejor el comportamiento de diseño de cada valor de propiedad.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 El código anterior produce un diseño similar al de la siguiente imagen. Los efectos de <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> posicionamiento de cada valor son visibles en la ilustración.  
  
 ![Ejemplo de propiedad VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Explicación de las propiedades Margin  
 La <xref:System.Windows.FrameworkElement.Margin%2A> propiedad describe la distancia entre un elemento y sus elementos secundarios o pares. <xref:System.Windows.FrameworkElement.Margin%2A>valores pueden ser uniformes, `Margin="20"`mediante el uso de sintaxis como . Con esta sintaxis, se aplicaría un uniforme <xref:System.Windows.FrameworkElement.Margin%2A> de 20 píxeles independientes del dispositivo al elemento. <xref:System.Windows.FrameworkElement.Margin%2A>los valores también pueden tomar la forma de cuatro valores distintos, cada uno de los valores que `Margin="0,10,5,25"`describe un margen distinto para aplicar a la izquierda, superior, derecha e inferior (en ese orden), como . El uso <xref:System.Windows.FrameworkElement.Margin%2A> adecuado de la propiedad permite un control muy preciso de la posición de representación de un elemento y la posición de representación de sus elementos vecinos y elementos secundarios.  
  
> [!NOTE]
> Un margen distinto de cero aplica <xref:System.Windows.FrameworkElement.ActualWidth%2A> espacio <xref:System.Windows.FrameworkElement.ActualHeight%2A>fuera del elemento y .  
  
 En el ejemplo siguiente se muestra cómo <xref:System.Windows.Controls.Button> aplicar márgenes uniformes alrededor de un grupo de elementos. Los <xref:System.Windows.Controls.Button> elementos se espacian uniformemente con un búfer de margen de diez píxeles en cada dirección.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 En muchos casos, un margen uniforme no resulta apropiado. En estos casos, se puede aplicar un espaciado no uniforme. En el ejemplo siguiente se muestra cómo aplicar un espaciado de margen no uniforme a los elementos secundarios. Los márgenes se describen en este orden: izquierdo, superior, derecho e inferior.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>
## <a name="understanding-the-padding-property"></a>Descripción de la propiedad Padding  
 El relleno <xref:System.Windows.FrameworkElement.Margin%2A> es similar en la mayoría de los aspectos. El Padding propiedad se expone en sólo en unas <xref:System.Windows.Documents.Block> <xref:System.Windows.Controls.Border>pocas <xref:System.Windows.Controls.Control>clases, principalmente como una conveniencia: , , , y <xref:System.Windows.Controls.TextBlock> son ejemplos de clases que exponen un Padding propiedad. La <xref:System.Windows.Controls.Border.Padding%2A> propiedad amplía el tamaño efectivo de un <xref:System.Windows.Thickness> elemento secundario por el valor especificado.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Border.Padding%2A> se <xref:System.Windows.Controls.Border> muestra cómo aplicar a un elemento primario.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Uso de las propiedades Alignment, Margin y Padding en una aplicación  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , y proporcione el control [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]de posicionamiento necesario para crear un complejo . Puede usar los efectos de cada propiedad para cambiar el posicionamiento de los elementos secundarios, lo que ofrece flexibilidad en la creación de aplicaciones dinámicas y experiencias de usuario.  
  
 En el ejemplo siguiente se muestra cada uno de los conceptos que se detallan en este tema. Basándose en la infraestructura que se encuentra en el <xref:System.Windows.Controls.Grid> primer ejemplo de <xref:System.Windows.Controls.Border> este tema, en este ejemplo se agrega un elemento como elemento secundario del primer ejemplo. <xref:System.Windows.Controls.Border.Padding%2A>se aplica al <xref:System.Windows.Controls.Border> elemento primario. Se <xref:System.Windows.Controls.Grid> utiliza para dividir el <xref:System.Windows.Controls.StackPanel> espacio entre tres elementos secundarios. <xref:System.Windows.Controls.Button>elementos se utilizan de nuevo <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>para mostrar los diversos efectos de y . <xref:System.Windows.Controls.TextBlock>se agregan elementos a cada uno <xref:System.Windows.Controls.ColumnDefinition> para <xref:System.Windows.Controls.Button> definir mejor las distintas propiedades aplicadas a los elementos de cada columna.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Cuando se compila, la aplicación anterior produce una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] similar a la de la siguiente ilustración. Los efectos de los distintos valores de propiedad son evidentes en el <xref:System.Windows.Controls.TextBlock> espaciado entre elementos y los valores de propiedad significativos para los elementos de cada columna se muestran dentro de los elementos.  
  
 ![Varias propiedades de posición en una aplicación](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Pasos siguientes  
 Las propiedades de <xref:System.Windows.FrameworkElement> posicionamiento definidas por la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clase permiten un control preciso de la colocación de elementos dentro de las aplicaciones. Ahora dispone de varias técnicas que puede usar para posicionar mejor los elementos mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Existen recursos adicionales que explican el diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con mayor detalle. El tema Información general sobre paneles <xref:System.Windows.Controls.Panel> contiene más [detalles](../controls/panels-overview.md) sobre los distintos elementos. El tema [Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md) de escritorio WPFWPF presenta técnicas avanzadas que usan elementos de diseño para colocar componentes y enlazar sus acciones a orígenes de datos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Información general sobre elementos Panel](../controls/panels-overview.md)
- [Diseño](layout.md)
- [Ejemplo WPF Layout Gallery](https://go.microsoft.com/fwlink/?LinkID=160054)
