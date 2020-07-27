---
title: Información general sobre elementos Panel
description: Windows Presentation Foundation proporciona elementos de panel predefinidos que controlan la representación de los elementos. Obtenga información sobre cómo crear elementos de panel personalizados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 7f3f6948de28f50dc6470a7dfc1a5bad67e57c79
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167773"
---
# <a name="panels-overview"></a>Información general sobre elementos Panel
<xref:System.Windows.Controls.Panel>los elementos son componentes que controlan la representación de los elementos, su tamaño y dimensiones, su posición y la disposición de su contenido secundario. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Proporciona una serie de elementos predefinidos, así como <xref:System.Windows.Controls.Panel> la capacidad de construir <xref:System.Windows.Controls.Panel> elementos personalizados.  
  
 En este tema se incluyen las siguientes secciones.  
  
- [La clase Panel](#Panels_view_from_10000_feet)  
  
- [Miembros comunes del elemento Panel](#Panels_declared_members)  
  
- [Elementos Panel derivados](#Panels_derived_elements)  
  
- [Paneles de interfaz de usuario](#Panels_main_UI_elements)  
  
- [Elementos Panel anidados](#Panels_nested_panel_elements)  
  
- [Elementos Panel personalizados](#Panels_custom_panel_elements)  
  
- [Compatibilidad para la localización y globalización](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>
## <a name="the-panel-class"></a>La clase Panel  
 <xref:System.Windows.Controls.Panel>es la clase base para todos los elementos que proporcionan compatibilidad de diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . <xref:System.Windows.Controls.Panel>Los elementos derivados se usan para colocar y organizar los elementos en el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código y.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un conjunto completo de implementaciones de panel derivadas que permiten numerosos diseños complejos. Estas clases derivadas exponen propiedades y métodos que habilitan la mayoría de los escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] estándar. Los desarrolladores que no pueden encontrar un comportamiento de organización secundario que satisfaga sus necesidades pueden crear nuevos diseños invalidando los <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos y. Para más información sobre los comportamientos de diseño personalizados, consulte [Elementos Panel personalizados](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Miembros comunes del elemento Panel  
 Todos los <xref:System.Windows.Controls.Panel> elementos admiten las propiedades base de ajuste de tamaño y posición definidas por <xref:System.Windows.FrameworkElement> , incluidos <xref:System.Windows.FrameworkElement.Height%2A> ,, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> , <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , <xref:System.Windows.FrameworkElement.Margin%2A> y <xref:System.Windows.FrameworkElement.LayoutTransform%2A> . Para obtener información adicional sobre las propiedades de posicionamiento definidas por <xref:System.Windows.FrameworkElement> , consulte [información general sobre alineación, márgenes y relleno](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>expone propiedades adicionales que son de importancia crítica para comprender y usar el diseño. La <xref:System.Windows.Controls.Panel.Background%2A> propiedad se usa para rellenar el área entre los límites de un elemento de panel derivado con <xref:System.Windows.Media.Brush> . <xref:System.Windows.Controls.Panel.Children%2A>representa la colección secundaria de elementos de la que <xref:System.Windows.Controls.Panel> se compone. <xref:System.Windows.Controls.Panel.InternalChildren%2A>representa el contenido de la <xref:System.Windows.Controls.Panel.Children%2A> colección más los miembros generados por el enlace de datos. Ambos constan de un elemento <xref:System.Windows.Controls.UIElementCollection> secundario hospedado en el elemento primario <xref:System.Windows.Controls.Panel> .  
  
 El panel también expone una <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> propiedad adjunta que se puede utilizar para lograr el orden en capas en un derivado <xref:System.Windows.Controls.Panel> . Los miembros de la colección de un panel <xref:System.Windows.Controls.Panel.Children%2A> con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valor superior aparecen delante de aquellos con un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valor inferior. Esto es especialmente útil para los paneles como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.Grid> que permiten a los elementos secundarios compartir el mismo espacio de coordenadas.  
  
 <xref:System.Windows.Controls.Panel>también define el <xref:System.Windows.Controls.Panel.OnRender%2A> método, que se puede utilizar para invalidar el comportamiento de presentación predeterminado de <xref:System.Windows.Controls.Panel> .  
  
#### <a name="attached-properties"></a>Propiedades asociadas  
 Los elementos de panel derivados usan mucho las propiedades adjuntas. Una propiedad adjunta es una forma especializada de propiedad de dependencia que no tiene el "contenedor" de la propiedad Common Language Runtime (CLR) convencional. Las propiedades adjuntas tienen una sintaxis especializada en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], que se puede ver en varios de los ejemplos a continuación.  
  
 Uno de los propósitos de una propiedad adjunta es permitir que los elementos secundarios almacenen valores únicos de una propiedad que en realidad está definida por un elemento principal. Una aplicación de esta funcionalidad consiste en tener elementos secundarios que informen al elemento principal cómo desean ser presentados en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], lo que resulta sumamente útil para el diseño de la aplicación. Para más información, consulte la [información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Elementos Panel derivados  
 Muchos objetos derivan de <xref:System.Windows.Controls.Panel> , pero no todos están diseñados para usarse como proveedores de diseño raíz. Hay seis clases de panel definidas ( <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.DockPanel> , <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.VirtualizingStackPanel> y <xref:System.Windows.Controls.WrapPanel> ) que están diseñadas específicamente para crear la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .  
  
 Cada elemento de panel encapsula su propia funcionalidad especial, como se muestra en la tabla siguiente.  
  
|Nombre del elemento|¿Es un panel de interfaz de usuario?|Descripción|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sí|Define un área en la que puede colocar explícitamente los elementos secundarios por coordenadas relativas al <xref:System.Windows.Controls.Canvas> área.|  
|<xref:System.Windows.Controls.DockPanel>|Sí|Define un área en la que se pueden organizar elementos secundarios de forma horizontal o vertical, relacionados entre sí.|  
|<xref:System.Windows.Controls.Grid>|Sí|Define un área de cuadrícula flexible que consta de columnas y filas. Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar con precisión mediante la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad.|  
|<xref:System.Windows.Controls.StackPanel>|Sí|Organiza elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Controla el diseño de los botones de ficha en un control <xref:System.Windows.Controls.TabControl> .|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Organiza el contenido dentro de un <xref:System.Windows.Controls.ToolBar> control.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid>se usa para organizar los elementos secundarios en una cuadrícula con todos los tamaños de celda iguales.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Proporciona una clase base para los paneles que pueden "virtualizar" su colección de elementos secundarios.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sí|Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sí|<xref:System.Windows.Controls.WrapPanel>coloca los elementos secundarios en una posición secuencial de izquierda a derecha, dividiendo el contenido en la línea siguiente en el borde del cuadro contenedor. La ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, en función del valor de la <xref:System.Windows.Controls.WrapPanel.Orientation%2A> propiedad.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Paneles de interfaz de usuario  
 Hay seis clases de panel disponibles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que están optimizadas para admitir [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] escenarios: <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.DockPanel> , <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.VirtualizingStackPanel> y <xref:System.Windows.Controls.WrapPanel> . Estos elementos de panel son fáciles de usar, versátiles y suficientemente extensibles para la mayoría de las aplicaciones.  
  
 Cada <xref:System.Windows.Controls.Panel> elemento derivado trata las restricciones de tamaño de manera diferente. Entender cómo <xref:System.Windows.Controls.Panel> controla las restricciones en la dirección horizontal o vertical puede hacer que el diseño sea más predecible.  
  
|**Nombre del panel**|**Dimensión x**|**Dimensión y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Restringida al contenido|Restringida al contenido|  
|<xref:System.Windows.Controls.DockPanel>|Restringida|Restringida|  
|<xref:System.Windows.Controls.StackPanel>(Orientación vertical)|Restringida|Restringida al contenido|  
|<xref:System.Windows.Controls.StackPanel>(Orientación horizontal)|Restringida al contenido|Restringida|  
|<xref:System.Windows.Controls.Grid>|Restringida|Restringido, excepto en los casos en los que <xref:System.Windows.GridUnitType.Auto> se aplica a filas y columnas|  
|<xref:System.Windows.Controls.WrapPanel>|Restringida al contenido|Restringida al contenido|  
  
 A continuación se ofrecen descripciones más detalladas y ejemplos del uso de cada uno de estos elementos.  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>Lienzo  
 El <xref:System.Windows.Controls.Canvas> elemento permite colocar el contenido de acuerdo con *x-* las coordenadas x *y-* e y absolutas. Los elementos se pueden dibujar en una ubicación única o bien, si ocupan las mismas coordenadas, el orden en que aparecen en el marcado determina el orden en que se dibujan.  
  
 <xref:System.Windows.Controls.Canvas>proporciona la compatibilidad de diseño más flexible de cualquier <xref:System.Windows.Controls.Panel> . Las propiedades Height y Width se usan para definir el área del lienzo, y los elementos dentro de se asignan a coordenadas absolutas relativas al área del elemento primario <xref:System.Windows.Controls.Canvas> . Cuatro propiedades adjuntas, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType> , permiten un control preciso de la ubicación de los objetos dentro de un <xref:System.Windows.Controls.Canvas> , lo que permite al desarrollador colocar y organizar los elementos de forma precisa en la pantalla.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds dentro de un lienzo  
 <xref:System.Windows.Controls.Canvas>puede colocar los elementos secundarios en cualquier posición de la pantalla, incluso en las coordenadas que están fuera de sus propias definidas <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> . Además, <xref:System.Windows.Controls.Canvas> no se ve afectado por el tamaño de sus elementos secundarios. Como resultado, es posible que un elemento secundario sobredibuje otros elementos fuera del rectángulo delimitador del elemento primario <xref:System.Windows.Controls.Canvas> . El comportamiento predeterminado de <xref:System.Windows.Controls.Canvas> es permitir que los elementos secundarios se dibujen fuera de los límites del elemento primario <xref:System.Windows.Controls.Canvas> . Si no desea este comportamiento, la <xref:System.Windows.UIElement.ClipToBounds%2A> propiedad se puede establecer en `true` . Esto hace que <xref:System.Windows.Controls.Canvas> se recorte a su propio tamaño. <xref:System.Windows.Controls.Canvas>es el único elemento de diseño que permite dibujar los elementos secundarios fuera de sus límites.  
  
 Este comportamiento se muestra gráficamente en el [ejemplo de comparación de las propiedades Width](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
#### <a name="defining-and-using-a-canvas"></a>Definición y uso de un lienzo  
 <xref:System.Windows.Controls.Canvas>Se puede crear una instancia de con solo usar el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código o. En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Controls.Canvas> para colocar el contenido de forma absoluta. Este código genera tres cuadrados de 100 píxeles. El primer cuadrado es rojo y su posición superior izquierda (*x, y*) se especifica como (0, 0). El segundo cuadrado es verde y su posición superior izquierda es (100, 100), justo debajo y a la derecha del primer cuadrado. El tercer cuadrado es azul y su posición superior izquierda es (50, 50), por lo que abarca el cuadrante inferior derecho del primer cuadrado y el cuadrante superior izquierdo del segundo. Como el tercer cuadrado se coloca en último lugar, pareciera que está encima de los otros dos cuadrados; es decir, las partes que se superponen toman el color del tercer cuadro.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento Canvas típico.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 El <xref:System.Windows.Controls.DockPanel> elemento usa la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta tal como se establece en los elementos de contenido secundario para colocar el contenido a lo largo de los bordes de un contenedor. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> se establece en <xref:System.Windows.Controls.Dock.Top> o <xref:System.Windows.Controls.Dock.Bottom> , coloca los elementos secundarios por encima o por debajo. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> se establece en <xref:System.Windows.Controls.Dock.Left> o <xref:System.Windows.Controls.Dock.Right> , coloca los elementos secundarios a la izquierda o a la derecha entre sí. La <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad determina la posición del elemento final agregado como un elemento secundario de <xref:System.Windows.Controls.DockPanel> .  
  
 Puede usar <xref:System.Windows.Controls.DockPanel> para colocar un grupo de controles relacionados, como un conjunto de botones. Como alternativa, puede utilizarlo para crear un "panel" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , similar al que se encuentra en Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Ajustar el tamaño al contenido  
 Si <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> no se especifican sus propiedades y, los <xref:System.Windows.Controls.DockPanel> tamaños se ajustan a su contenido. El tamaño puede aumentar o disminuir en función del tamaño de los elementos secundarios. Sin embargo, cuando se especifican estas propiedades y ya no hay espacio para el siguiente elemento secundario especificado, no se <xref:System.Windows.Controls.DockPanel> muestra ese elemento secundario ni los elementos secundarios subsiguientes, y no se miden los elementos secundarios subsiguientes.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 De forma predeterminada, el último elemento secundario de un <xref:System.Windows.Controls.DockPanel> elemento "rellenará" el espacio restante sin asignar. Si no desea este comportamiento, establezca la <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad en `false` .  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definición y uso de un elemento DockPanel  
 En el ejemplo siguiente se muestra cómo particionar el espacio mediante <xref:System.Windows.Controls.DockPanel> . <xref:System.Windows.Controls.Border>Se agregan cinco elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.DockPanel> . Cada usa una propiedad de posicionamiento diferente de un <xref:System.Windows.Controls.DockPanel> para particionar el espacio. El último elemento "rellena" el espacio que queda sin asignar.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Escenario DockPanel típico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Cuadrícula  
 El <xref:System.Windows.Controls.Grid> elemento combina la funcionalidad de una posición absoluta y un control de datos tabulares. <xref:System.Windows.Controls.Grid>Le permite colocar y aplicar estilo fácilmente a los elementos. <xref:System.Windows.Controls.Grid>permite definir agrupaciones de filas y de columnas flexibles e incluso proporciona un mecanismo para compartir información de tamaño entre varios <xref:System.Windows.Controls.Grid> elementos.  
  
#### <a name="how-is-grid-different-from-table"></a>¿En qué se diferencian Grid y Table?  
 <xref:System.Windows.Documents.Table>y <xref:System.Windows.Controls.Grid> comparten algunas funciones comunes, pero cada una de ellas es más adecuada para distintos escenarios. Un <xref:System.Windows.Documents.Table> está diseñado para su uso en el contenido dinámico (consulte [información general sobre documentos dinámicos](../advanced/flow-document-overview.md) para obtener más información sobre el contenido dinámico). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro de <xref:System.Windows.Documents.FlowDocument> , <xref:System.Windows.Documents.Table> admite los comportamientos del contenido dinámico, como la paginación, el reflujo de columnas y la selección de contenido, mientras que <xref:System.Windows.Controls.Grid> no. <xref:System.Windows.Controls.Grid>Por otra parte, se usa mejor fuera de un <xref:System.Windows.Documents.FlowDocument> por muchas razones, como <xref:System.Windows.Controls.Grid> Agregar elementos basados en un índice de fila y de columna, no <xref:System.Windows.Documents.Table> . El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table>no admite la disposición en capas. Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda". <xref:System.Windows.Documents.Table>no es compatible con esta característica. Por último, un <xref:System.Windows.Controls.Grid> es un peso más claro que un <xref:System.Windows.Documents.Table> .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamiento del ajuste de tamaño de las columnas y las filas  
 Las columnas y filas definidas dentro de <xref:System.Windows.Controls.Grid> pueden aprovechar <xref:System.Windows.GridUnitType.Star> el ajuste de tamaño para distribuir proporcionalmente el espacio restante. Cuando <xref:System.Windows.GridUnitType.Star> se selecciona como alto o ancho de una fila o columna, dicha columna o fila recibe una proporción ponderada del espacio disponible restante. Esto contrasta con <xref:System.Windows.GridUnitType.Auto> , que distribuirá el espacio uniformemente en función del tamaño del contenido de una columna o fila. Este valor se expresa como `*` o `2*` cuando se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. En el primer caso, la fila o la columna recibiría una vez el espacio disponible, en el segundo caso, dos veces, y así sucesivamente. Al combinar esta técnica para distribuir proporcionalmente el espacio con un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> valor de y `Stretch` , es posible particionar el espacio de diseño por porcentaje de espacio de la pantalla. <xref:System.Windows.Controls.Grid>es el único panel de diseño que puede distribuir el espacio de esta manera.  
  
#### <a name="defining-and-using-a-grid"></a>Definición y uso de una cuadrícula  
 En el ejemplo siguiente se muestra cómo compilar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] similar al que se encuentra en el cuadro de diálogo Ejecutar disponible en el menú Inicio de Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento de cuadrícula típico.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 <xref:System.Windows.Controls.StackPanel>Permite "apilar" elementos en una dirección asignada. De forma predeterminada, los elementos se apilan en dirección vertical. La <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad se puede utilizar para controlar el flujo de contenido.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel frente a DockPanel  
 Aunque <xref:System.Windows.Controls.DockPanel> también puede "apilar" elementos secundarios <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel> no produce resultados análogos en algunos escenarios de uso. Por ejemplo, el orden de los elementos secundarios puede afectar a su tamaño en <xref:System.Windows.Controls.DockPanel> pero no en <xref:System.Windows.Controls.StackPanel> . Esto se debe <xref:System.Windows.Controls.StackPanel> a que las medidas en la dirección de la pila en <xref:System.Double.PositiveInfinity> , mientras que <xref:System.Windows.Controls.DockPanel> mide solo el tamaño disponible.  
  
 En el ejemplo siguiente se muestra esta diferencia clave.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La diferencia en cuanto al comportamiento de representación se puede ver en esta imagen.  
  
 ![Captura de pantalla: Captura de pantalla de StackPanel frente a DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definición y uso de un elemento StackPanel  
 En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Windows.Controls.StackPanel> para crear un conjunto de botones ubicados verticalmente. Para el posicionamiento horizontal, establezca la <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad en <xref:System.Windows.Controls.Orientation.Horizontal> .  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento StackPanel típico.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también proporciona una variación del <xref:System.Windows.Controls.StackPanel> elemento que "virtualiza" automáticamente el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica por la que se genera un subconjunto de elementos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel>(a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel> ) calcula los elementos visibles y funciona con <xref:System.Windows.Controls.ItemContainerGenerator> desde un <xref:System.Windows.Controls.ItemsControl> (como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView> ) para crear solo elementos para elementos visibles.  
  
 El <xref:System.Windows.Controls.VirtualizingStackPanel> elemento se establece automáticamente como el host de elementos para los controles como <xref:System.Windows.Controls.ListBox> . Al hospedar una colección enlazada a datos, el contenido se virtualiza automáticamente, siempre y cuando el contenido se encuentre dentro de los límites de <xref:System.Windows.Controls.ScrollViewer> . Esto mejora notablemente el rendimiento cuando se hospedan muchos elementos secundarios.  
  
 En el marcado siguiente se muestra cómo usar <xref:System.Windows.Controls.VirtualizingStackPanel> como host de elementos. La <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> propiedad adjunta debe establecerse en `true` (valor predeterminado) para que se produzca la virtualización.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>se usa para colocar los elementos secundarios en una posición secuencial de izquierda a derecha, lo que divide el contenido en la línea siguiente cuando alcanza el borde de su contenedor primario. El contenido se puede orientar horizontal o verticalmente. <xref:System.Windows.Controls.WrapPanel>resulta útil para escenarios de flujo sencillos [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . También se puede usar para aplicar un tamaño uniforme a todos sus elementos secundarios.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.WrapPanel> para mostrar <xref:System.Windows.Controls.Button> los controles que se ajustan cuando llegan al borde de su contenedor.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento WrapPanel típico.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Elementos Panel anidados  
 <xref:System.Windows.Controls.Panel>los elementos se pueden anidar entre sí con el fin de generar diseños complejos. Esto puede resultar muy útil en situaciones en las que una <xref:System.Windows.Controls.Panel> es ideal para una parte de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , pero puede no satisfacer las necesidades de una parte diferente de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .  
  
 No existe ningún límite práctico para la cantidad de anidamiento que puede admitir la aplicación; sin embargo, en general se recomienda limitar la aplicación para que use solo los paneles que son realmente necesarios para el diseño que se desea. En muchos casos, <xref:System.Windows.Controls.Grid> se puede usar un elemento en lugar de paneles anidados debido a su flexibilidad como contenedor de diseño. Esto puede aumentar el rendimiento de una aplicación al dejar fuera del árbol los elementos innecesarios.  
  
 En el ejemplo siguiente se muestra cómo crear un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que aprovecha <xref:System.Windows.Controls.Panel> los elementos anidados para lograr un diseño específico. En este caso concreto, <xref:System.Windows.Controls.DockPanel> se utiliza un elemento para proporcionar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] estructura, y <xref:System.Windows.Controls.StackPanel> los elementos anidados, <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Canvas> se usan para colocar los elementos secundarios de forma precisa en el elemento primario <xref:System.Windows.Controls.DockPanel> .  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![IU que aprovecha los paneles anidados.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Elementos Panel personalizados  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una matriz de controles de diseño flexibles, los comportamientos de diseño personalizados también se pueden lograr invalidando los <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos y. Es posible ajustar de forma personalizada el tamaño y la posición si se definen nuevos comportamientos de posicionamiento mediante estos métodos de invalidación.  
  
 Del mismo modo, los comportamientos de diseño personalizados basados en clases derivadas (como <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.Grid> ) se pueden definir invalidando sus <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos y.  
  
 En el marcado siguiente se muestra cómo crear un <xref:System.Windows.Controls.Panel> elemento personalizado. Este nuevo <xref:System.Windows.Controls.Panel> , definido como `PlotPanel` , admite la posición de los elementos secundarios mediante el uso de las coordenadas *x* e *y* codificadas de forma rígida. En este ejemplo, un <xref:System.Windows.Shapes.Rectangle> elemento (no se muestra) se coloca en el punto de trazado 50 (*x*) y 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Para ver una implementación de un panel personalizado más complejo, consulte el [ejemplo de creación de un panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Compatibilidad para la localización y globalización  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite diversas características que facilitan la creación de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizable.  
  
 Todos los elementos del panel admiten de forma nativa la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad, que se puede usar para cambiar dinámicamente el flujo del contenido en función de la configuración regional o de idioma de un usuario. Para más información, consulte <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La <xref:System.Windows.Window.SizeToContent%2A> propiedad proporciona un mecanismo que permite a los desarrolladores de aplicaciones anticiparse a las necesidades de localizadas [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Mediante el <xref:System.Windows.SizeToContent.WidthAndHeight> valor de esta propiedad, un elemento primario <xref:System.Windows.Window> siempre dimensiona dinámicamente para ajustarse al contenido y no está restringido por las restricciones de alto o ancho artificial.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.StackPanel> son buenas opciones para localizable [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . <xref:System.Windows.Controls.Canvas>No obstante, no es una buena opción, ya que coloca el contenido de forma absoluta, lo que dificulta la localización.  
  
 Para obtener información adicional sobre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la creación de aplicaciones con interfaces de usuario localizables (IUS), consulte la [información general sobre el uso del diseño automático](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Ejemplo WPF Layout Gallery](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Diseño](../advanced/layout.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
- [Información general sobre alineación, márgenes y relleno](../advanced/alignment-margins-and-padding-overview.md)
- [Ejemplo de creación de un panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md)
- [Información general sobre el uso del diseño automático](../advanced/use-automatic-layout-overview.md)
- [Presentación y diseño](../advanced/optimizing-performance-layout-and-design.md)
