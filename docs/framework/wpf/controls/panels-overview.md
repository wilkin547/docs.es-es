---
title: Información general sobre elementos Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 9bd2af8cd74c32bcda3a6105f39af470f961289d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625726"
---
# <a name="panels-overview"></a>Información general sobre elementos Panel
<xref:System.Windows.Controls.Panel> los elementos son componentes que controlan la representación de elementos, su tamaño y dimensiones, su posición y la disposición de su contenido secundario. El [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una serie de predefinidos <xref:System.Windows.Controls.Panel> elementos, así como la capacidad de construir personalizado <xref:System.Windows.Controls.Panel> elementos.  
  
 Este tema contiene las siguientes secciones:  
  
- [La clase Panel](#Panels_view_from_10000_feet)  
  
- [Miembros comunes del elemento Panel](#Panels_declared_members)  
  
- [Elementos Panel derivados](#Panels_derived_elements)  
  
- [Paneles de interfaz de usuario](#Panels_main_UI_elements)  
  
- [Elementos Panel anidados](#Panels_nested_panel_elements)  
  
- [Elementos Panel personalizados](#Panels_custom_panel_elements)  
  
- [Compatibilidad para la localización y globalización](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>La clase Panel  
 <xref:System.Windows.Controls.Panel> es la clase base para todos los elementos que proporcionan diseño admiten en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Derivados <xref:System.Windows.Controls.Panel> elementos se utilizan para colocar y organizar elementos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y el código.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un conjunto completo de implementaciones de panel derivadas que permiten numerosos diseños complejos. Estas clases derivadas exponen propiedades y métodos que habilitan la mayoría de los escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] estándar. Los desarrolladores que no puede encontrar un comportamiento de disposición secundario que satisfaga sus necesidades puede crear diseños nuevos invalidando el <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos. Para más información sobre los comportamientos de diseño personalizados, consulte [Elementos Panel personalizados](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Miembros comunes del elemento Panel  
 Todos los <xref:System.Windows.Controls.Panel> elementos admiten la base de tamaño y la posición de las propiedades definidas por <xref:System.Windows.FrameworkElement>, incluidos <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, y <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Para obtener más información sobre el posicionamiento de las propiedades definidas por <xref:System.Windows.FrameworkElement>, consulte [alineación, márgenes y relleno de información general sobre](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> expone propiedades adicionales que son de importancia crítica para entender y usar el diseño. El <xref:System.Windows.Controls.Panel.Background%2A> propiedad se utiliza para rellenar el área entre los límites de un elemento panel derivado con un <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A> representa la colección de elementos secundarios que el <xref:System.Windows.Controls.Panel> está formado por. <xref:System.Windows.Controls.Panel.InternalChildren%2A> representa el contenido de la <xref:System.Windows.Controls.Panel.Children%2A> colección junto con los miembros generados por el enlace de datos. Ambos se componen de un <xref:System.Windows.Controls.UIElementCollection> de elementos secundarios hospedados dentro del elemento primario <xref:System.Windows.Controls.Panel>.  
  
 Panel también expone un <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> adjunta la propiedad que se puede usar para lograr un orden dispuesto en capas en un derivado <xref:System.Windows.Controls.Panel>. Los miembros de un panel <xref:System.Windows.Controls.Panel.Children%2A> colección con una mayor <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valor aparecen delante de aquellos con un menor <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> valor. Esto es especialmente útil para los paneles como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.Grid> que permiten a los elementos secundarios compartir el mismo espacio de coordenadas.  
  
 <xref:System.Windows.Controls.Panel> También define la <xref:System.Windows.Controls.Panel.OnRender%2A> método, que se puede usar para invalidar el comportamiento de presentación predeterminado de un <xref:System.Windows.Controls.Panel>.  
  
#### <a name="attached-properties"></a>Propiedades asociadas  
 Los elementos de panel derivados usan mucho las propiedades adjuntas. Una propiedad adjunta es una forma especializada de propiedad de dependencia que no tiene el "contenedor" de propiedades de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] convencional. Las propiedades adjuntas tienen una sintaxis especializada en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], que se puede ver en varios de los ejemplos a continuación.  
  
 Uno de los propósitos de una propiedad adjunta es permitir que los elementos secundarios almacenen valores únicos de una propiedad que en realidad está definida por un elemento principal. Una aplicación de esta funcionalidad consiste en tener elementos secundarios que informen al elemento principal cómo desean ser presentados en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], lo que resulta sumamente útil para el diseño de la aplicación. Para más información, consulte la [información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Elementos Panel derivados  
 Muchos objetos se derivan de <xref:System.Windows.Controls.Panel>, pero no todos ellos están pensados para usarlos como proveedores de diseño raíz. Existen seis clases de panel definidas (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, y <xref:System.Windows.Controls.WrapPanel>) que están diseñadas específicamente para crear la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Cada elemento de panel encapsula su propia funcionalidad especial, como se muestra en la tabla siguiente.  
  
|Nombre del elemento|¿Es un panel de interfaz de usuario?|Descripción|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sí|Define un área en la cual puede colocar explícitamente los elementos secundarios utilizando las coordenadas relativas a la <xref:System.Windows.Controls.Canvas> área.|  
|<xref:System.Windows.Controls.DockPanel>|Sí|Define un área en la que se pueden organizar elementos secundarios de forma horizontal o vertical, relacionados entre sí.|  
|<xref:System.Windows.Controls.Grid>|Sí|Define un área de cuadrícula flexible que consta de columnas y filas. Los elementos secundarios de un <xref:System.Windows.Controls.Grid> puede colocar con precisión usando la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad.|  
|<xref:System.Windows.Controls.StackPanel>|Sí|Organiza elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Controla el diseño de botones de ficha en un <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Organiza el contenido dentro de un <xref:System.Windows.Controls.ToolBar> control.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid> se utiliza para organizar a los elementos secundarios en una cuadrícula con todos los tamaños de celda igual.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Proporciona una clase base para los paneles que pueden "virtualizar" su colección de elementos secundarios.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sí|Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sí|<xref:System.Windows.Controls.WrapPanel> Organiza los elementos secundarios en posición secuencial de izquierda a derecha y traslada el contenido a la línea siguiente en el borde del cuadro contenedor. Ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, dependiendo del valor de la <xref:System.Windows.Controls.WrapPanel.Orientation%2A> propiedad.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Paneles de interfaz de usuario  
 Existen seis clases de panel disponibles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que están optimizados para admitir [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] escenarios: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, y <xref:System.Windows.Controls.WrapPanel>. Estos elementos de panel son fáciles de usar, versátiles y suficientemente extensibles para la mayoría de las aplicaciones.  
  
 Cada uno derivado <xref:System.Windows.Controls.Panel> elemento trata las restricciones de tamaño de manera diferente. Descripción de cómo un <xref:System.Windows.Controls.Panel> identificadores restricciones en la dirección horizontal o vertical pueden hacer diseño más predecible.  
  
|**Nombre del panel**|**Dimensión x**|**Dimensión y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Restringida al contenido|Restringida al contenido|  
|<xref:System.Windows.Controls.DockPanel>|Restringida|Restringida|  
|<xref:System.Windows.Controls.StackPanel> (Orientación vertical)|Restringida|Restringida al contenido|  
|<xref:System.Windows.Controls.StackPanel> (Orientación horizontal)|Restringida al contenido|Restringida|  
|<xref:System.Windows.Controls.Grid>|Restringida|Restringida, excepto en casos donde <xref:System.Windows.GridUnitType.Auto> se aplican a las filas y columnas|  
|<xref:System.Windows.Controls.WrapPanel>|Restringida al contenido|Restringida al contenido|  
  
 A continuación se ofrecen descripciones más detalladas y ejemplos del uso de cada uno de estos elementos.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 El <xref:System.Windows.Controls.Canvas> elemento permite la colocación del contenido de acuerdo con *x -* y *y -* coordenadas. Los elementos se pueden dibujar en una ubicación única o bien, si ocupan las mismas coordenadas, el orden en que aparecen en el marcado determina el orden en que se dibujan.  
  
 <xref:System.Windows.Controls.Canvas> proporciona la compatibilidad de diseño más flexible de cualquier <xref:System.Windows.Controls.Panel>. Propiedades Height y Width se usan para definir el área del lienzo, y se asignan a los elementos dentro de las coordenadas absolutas en relación con el área del elemento primario <xref:System.Windows.Controls.Canvas>. Cuatro propiedades adjuntas <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, permitir que un control exhaustivo de la posición de los objetos dentro de un <xref:System.Windows.Controls.Canvas>, lo que permite al programador colocar y organizar elementos en la pantalla con precisión.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds dentro de un lienzo  
 <xref:System.Windows.Controls.Canvas> puede colocar elementos secundarios en cualquier posición de la pantalla, incluso en coordenadas ubicadas fuera de su propio definido <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A>. Además, <xref:System.Windows.Controls.Canvas> no se ve afectado por el tamaño de sus elementos secundarios. Como resultado, es posible que un elemento secundario a otros elementos fuera del rectángulo delimitador del elemento primario el sobredibujo <xref:System.Windows.Controls.Canvas>. El comportamiento predeterminado de un <xref:System.Windows.Controls.Canvas> es permitir que los elementos secundarios se dibuje fuera de los límites del elemento primario <xref:System.Windows.Controls.Canvas>. Si este comportamiento no deseado, la <xref:System.Windows.UIElement.ClipToBounds%2A> propiedad puede establecerse en `true`. Esto hace que <xref:System.Windows.Controls.Canvas> se recorte a su propio tamaño. <xref:System.Windows.Controls.Canvas> es el único elemento de diseño que permite que los niños se dibuje fuera de sus límites.  
  
 Este comportamiento se muestra gráficamente en el [ejemplo de comparación de las propiedades Width](https://go.microsoft.com/fwlink/?LinkID=160050).  
  
#### <a name="defining-and-using-a-canvas"></a>Definición y uso de un lienzo  
 Un <xref:System.Windows.Controls.Canvas> se pueden crear instancias utilizando simplemente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código. En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Controls.Canvas> a la posición absoluta de contenido. Este código genera tres cuadrados de 100 píxeles. El primer cuadrado es rojo y su posición superior izquierda (*x, y*) se especifica como (0, 0). El segundo cuadrado es verde y su posición superior izquierda es (100, 100), justo debajo y a la derecha del primer cuadrado. El tercer cuadrado es azul y su posición superior izquierda es (50, 50), por lo que abarca el cuadrante inferior derecho del primer cuadrado y el cuadrante superior izquierdo del segundo. Como el tercer cuadrado se coloca en último lugar, pareciera que está encima de los otros dos cuadrados; es decir, las partes que se superponen toman el color del tercer cuadro.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Un elemento Canvas típico.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 El <xref:System.Windows.Controls.DockPanel> elemento utiliza la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> propiedad adjunta como conjunto de elementos de contenido secundarios para colocar el contenido a lo largo de los bordes de un contenedor. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> está establecido en <xref:System.Windows.Controls.Dock.Top> o <xref:System.Windows.Controls.Dock.Bottom>, coloca los elementos secundarios por encima o debajo de la otra. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> está establecido en <xref:System.Windows.Controls.Dock.Left> o <xref:System.Windows.Controls.Dock.Right>, coloca los elementos secundarios a la izquierda o derecha de los demás. El <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad determina la posición del elemento final agregado como un elemento secundario de un <xref:System.Windows.Controls.DockPanel>.  
  
 Puede usar <xref:System.Windows.Controls.DockPanel> para colocar un grupo de controles relacionados, como un conjunto de botones. También puede usarlo para crear una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] "con paneles", similar a la de [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### <a name="sizing-to-content"></a>Ajuste del tamaño al contenido  
 Si su <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> no se especifican las propiedades, <xref:System.Windows.Controls.DockPanel> tamaños a su contenido. El tamaño puede aumentar o disminuir en función del tamaño de los elementos secundarios. Sin embargo, cuando estas propiedades se especifican y ya no hay espacio para el siguiente elemento secundario especificado, <xref:System.Windows.Controls.DockPanel> no muestra ese elemento secundario ni los elementos secundarios subsiguientes y no se mide los elementos secundarios subsiguientes.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 De forma predeterminada, el último elemento secundario de un <xref:System.Windows.Controls.DockPanel> elemento "rellenará" el resto de espacio sin asignar. Si no se desea este comportamiento, establezca el <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definición y uso de un elemento DockPanel  
 En el ejemplo siguiente se muestra cómo particionar el espacio mediante un <xref:System.Windows.Controls.DockPanel>. Cinco <xref:System.Windows.Controls.Border> elementos se agregan como elementos secundarios de un elemento primario <xref:System.Windows.Controls.DockPanel>. Cada uno de ellos usa una propiedad de posicionamiento distinta de una <xref:System.Windows.Controls.DockPanel> al espacio de partición. El último elemento "rellena" el espacio que queda sin asignar.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Escenario DockPanel típico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Cuadrícula  
 El <xref:System.Windows.Controls.Grid> elemento combina la funcionalidad de un control de datos tabulares y posicionamiento absoluto. Un <xref:System.Windows.Controls.Grid> le permite fácilmente los elementos de estilo y posición. <xref:System.Windows.Controls.Grid> le permite definir flexibles de filas y las agrupaciones de columnas e incluso proporciona un mecanismo para compartir información de tamaño entre varios <xref:System.Windows.Controls.Grid> elementos.  
  
#### <a name="how-is-grid-different-from-table"></a>¿En qué se diferencian Grid y Table?  
 <xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten funcionalidades comunes, pero cada una es adecuada para escenarios diferentes. Un <xref:System.Windows.Documents.Table> está diseñado para su uso en contenido dinámico (consulte [Flow Document Overview](../advanced/flow-document-overview.md) para obtener más información sobre el contenido dinámico). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro de un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> admite el flujo de los comportamientos del contenido, como paginación, ajuste dinámico de columnas y selección de contenido mientras una <xref:System.Windows.Controls.Grid> no lo hace. Un <xref:System.Windows.Controls.Grid> por otro lado se utiliza fuera de un <xref:System.Windows.Documents.FlowDocument> por diversos motivos incluidos <xref:System.Windows.Controls.Grid> agrega elementos basándose en un índice de fila y columna, <xref:System.Windows.Documents.Table> no lo hace. El <xref:System.Windows.Controls.Grid> elemento permite la disposición en capas del contenido secundario, lo que permite más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table> no admite la disposición en capas. Los elementos secundarios de un <xref:System.Windows.Controls.Grid> puede colocar de manera absoluta en relación con el área de los límites "celda". <xref:System.Windows.Documents.Table> no se admite esta característica. Por último, un <xref:System.Windows.Controls.Grid> es más ligero que un <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamiento del ajuste de tamaño de las columnas y las filas  
 Las columnas y las filas definidas dentro de un <xref:System.Windows.Controls.Grid> puede sacar partido de <xref:System.Windows.GridUnitType.Star> ajuste de tamaño con el fin de distribuir proporcionalmente el espacio restante. Cuando <xref:System.Windows.GridUnitType.Star> está seleccionado como el alto o ancho de una fila o columna, que la columna o fila recibe una proporción ponderada del espacio disponible restante. Se trata en contraposición al <xref:System.Windows.GridUnitType.Auto>, distribuirá el espacio de manera uniforme en función del tamaño del contenido dentro de una columna o fila. Este valor se expresa como `*` o `2*` cuando se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. En el primer caso, la fila o la columna recibiría una vez el espacio disponible, en el segundo caso, dos veces, y así sucesivamente. Mediante la combinación de esta técnica para distribuir proporcionalmente el espacio con un <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> valor `Stretch` es posible dividir el espacio de diseño por el porcentaje de espacio en la pantalla. <xref:System.Windows.Controls.Grid> es el único panel de diseño que puede distribuir el espacio de esta manera.  
  
#### <a name="defining-and-using-a-grid"></a>Definición y uso de una cuadrícula  
 En el ejemplo siguiente se muestra cómo compilar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] similar a la del cuadro de diálogo Ejecutar del menú Inicio de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento Grid típico.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Un <xref:System.Windows.Controls.StackPanel> le permite "apilar" los elementos en una dirección asignada. De forma predeterminada, los elementos se apilan en dirección vertical. El <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad puede utilizarse para controlar el flujo del contenido.  
  
#### <a name="stackpanel-vs-dockpanel"></a>Comparación entre StackPanel y DockPanel  
 Aunque <xref:System.Windows.Controls.DockPanel> también puede "apilar" elementos secundarios, <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel> no generan resultados análogos en algunos escenarios de uso. Por ejemplo, el orden de los elementos secundarios puede afectar a su tamaño en un <xref:System.Windows.Controls.DockPanel> , pero no en un <xref:System.Windows.Controls.StackPanel>. Esto es porque <xref:System.Windows.Controls.StackPanel> medidas en la dirección del apilado en <xref:System.Double.PositiveInfinity>, mientras que <xref:System.Windows.Controls.DockPanel> mide solo el tamaño disponible.  
  
 En el ejemplo siguiente se muestra esta diferencia clave.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La diferencia en cuanto al comportamiento de representación se puede ver en esta imagen.  
  
 ![Captura de pantalla: Comparación entre StackPanel y DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definición y uso de un elemento StackPanel  
 En el ejemplo siguiente se muestra cómo usar un <xref:System.Windows.Controls.StackPanel> para crear un conjunto de botones colocados verticalmente. Para colocarlos horizontalmente, establezca el <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento StackPanel típico.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También proporciona una variación de la <xref:System.Windows.Controls.StackPanel> elemento que "virtualiza" automáticamente el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica por la que se genera un subconjunto de elementos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel> (a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel>) calcula los elementos visibles y funciona con la <xref:System.Windows.Controls.ItemContainerGenerator> desde un <xref:System.Windows.Controls.ItemsControl> (como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) sólo crear elementos para los elementos visibles.  
  
 El <xref:System.Windows.Controls.VirtualizingStackPanel> elemento se establece automáticamente como el host de elementos para los controles, como el <xref:System.Windows.Controls.ListBox>. Cuando hospeda los datos de una colección enlazada, contenido se virtualiza automáticamente, siempre y cuando el contenido está dentro de los límites de un <xref:System.Windows.Controls.ScrollViewer>. Esto mejora notablemente el rendimiento cuando se hospedan muchos elementos secundarios.  
  
 El marcado siguiente muestra cómo utilizar un <xref:System.Windows.Controls.VirtualizingStackPanel> como un host de elementos. El <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> debe establecerse la propiedad adjunta en `true` (predeterminado) para que se produzca la virtualización.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> se utiliza para situar elementos secundarios en posición secuencial de izquierda a derecha y traslada el contenido a la línea siguiente cuando alcanza el borde de su contenedor primario. El contenido se puede orientar horizontal o verticalmente. <xref:System.Windows.Controls.WrapPanel> es útil para el flujo simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios. También se puede usar para aplicar un tamaño uniforme a todos sus elementos secundarios.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.WrapPanel> para mostrar <xref:System.Windows.Controls.Button> los controles que se ajustan cuando llegan al borde de su contenedor.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento WrapPanel típico.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Elementos Panel anidados  
 <xref:System.Windows.Controls.Panel> los elementos se pueden anidar dentro de otros para generar diseños complejos. Esto puede resultar muy útil en situaciones donde un <xref:System.Windows.Controls.Panel> es ideal para una parte de un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], pero no se puede satisfacer las necesidades de una parte distinta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 No existe ningún límite práctico para la cantidad de anidamiento que puede admitir la aplicación; sin embargo, en general se recomienda limitar la aplicación para que use solo los paneles que son realmente necesarios para el diseño que se desea. En muchos casos, un <xref:System.Windows.Controls.Grid> elemento se puede usar en lugar de paneles anidados debido a su flexibilidad como contenedor de diseño. Esto puede aumentar el rendimiento de una aplicación al dejar fuera del árbol los elementos innecesarios.  
  
 En el ejemplo siguiente se muestra cómo crear un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que lo aprovecha anidado <xref:System.Windows.Controls.Panel> elementos con el fin de lograr un diseño específico. En este caso concreto, un <xref:System.Windows.Controls.DockPanel> elemento se usa para proporcionar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] estructurar y anidar <xref:System.Windows.Controls.StackPanel> elementos, un <xref:System.Windows.Controls.Grid>y un <xref:System.Windows.Controls.Canvas> sirven para colocar los elementos secundarios con precisión dentro del elemento primario <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![UI que aprovecha los paneles anidados.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Elementos Panel personalizados  
 Mientras [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una matriz de controles de diseño flexibles, diseño personalizado también se pueden conseguir comportamientos invalidando el <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos. Es posible ajustar de forma personalizada el tamaño y la posición si se definen nuevos comportamientos de posicionamiento mediante estos métodos de invalidación.  
  
 De forma similar, los comportamientos de diseño personalizados en función de sus clases derivadas (como <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.Grid>) se pueden definir invalidando sus <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos.  
  
 El marcado siguiente muestra cómo crear una personalizada <xref:System.Windows.Controls.Panel> elemento. Esta nueva <xref:System.Windows.Controls.Panel>, definida como `PlotPanel`, admite el posicionamiento de elementos secundarios mediante el uso de disco duro de forma rígida *x -* y *y -* coordenadas. En este ejemplo, un <xref:System.Windows.Shapes.Rectangle> (no mostrado) del elemento se coloca en las coordenadas 50 (*x*) y 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Para ver una implementación de un panel personalizado más complejo, consulte el [ejemplo de creación de un panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Compatibilidad para la localización y globalización  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite diversas características que facilitan la creación de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizable.  
  
 Todos los elementos panel admiten de forma nativa la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad, que se puede usar para alterar dinámicamente el flujo contenido basándose en la configuración de idioma o configuración regional del usuario. Para obtener más información, consulta <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 El <xref:System.Windows.Window.SizeToContent%2A> propiedad proporciona un mecanismo que permite a los desarrolladores de aplicaciones para prever las necesidades de localizadas [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Mediante el <xref:System.Windows.SizeToContent.WidthAndHeight> valor de esta propiedad, un elemento primario <xref:System.Windows.Window> siempre ajusta su tamaño dinámicamente para ajustarse al contenido y no está limitado por las restricciones artificiales de alto o ancho.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, y <xref:System.Windows.Controls.StackPanel> son buenas opciones para localizable [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas> es no es una buena elección, sin embargo, dado que coloca el contenido de forma absoluta, lo que sea difícil su localización.  
  
 Para información adicional sobre cómo crear aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] localizables, consulte [Información general sobre el uso del diseño automático](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Ejemplo WPF Layout Gallery](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Diseño](../advanced/layout.md)
- [WPF Controls Gallery Sample](https://go.microsoft.com/fwlink/?LinkID=160053) (Ejemplo de galería de controles de WPF)
- [Información general sobre alineación, márgenes y relleno](../advanced/alignment-margins-and-padding-overview.md)
- [Crear un ejemplo de Panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Información general sobre propiedades asociadas](../advanced/attached-properties-overview.md)
- [Información general sobre el uso del diseño automático](../advanced/use-automatic-layout-overview.md)
- [Presentación y diseño](../advanced/optimizing-performance-layout-and-design.md)
