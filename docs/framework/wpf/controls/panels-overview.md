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
ms.openlocfilehash: 7810bfbf4f5bedf51e0797a4b9017f589e0b0a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187581"
---
# <a name="panels-overview"></a>Información general sobre elementos Panel
<xref:System.Windows.Controls.Panel>los elementos son componentes que controlan la representación de los elementos: su tamaño y dimensiones, su posición y la disposición de su contenido secundario. Proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] una serie de <xref:System.Windows.Controls.Panel> elementos predefinidos, así <xref:System.Windows.Controls.Panel> como la capacidad de construir elementos personalizados.  
  
 Este tema contiene las siguientes secciones.  
  
- [La clase Panel](#Panels_view_from_10000_feet)  
  
- [Miembros comunes del elemento Panel](#Panels_declared_members)  
  
- [Elementos Panel derivados](#Panels_derived_elements)  
  
- [Paneles de interfaz de usuario](#Panels_main_UI_elements)  
  
- [Elementos Panel anidados](#Panels_nested_panel_elements)  
  
- [Elementos Panel personalizados](#Panels_custom_panel_elements)  
  
- [Compatibilidad para la localización y globalización](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>
## <a name="the-panel-class"></a>La clase Panel  
 <xref:System.Windows.Controls.Panel>es la clase base para todos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]los elementos que proporcionan compatibilidad con el diseño en . Los <xref:System.Windows.Controls.Panel> elementos derivados se utilizan [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para colocar y organizar los elementos en y el código.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un conjunto completo de implementaciones de panel derivadas que permiten numerosos diseños complejos. Estas clases derivadas exponen propiedades y métodos que habilitan la mayoría de los escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] estándar. Los desarrolladores que no pueden encontrar un comportamiento de arreglo secundario <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> que <xref:System.Windows.FrameworkElement.MeasureOverride%2A> satisfaga sus necesidades pueden crear nuevos diseños reemplazando los métodos y. Para más información sobre los comportamientos de diseño personalizados, consulte [Elementos Panel personalizados](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Miembros comunes del elemento Panel  
 Todos <xref:System.Windows.Controls.Panel> los elementos admiten las propiedades <xref:System.Windows.FrameworkElement>de <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A>tamaño <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>y <xref:System.Windows.FrameworkElement.Margin%2A>posicionamiento base definidas por , , , , , y <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Para obtener información adicional sobre <xref:System.Windows.FrameworkElement>las propiedades de posicionamiento definidas por , vea [Alineación, Márgenes y Descripción general](../advanced/alignment-margins-and-padding-overview.md)del relleno .  
  
 <xref:System.Windows.Controls.Panel>expone propiedades adicionales que son de importancia crítica para comprender y usar el diseño. La <xref:System.Windows.Controls.Panel.Background%2A> propiedad se utiliza para rellenar el área entre los <xref:System.Windows.Media.Brush>límites de un elemento de panel derivado con un . <xref:System.Windows.Controls.Panel.Children%2A>representa la colección secundaria <xref:System.Windows.Controls.Panel> de elementos de los que se compone. <xref:System.Windows.Controls.Panel.InternalChildren%2A>representa el contenido <xref:System.Windows.Controls.Panel.Children%2A> de la colección más los miembros generados por el enlace de datos. Ambos constan <xref:System.Windows.Controls.UIElementCollection> de un de <xref:System.Windows.Controls.Panel>elementos secundarios hospedados dentro del elemento primario .  
  
 Panel también expone <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> una propiedad adjunta que se puede utilizar <xref:System.Windows.Controls.Panel>para lograr el orden en capas en un derivado . Los miembros de <xref:System.Windows.Controls.Panel.Children%2A> la colección de un panel con un valor más alto <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> aparecen delante de aquellos con un valor más bajo. <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Esto es particularmente útil <xref:System.Windows.Controls.Canvas> para <xref:System.Windows.Controls.Grid> paneles como y que permiten a los niños compartir el mismo espacio de coordenadas.  
  
 <xref:System.Windows.Controls.Panel>también define <xref:System.Windows.Controls.Panel.OnRender%2A> el método, que se puede utilizar <xref:System.Windows.Controls.Panel>para invalidar el comportamiento de presentación predeterminado de un archivo .  
  
#### <a name="attached-properties"></a>Propiedades asociadas  
 Los elementos de panel derivados usan mucho las propiedades adjuntas. Una propiedad adjunta es una forma especializada de propiedad de dependencia que no tiene la propiedad de Common Language Runtime (CLR) convencional "wrapper". Las propiedades adjuntas tienen una sintaxis especializada en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], que se puede ver en varios de los ejemplos a continuación.  
  
 Uno de los propósitos de una propiedad adjunta es permitir que los elementos secundarios almacenen valores únicos de una propiedad que en realidad está definida por un elemento principal. Una aplicación de esta funcionalidad consiste en tener elementos secundarios que informen al elemento principal cómo desean ser presentados en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], lo que resulta sumamente útil para el diseño de la aplicación. Para más información, consulte la [información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Elementos Panel derivados  
 Muchos objetos <xref:System.Windows.Controls.Panel>derivan de , pero no todos ellos están diseñados para su uso como proveedores de diseño raíz. Hay seis clases<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.DockPanel>de <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.StackPanel>panel <xref:System.Windows.Controls.VirtualizingStackPanel>definidas <xref:System.Windows.Controls.WrapPanel>( , , , [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], , , y ) que están diseñadas específicamente para crear la aplicación.  
  
 Cada elemento de panel encapsula su propia funcionalidad especial, como se muestra en la tabla siguiente.  
  
|Nombre del elemento|¿Es un panel de interfaz de usuario?|Descripción|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sí|Define un área dentro de la <xref:System.Windows.Controls.Canvas> cual puede colocar explícitamente los elementos secundarios mediante coordenadas relativas al área.|  
|<xref:System.Windows.Controls.DockPanel>|Sí|Define un área en la que se pueden organizar elementos secundarios de forma horizontal o vertical, relacionados entre sí.|  
|<xref:System.Windows.Controls.Grid>|Sí|Define un área de cuadrícula flexible que consta de columnas y filas. Los elementos <xref:System.Windows.Controls.Grid> secundarios de a <xref:System.Windows.FrameworkElement.Margin%2A> se pueden colocar con precisión mediante la propiedad.|  
|<xref:System.Windows.Controls.StackPanel>|Sí|Organiza elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Sin |Controla el diseño de <xref:System.Windows.Controls.TabControl>los botones de tabulación en un archivo .|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Sin |Organiza el contenido <xref:System.Windows.Controls.ToolBar> dentro de un control.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Sin |<xref:System.Windows.Controls.Primitives.UniformGrid>se utiliza para organizar a los niños en una cuadrícula con todos los tamaños de celda iguales.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Sin |Proporciona una clase base para los paneles que pueden "virtualizar" su colección de elementos secundarios.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sí|Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sí|<xref:System.Windows.Controls.WrapPanel>coloca los elementos secundarios en posición secuencial de izquierda a derecha, rompiendo el contenido a la siguiente línea en el borde del cuadro contenedor. El orden posterior ocurre secuencialmente de arriba a abajo o <xref:System.Windows.Controls.WrapPanel.Orientation%2A> de derecha a izquierda, dependiendo del valor de la propiedad.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Paneles de interfaz de usuario  
 Hay seis clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de panel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] disponibles <xref:System.Windows.Controls.Canvas>que <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>están <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.VirtualizingStackPanel>optimizadas <xref:System.Windows.Controls.WrapPanel>para admitir escenarios: , , , , , , , y . Estos elementos de panel son fáciles de usar, versátiles y suficientemente extensibles para la mayoría de las aplicaciones.  
  
 Cada elemento <xref:System.Windows.Controls.Panel> derivado trata las restricciones de tamaño de forma diferente. Comprender cómo <xref:System.Windows.Controls.Panel> se manejan las restricciones en la dirección horizontal o vertical puede hacer que el diseño sea más predecible.  
  
|**Nombre del panel**|**Dimensión x**|**Dimensión y**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Restringida al contenido|Restringida al contenido|  
|<xref:System.Windows.Controls.DockPanel>|Restringida|Restringida|  
|<xref:System.Windows.Controls.StackPanel>(Orientación vertical)|Restringida|Restringida al contenido|  
|<xref:System.Windows.Controls.StackPanel>(Orientación horizontal)|Restringida al contenido|Restringida|  
|<xref:System.Windows.Controls.Grid>|Restringida|Restringido, excepto en <xref:System.Windows.GridUnitType.Auto> los casos en que se aplican a filas y columnas|  
|<xref:System.Windows.Controls.WrapPanel>|Restringida al contenido|Restringida al contenido|  
  
 A continuación se ofrecen descripciones más detalladas y ejemplos del uso de cada uno de estos elementos.  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>Lienzo  
 El <xref:System.Windows.Controls.Canvas> elemento permite el posicionamiento del contenido de acuerdo con las coordenadas *x* e *y* absolutas. Los elementos se pueden dibujar en una ubicación única o bien, si ocupan las mismas coordenadas, el orden en que aparecen en el marcado determina el orden en que se dibujan.  
  
 <xref:System.Windows.Controls.Canvas>proporciona el soporte de <xref:System.Windows.Controls.Panel>diseño más flexible de cualquier archivo . Las propiedades Height y Width se utilizan para definir el área del lienzo y a <xref:System.Windows.Controls.Canvas>los elementos del interior se les asignan coordenadas absolutas en relación con el área del elemento primario. Cuatro propiedades <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>adjuntas, , <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas>permiten un control preciso de la colocación de objetos dentro de un , lo que permite al desarrollador colocar y organizar los elementos con precisión en la pantalla.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds dentro de un lienzo  
 <xref:System.Windows.Controls.Canvas>puede colocar elementos secundarios en cualquier posición de la pantalla, <xref:System.Windows.FrameworkElement.Height%2A> incluso <xref:System.Windows.FrameworkElement.Width%2A>en coordenadas que están fuera de su propio definido y . Además, <xref:System.Windows.Controls.Canvas> no se ve afectado por el tamaño de sus hijos. Como resultado, es posible que un elemento secundario sobreste desdibujo <xref:System.Windows.Controls.Canvas>excesivo de otros elementos fuera del rectángulo delimitador del elemento primario . El comportamiento predeterminado <xref:System.Windows.Controls.Canvas> de a es permitir que los elementos secundarios se dibujen fuera de los límites del elemento primario. <xref:System.Windows.Controls.Canvas> Si este comportamiento no <xref:System.Windows.UIElement.ClipToBounds%2A> es deseable, `true`la propiedad se puede establecer en . Esto <xref:System.Windows.Controls.Canvas> hace que el clip sea de su propio tamaño. <xref:System.Windows.Controls.Canvas>es el único elemento de diseño que permite dibujar elementos secundarios fuera de sus límites.  
  
 Este comportamiento se muestra gráficamente en el [ejemplo de comparación de las propiedades Width](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
#### <a name="defining-and-using-a-canvas"></a>Definición y uso de un lienzo  
 A <xref:System.Windows.Controls.Canvas> se puede crear [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] una instancia simplemente mediante el uso o el código. En el ejemplo siguiente <xref:System.Windows.Controls.Canvas> se muestra cómo utilizar para colocar absolutamente el contenido. Este código genera tres cuadrados de 100 píxeles. El primer cuadrado es rojo y su posición superior izquierda (*x, y*) se especifica como (0, 0). El segundo cuadrado es verde y su posición superior izquierda es (100, 100), justo debajo y a la derecha del primer cuadrado. El tercer cuadrado es azul y su posición superior izquierda es (50, 50), por lo que abarca el cuadrante inferior derecho del primer cuadrado y el cuadrante superior izquierdo del segundo. Como el tercer cuadrado se coloca en último lugar, pareciera que está encima de los otros dos cuadrados; es decir, las partes que se superponen toman el color del tercer cuadro.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento Canvas típico.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 El <xref:System.Windows.Controls.DockPanel> elemento <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> utiliza la propiedad adjunta como establecida en los elementos de contenido secundario para colocar el contenido a lo largo de los bordes de un contenedor. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> se <xref:System.Windows.Controls.Dock.Top> establece <xref:System.Windows.Controls.Dock.Bottom>en o , coloca elementos secundarios por encima o por debajo uno del otro. Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> se <xref:System.Windows.Controls.Dock.Left> establece <xref:System.Windows.Controls.Dock.Right>en o , coloca los elementos secundarios a la izquierda o a la derecha unos de otros. La <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad determina la posición del elemento final <xref:System.Windows.Controls.DockPanel>agregado como un elemento secundario de un archivo .  
  
 Puede utilizar <xref:System.Windows.Controls.DockPanel> para colocar un grupo de controles relacionados, como un conjunto de botones. Alternativamente, puede usarlo para crear un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"paned", similar al que se encuentra en Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Ajustar el tamaño al contenido  
 Si <xref:System.Windows.FrameworkElement.Height%2A> no <xref:System.Windows.FrameworkElement.Width%2A> se especifican sus <xref:System.Windows.Controls.DockPanel> propiedades, se ajusta a su contenido. El tamaño puede aumentar o disminuir en función del tamaño de los elementos secundarios. Sin embargo, cuando se especifican estas propiedades y ya no <xref:System.Windows.Controls.DockPanel> hay espacio para el siguiente elemento secundario especificado, no muestra ese elemento secundario o elementos secundarios posteriores y no mide los elementos secundarios subsiguientes.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 De forma predeterminada, el <xref:System.Windows.Controls.DockPanel> último elemento secundario de un elemento "rellenará" el espacio restante sin asignar. Si no se desea este <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> comportamiento, establezca la propiedad en `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definición y uso de un elemento DockPanel  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.DockPanel>cómo particionar espacio mediante un archivo . Se <xref:System.Windows.Controls.Border> agregan cinco elementos <xref:System.Windows.Controls.DockPanel>como elementos secundarios de un elemento primario. Cada uno utiliza una propiedad <xref:System.Windows.Controls.DockPanel> de posicionamiento diferente de un espacio de partición. El último elemento "rellena" el espacio que queda sin asignar.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Escenario DockPanel típico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Cuadrícula  
 El <xref:System.Windows.Controls.Grid> elemento combina la funcionalidad de un posicionamiento absoluto y control de datos tabulares. A <xref:System.Windows.Controls.Grid> le permite posicionar y aplicar estilo fácilmente a los elementos. <xref:System.Windows.Controls.Grid>le permite definir agrupaciones flexibles de filas y columnas, e <xref:System.Windows.Controls.Grid> incluso proporciona un mecanismo para compartir información de tamaño entre varios elementos.  
  
#### <a name="how-is-grid-different-from-table"></a>¿En qué se diferencian Grid y Table?  
 <xref:System.Windows.Documents.Table>y <xref:System.Windows.Controls.Grid> compartir algunas funciones comunes, pero cada uno es el más adecuado para diferentes escenarios. A <xref:System.Windows.Documents.Table> está diseñado para su uso dentro del contenido de flujo (consulte [Información general](../advanced/flow-document-overview.md) del documento de flujo para obtener más información sobre el contenido del flujo). Las cuadrículas son más apropiadas para formularios (básicamente, en cualquier lugar excepto en el contenido dinámico). Dentro <xref:System.Windows.Documents.FlowDocument>de <xref:System.Windows.Documents.Table> un , admite comportamientos de contenido de flujo <xref:System.Windows.Controls.Grid> como paginación, reflujo de columna y selección de contenido, mientras que a no. A <xref:System.Windows.Controls.Grid> por otro lado se utiliza <xref:System.Windows.Documents.FlowDocument> mejor fuera <xref:System.Windows.Controls.Grid> de un por muchas razones, incluyendo agrega elementos basados en un índice de fila y columna, <xref:System.Windows.Documents.Table> no lo hace. El <xref:System.Windows.Controls.Grid> elemento permite la creación de capas de contenido secundario, lo que permite que exista más de un elemento dentro de una sola "célula". <xref:System.Windows.Documents.Table>no admite capas. Los elementos <xref:System.Windows.Controls.Grid> secundarios de a se pueden colocar absolutamente en relación con el área de sus límites de "célula". <xref:System.Windows.Documents.Table>no admite esta función. Por último, un <xref:System.Windows.Controls.Grid> es <xref:System.Windows.Documents.Table>más ligero que un .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Comportamiento del ajuste de tamaño de las columnas y las filas  
 Las columnas y <xref:System.Windows.Controls.Grid> filas definidas <xref:System.Windows.GridUnitType.Star> dentro de un pueden aprovechar el tamaño para distribuir el espacio restante proporcionalmente. Cuando <xref:System.Windows.GridUnitType.Star> se selecciona como Altura o Ancho de una fila o columna, esa columna o fila recibe una proporción ponderada del espacio disponible restante. Esto contrasta <xref:System.Windows.GridUnitType.Auto>con , que distribuirá el espacio uniformemente en función del tamaño del contenido dentro de una columna o fila. Este valor se expresa como `*` o `2*` cuando se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. En el primer caso, la fila o la columna recibiría una vez el espacio disponible, en el segundo caso, dos veces, y así sucesivamente. Mediante la combinación de esta <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> técnica <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> para `Stretch` distribuir proporcionalmente el espacio con un y el valor de la misma es posible particionar el espacio de diseño por porcentaje de espacio de pantalla. <xref:System.Windows.Controls.Grid>es el único panel de diseño que puede distribuir espacio de esta manera.  
  
#### <a name="defining-and-using-a-grid"></a>Definición y uso de una cuadrícula  
 En el ejemplo siguiente se [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muestra cómo crear un similar al que se encuentra en el cuadro de diálogo Ejecutar disponible en el menú Inicio de Windows.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento de cuadrícula típico.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 A <xref:System.Windows.Controls.StackPanel> le permite "apilar" elementos en una dirección asignada. De forma predeterminada, los elementos se apilan en dirección vertical. La <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad se puede utilizar para controlar el flujo de contenido.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel vs. DockPanel  
 Aunque <xref:System.Windows.Controls.DockPanel> también puede "apilar" elementos secundarios <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel> no producir resultados análogos en algunos escenarios de uso. Por ejemplo, el orden de los elementos secundarios <xref:System.Windows.Controls.StackPanel>puede afectar a su tamaño en un <xref:System.Windows.Controls.DockPanel> archivo . Esto se <xref:System.Windows.Controls.StackPanel> debe a que mide en la dirección de apilamiento en <xref:System.Double.PositiveInfinity>, mientras que <xref:System.Windows.Controls.DockPanel> mientras que mide sólo el tamaño disponible.  
  
 En el ejemplo siguiente se muestra esta diferencia clave.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La diferencia en cuanto al comportamiento de representación se puede ver en esta imagen.  
  
 ![Captura de pantalla: Captura de pantalla de StackPanel frente a DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definición y uso de un elemento StackPanel  
 En el ejemplo siguiente se <xref:System.Windows.Controls.StackPanel> muestra cómo utilizar a para crear un conjunto de botones posicionados verticalmente. Para el posicionamiento <xref:System.Windows.Controls.StackPanel.Orientation%2A> horizontal, <xref:System.Windows.Controls.Orientation.Horizontal>establezca la propiedad en .  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento StackPanel típico.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también proporciona una <xref:System.Windows.Controls.StackPanel> variación del elemento que automáticamente "virtualiza" el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica por la que se genera un subconjunto de elementos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel>(a través <xref:System.Windows.Controls.VirtualizingPanel>de la funcionalidad proporcionada por <xref:System.Windows.Controls.ItemContainerGenerator> ) <xref:System.Windows.Controls.ItemsControl> calcula <xref:System.Windows.Controls.ListBox> los <xref:System.Windows.Controls.ListView>elementos visibles y funciona con el from an (como o ) para crear solo elementos para los elementos visibles.  
  
 El <xref:System.Windows.Controls.VirtualizingStackPanel> elemento se establece automáticamente como el <xref:System.Windows.Controls.ListBox>host de elementos para controles como el archivo . Al hospedar una colección enlazada a datos, el contenido se virtualiza <xref:System.Windows.Controls.ScrollViewer>automáticamente, siempre que el contenido esté dentro de los límites de un archivo . Esto mejora notablemente el rendimiento cuando se hospedan muchos elementos secundarios.  
  
 El marcado siguiente muestra cómo <xref:System.Windows.Controls.VirtualizingStackPanel> usar un como host de elementos. La <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> propiedad adjunta debe `true` establecerse en (valor predeterminado) para que se produzca la virtualización.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>se utiliza para colocar elementos secundarios en posición secuencial de izquierda a derecha, rompiendo el contenido a la siguiente línea cuando llega al borde de su contenedor primario. El contenido se puede orientar horizontal o verticalmente. <xref:System.Windows.Controls.WrapPanel>es útil para [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios de flujo simples. También se puede usar para aplicar un tamaño uniforme a todos sus elementos secundarios.  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.WrapPanel> muestra <xref:System.Windows.Controls.Button> cómo crear un para mostrar los controles que se ajustan cuando llegan al borde de su contenedor.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento WrapPanel típico.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Elementos Panel anidados  
 <xref:System.Windows.Controls.Panel>los elementos se pueden anidar entre sí para producir diseños complejos. Esto puede resultar muy útil <xref:System.Windows.Controls.Panel> en situaciones donde [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]uno es ideal para una porción [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]de un , pero puede no satisfacer las necesidades de una porción diferente de la .  
  
 No existe ningún límite práctico para la cantidad de anidamiento que puede admitir la aplicación; sin embargo, en general se recomienda limitar la aplicación para que use solo los paneles que son realmente necesarios para el diseño que se desea. En muchos casos, se puede utilizar un <xref:System.Windows.Controls.Grid> elemento en lugar de paneles anidados debido a su flexibilidad como contenedor de diseño. Esto puede aumentar el rendimiento de una aplicación al dejar fuera del árbol los elementos innecesarios.  
  
 En el ejemplo siguiente se [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muestra cómo <xref:System.Windows.Controls.Panel> crear un que aprovecha los elementos anidados para lograr un diseño específico. En este caso <xref:System.Windows.Controls.DockPanel> concreto, se [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utiliza un <xref:System.Windows.Controls.StackPanel> elemento para <xref:System.Windows.Controls.Grid>proporcionar <xref:System.Windows.Controls.Canvas> estructura y los elementos anidados, un , y a se utilizan para colocar elementos secundarios precisamente dentro del elemento primario. <xref:System.Windows.Controls.DockPanel>  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 La aplicación compilada genera una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![IU que aprovecha los paneles anidados.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Elementos Panel personalizados  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una matriz de controles de diseño flexibles, los <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> comportamientos de diseño personalizados también se pueden lograr reemplazando los métodos y. <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Es posible ajustar de forma personalizada el tamaño y la posición si se definen nuevos comportamientos de posicionamiento mediante estos métodos de invalidación.  
  
 De forma similar, los comportamientos de <xref:System.Windows.Controls.Canvas> diseño <xref:System.Windows.Controls.Grid>personalizados basados en <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> clases derivadas (como o ) se pueden definir reemplazando sus métodos y.  
  
 El marcado siguiente muestra cómo <xref:System.Windows.Controls.Panel> crear un elemento personalizado. Este <xref:System.Windows.Controls.Panel>nuevo , `PlotPanel`definido como , admite el posicionamiento de elementos secundarios mediante el uso de coordenadas *x* e *y* codificadas de forma rígida. En este ejemplo, un <xref:System.Windows.Shapes.Rectangle> elemento (no se muestra) se coloca en el punto de trazado 50 (*x*) y 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Para ver una implementación de un panel personalizado más complejo, consulte el [ejemplo de creación de un panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Compatibilidad para la localización y globalización  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite diversas características que facilitan la creación de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizable.  
  
 Todos los elementos <xref:System.Windows.FrameworkElement.FlowDirection%2A> del panel admiten de forma nativa la propiedad, que se puede usar para volver a fluir dinámicamente el contenido en función de la configuración regional o de idioma de un usuario. Para más información, consulte <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La <xref:System.Windows.Window.SizeToContent%2A> propiedad proporciona un mecanismo que permite a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]los desarrolladores de aplicaciones anticipar las necesidades de localizada . Con <xref:System.Windows.SizeToContent.WidthAndHeight> el valor de esta <xref:System.Windows.Window> propiedad, un elemento primario siempre ajusta el tamaño dinámicamente para ajustarse al contenido y no está restringido por restricciones artificiales de alto o ancho.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel> y son todas [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]buenas opciones para localizable . <xref:System.Windows.Controls.Canvas>no es una buena opción, sin embargo, porque posiciona el contenido absolutamente, lo que dificulta la localización.  
  
 Para obtener información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] adicional sobre la creación de aplicaciones con interfaces de usuario localizables (UI), consulte Usar información general sobre [diseño sautomático](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Consulte también

- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Ejemplo WPF Layout Gallery](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Diseño](../advanced/layout.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
- [Información general sobre alineación, márgenes y relleno](../advanced/alignment-margins-and-padding-overview.md)
- [Ejemplo de creación de un panel de ajuste de contenido personalizado](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Información general sobre propiedades asociadas](../advanced/attached-properties-overview.md)
- [Información general sobre el uso del diseño automático](../advanced/use-automatic-layout-overview.md)
- [Presentación y diseño](../advanced/optimizing-performance-layout-and-design.md)
