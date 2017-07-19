---
title: "Informaci&#243;n general sobre elementos Panel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles, Panel"
  - "Panel (control) [WPF], acerca del control Panel"
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: 48
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 45
---
# Informaci&#243;n general sobre elementos Panel
Los elementos <xref:System.Windows.Controls.Panel> son componentes que controlan la representación de los elementos: su tamaño y dimensiones, su posición y la disposición de su contenido secundario.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona varios elementos <xref:System.Windows.Controls.Panel> predefinidos, así como la posibilidad de construir elementos <xref:System.Windows.Controls.Panel> personalizados.  
  
 Este tema contiene las secciones siguientes.  
  
-   [La clase Panel](#Panels_view_from_10000_feet)  
  
-   [Miembros comunes de los elementos Panel](#Panels_declared_members)  
  
-   [Elementos Panel derivados](#Panels_derived_elements)  
  
-   [Paneles de interfaz de usuario](#Panels_main_UI_elements)  
  
-   [Elementos Panel anidados](#Panels_nested_panel_elements)  
  
-   [Elementos Panel personalizados](#Panels_custom_panel_elements)  
  
-   [Compatibilidad para la localización y globalización](#Panels_global_localization)  
  
-   [Temas relacionados](#seeAlsoToggle)  
  
<a name="Panels_view_from_10000_feet"></a>   
## La clase Panel  
 <xref:System.Windows.Controls.Panel> es la clase base para todos los elementos que proporcionan la compatibilidad de diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Los elementos <xref:System.Windows.Controls.Panel> derivados se utilizan para colocar y organizar elementos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un conjunto completo de implementaciones de panel derivadas que permiten numerosos diseños complejos.  Estas clases derivadas exponen propiedades y métodos que habilitan la mayoría de los escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] estándar.  Los programadores que no encuentren un comportamiento de disposición secundario acorde con sus necesidades pueden crear diseños nuevos que invaliden los métodos <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  Para obtener más información sobre los comportamientos de diseño personalizados, vea [Elementos Panel personalizados](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## Miembros comunes de los elementos Panel  
 Todos los elementos <xref:System.Windows.Controls.Panel> son compatibles con las propiedades básicas de posición y dimensionamiento definidas por <xref:System.Windows.FrameworkElement>, como son <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> y <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  Para obtener información adicional sobre las propiedades de posición definidas por <xref:System.Windows.FrameworkElement>, vea [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> expone propiedades adicionales que son de importancia crítica para entender y utilizar el diseño.  La propiedad <xref:System.Windows.Controls.Panel.Background%2A> se utiliza para rellenar el área existente entre los límites de un elemento de panel derivado con un objeto <xref:System.Windows.Media.Brush>.  <xref:System.Windows.Controls.Panel.Children%2A> representa la colección secundaria de elementos que forman el elemento <xref:System.Windows.Controls.Panel>.  <xref:System.Windows.Controls.Panel.InternalChildren%2A> representa el contenido de la colección <xref:System.Windows.Controls.Panel.Children%2A> junto con los miembros generados mediante el enlace de datos.  Ambos se componen de una colección <xref:System.Windows.Controls.UIElementCollection> de elementos secundarios hospedados en el elemento <xref:System.Windows.Controls.Panel> primario.  
  
 El panel también expone una propiedad adjunta <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> que se puede utilizar para lograr un orden dispuesto en capas en un elemento <xref:System.Windows.Controls.Panel> derivado.  Los miembros de la colección <xref:System.Windows.Controls.Panel.Children%2A> de un panel cuyo valor de <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> es mayor aparecen delante de los que tienen un valor de <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> menor.  Esto es especialmente útil para los paneles como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.Grid>, que permiten a los elementos secundarios compartir el mismo espacio de coordenadas.  
  
 <xref:System.Windows.Controls.Panel> también define el método <xref:System.Windows.Controls.Panel.OnRender%2A>, que se puede utilizar para invalidar el comportamiento de presentación predeterminado de un elemento <xref:System.Windows.Controls.Panel>.  
  
#### Propiedades adjuntas  
 Los elementos de panel derivados utilizan mucho las [propiedades adjuntas](GTMT).  Una propiedad adjunta es una forma especializada de [propiedad de dependencia](GTMT) que no tiene el "contenedor" de propiedades de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] convencional.  Las propiedades adjuntas tienen una sintaxis especializada en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], que se puede ver en algunos de los ejemplos que siguen.  
  
 Uno de los propósitos de una propiedad adjunta es permitir a los elementos secundarios almacenar valores únicos de una propiedad que en realidad está definida por un elemento principal.  Una aplicación de esta funcionalidad consiste en tener elementos secundarios que informen al elemento primario sobre cómo desean ser presentados en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], lo que resulta sumamente útil para el diseño de la aplicación.  Para obtener más información, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## Elementos Panel derivados  
 Muchos objetos se derivan de <xref:System.Windows.Controls.Panel>, pero no todos ellos están pensados para usarlos como proveedores de diseño raíz.  Existen seis clases de panel definidas \(<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> y <xref:System.Windows.Controls.WrapPanel>\) que están diseñadas específicamente para crear la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de las aplicaciones.  
  
 Cada elemento de panel encapsula su propia funcionalidad especial, como se muestra en la tabla siguiente.  
  
|Nombre del elemento|¿Es un panel de interfaz de usuario?|Descripción|  
|-------------------------|------------------------------------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Sí|Define un área en la que pueden colocarse explícitamente los elementos secundarios utilizando las coordenadas relativas al área del control <xref:System.Windows.Controls.Canvas>.|  
|<xref:System.Windows.Controls.DockPanel>|Sí|Define un área en la que se pueden organizar horizontal o verticalmente los elementos secundarios, uno respecto al otro.|  
|<xref:System.Windows.Controls.Grid>|Sí|Define un área de cuadrícula flexible que se compone de columnas y filas.  Los elementos secundarios de un control <xref:System.Windows.Controls.Grid> se pueden colocar con precisión utilizando la propiedad <xref:System.Windows.FrameworkElement.Margin%2A>.|  
|<xref:System.Windows.Controls.StackPanel>|Sí|Organiza los elementos secundarios en una única línea que se puede orientar horizontal o verticalmente.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|No|Controla el diseño de los botones de las fichas de un control <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|No|Organiza el contenido dentro de un control <xref:System.Windows.Controls.ToolBar>.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|No|<xref:System.Windows.Controls.Primitives.UniformGrid> se utiliza para organizar los elementos secundarios en una cuadrícula cuyas celdas tienen todas el mismo tamaño.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|No|Proporciona una clase base para los paneles que pueden "virtualizar" su colección de elementos secundarios.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Sí|Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.|  
|<xref:System.Windows.Controls.WrapPanel>|Sí|<xref:System.Windows.Controls.WrapPanel> organiza los elementos secundarios secuencialmente de izquierda a derecha y traslada el contenido a la línea siguiente cuando alcanza el borde del cuadro contenedor.  La clasificación siguiente se realiza secuencialmente de arriba abajo o de izquierda a derecha, en función del valor de la propiedad <xref:System.Windows.Controls.WrapPanel.Orientation%2A>.|  
  
<a name="Panels_main_UI_elements"></a>   
## Paneles de interfaz de usuario  
 Existen seis clases de paneles disponibles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que están optimizadas para admitir los escenarios de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> y <xref:System.Windows.Controls.WrapPanel>.  Estos elementos de panel son fáciles utilizar, versátiles y suficientemente extensibles para la mayoría de las aplicaciones.  
  
 Cada elemento <xref:System.Windows.Controls.Panel> derivado trata las restricciones de tamaño de forma distinta.  La comprensión del modo en que un elemento <xref:System.Windows.Controls.Panel> controla las restricciones en la dirección horizontal o vertical puede hacer que el diseño sea más predecible.  
  
|**Nombre del panel**|**Dimensión x**|**Dimensión y**|  
|--------------------------|---------------------|---------------------|  
|<xref:System.Windows.Controls.Canvas>|Restringida al contenido|Restringida al contenido|  
|<xref:System.Windows.Controls.DockPanel>|Restringida|Restringida|  
|<xref:System.Windows.Controls.StackPanel> \(Orientación vertical\)|Restringida|Restringida al contenido|  
|<xref:System.Windows.Controls.StackPanel> \(Orientación horizontal\)|Restringida al contenido|Restringida|  
|<xref:System.Windows.Controls.Grid>|Restringida|Restringida, excepto en los casos en que <xref:System.Windows.GridUnitType> se aplica a las filas y las columnas|  
|<xref:System.Windows.Controls.WrapPanel>|Restringida al contenido|Restringida al contenido|  
  
 A continuación se ofrecen descripciones más detalladas y ejemplos del uso de cada uno de estos elementos.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### Canvas  
 El elemento <xref:System.Windows.Controls.Canvas> permite la colocación del contenido de acuerdo con unas coordenadas *x* e *y* absolutas.  Los elementos se pueden dibujar en una ubicación única; o, si ocupan las mismas coordenadas, el orden en que aparecen en el marcado determina el orden en el que se dibujan.  
  
 <xref:System.Windows.Controls.Canvas> proporciona la compatibilidad de diseño más flexible de todos los elementos <xref:System.Windows.Controls.Panel>.  Las propiedades Height y Width se utilizan para definir el área del lienzo, y a los elementos que contiene se les asignan coordenadas absolutas relativas al área del elemento <xref:System.Windows.Controls.Canvas> primario.  Cuatro propiedades adjuntas, <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=fullName> y <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=fullName>, permiten obtener un control muy preciso de la posición de los objetos dentro de un elemento <xref:System.Windows.Controls.Canvas>, y gracias a ellas el programador puede colocar y organizar con precisión los elementos en la pantalla.  
  
#### ClipToBounds dentro de un lienzo  
 <xref:System.Windows.Controls.Canvas> puede colocar los elementos secundarios en cualquier posición de la pantalla, incluso en coordenadas situadas fuera de sus propias dimensiones, definidas mediante <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A>.  Además, el tamaño de sus propios elementos secundarios no afecta a <xref:System.Windows.Controls.Canvas>.  Como resultado, es posible que un elemento secundario se dibuje sobre otros elementos situados fuera del rectángulo delimitador del elemento <xref:System.Windows.Controls.Canvas> primario.  El comportamiento predeterminado de un elemento <xref:System.Windows.Controls.Canvas> es permitir que se dibujen elementos secundarios fuera de los límites del elemento <xref:System.Windows.Controls.Canvas> primario.  Si no desea que esto ocurra, puede establecer la propiedad <xref:System.Windows.UIElement.ClipToBounds%2A> en `true`.  Esto hace que <xref:System.Windows.Controls.Canvas> se recorte a su propio tamaño.  <xref:System.Windows.Controls.Canvas> es el único elemento de diseño que permite dibujar los elementos secundarios fuera sus límites.  
  
 Este comportamiento se muestra gráficamente en [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
#### Definir y utilizar un lienzo  
 Es posible crear instancias de un elemento <xref:System.Windows.Controls.Canvas> simplemente con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o mediante código.  En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Controls.Canvas> para colocar el contenido de forma absoluta.  Este código genera tres cuadrados de 100 píxeles.  El primer cuadrado es rojo y su posición superior izquierda \(*x, y*\) se especifica como \(0, 0\).  El segundo cuadrado es verde y su posición superior izquierda es \(100, 100\), que es inmediatamente debajo y a la derecha del primer cuadrado.  El tercer cuadrado es azul y su posición superior izquierda es \(50, 50\), por lo que cubre el cuadrante inferior derecho del primer cuadrado y el cuadrante superior izquierdo del segundo.  Dado que el tercer cuadrado se coloca en último lugar, parece que está encima de los otros dos cuadrados; es decir, las partes que se superponen adoptan el color del tercer cuadrado.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento Canvas típico.](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.png "panel\_intro\_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### DockPanel  
 El elemento <xref:System.Windows.Controls.DockPanel> utiliza la propiedad adjunta <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> tal y como está establecida en los elementos de contenido secundarios para colocar el contenido a lo largo de los bordes de un contenedor.  Cuando <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> se establece en <xref:System.Windows.Controls.Dock> o <xref:System.Windows.Controls.Dock>, coloca los elementos secundarios por encima o por debajo de los demás.  Cuando la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> está establecida en <xref:System.Windows.Controls.Dock> o en <xref:System.Windows.Controls.Dock>, coloca los elementos secundarios a la izquierda o a la derecha de los demás.  La propiedad <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> determina la posición del último elemento agregado como un elemento secundario de un elemento <xref:System.Windows.Controls.DockPanel>.  
  
 Puede utilizar <xref:System.Windows.Controls.DockPanel> para colocar un grupo de controles relacionados, como un conjunto de botones.  También puede utilizarlo para crear una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] "con paneles", similar a la de [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### Ajustar el tamaño al contenido  
 Si no se especifican las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Controls.DockPanel> se ajusta a su contenido.  Su tamaño puede aumentar o disminuir de acuerdo con el tamaño de sus elementos secundarios.  Sin embargo, cuando se especifican estas propiedades y ya no hay sitio para el siguiente elemento secundario especificado, <xref:System.Windows.Controls.DockPanel> no muestra ese elemento secundario ni los elementos secundarios subsiguientes, y no mide los elementos secundarios subsiguientes.  
  
#### LastChildFill  
 De forma predeterminada, el último elemento secundario de un elemento <xref:System.Windows.Controls.DockPanel> "rellenará" el espacio restante que quede sin asignar.  Si no desea que esto ocurra, establezca la propiedad <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> en `false`.  
  
#### Definir y utilizar un elemento DockPanel  
 En el ejemplo siguiente se muestra cómo dividir el espacio mediante <xref:System.Windows.Controls.DockPanel>.  Se agregan cinco elementos <xref:System.Windows.Controls.Border> como elementos secundarios de un elemento <xref:System.Windows.Controls.DockPanel> primario.  Cada uno de ellos utiliza una propiedad de posición diferente de un elemento <xref:System.Windows.Controls.DockPanel> para dividir el espacio.  El último elemento "rellena" el espacio que queda sin asignar.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Escenario DockPanel típico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### Cuadrícula  
 El elemento <xref:System.Windows.Controls.Grid> combina la funcionalidad de una posición absoluta y de un control de datos tabular.  <xref:System.Windows.Controls.Grid> permite colocar con facilidad elementos y aplicarles estilo.  Con <xref:System.Windows.Controls.Grid> podrá definir agrupaciones flexibles de filas y columnas, e incluso dispone de un mecanismo para compartir información de tamaño entre varios elementos <xref:System.Windows.Controls.Grid>.  
  
#### ¿En qué se diferencian Grid y Table?  
 <xref:System.Windows.Documents.Table> y <xref:System.Windows.Controls.Grid> comparten funcionalidades comunes, pero cada elemento es más apropiado para determinados escenarios.  <xref:System.Windows.Documents.Table> se ha diseñado para su uso en contenido dinámico \(vea [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md) para obtener más información sobre el contenido dinámico\).  Las cuadrículas son más apropiadas para formularios \(básicamente, en cualquier lugar excepto en el contenido dinámico\).  Dentro de un <xref:System.Windows.Documents.FlowDocument>, una <xref:System.Windows.Documents.Table> admite los comportamientos del contenido dinámico, como la paginación, el ajuste dinámico de columnas y la selección de contenido, mientras que <xref:System.Windows.Controls.Grid> no.  Por su parte, <xref:System.Windows.Controls.Grid> es más apropiado fuera de un <xref:System.Windows.Documents.FlowDocument> por numerosas razones; una de ellas es que <xref:System.Windows.Controls.Grid> agrega elementos basándose en un índice de fila y columna, y <xref:System.Windows.Documents.Table> no.  El elemento <xref:System.Windows.Controls.Grid> permite la disposición en capas del contenido secundario, lo que permite que haya más de un elemento dentro de una sola "celda". <xref:System.Windows.Documents.Table> no admite la disposición en capas.  Los elementos secundarios de <xref:System.Windows.Controls.Grid> se pueden colocar de manera absoluta en relación con el área de los límites de la "celda".  <xref:System.Windows.Documents.Table> no admite esta característica.  Por último, <xref:System.Windows.Controls.Grid> es más ligero que <xref:System.Windows.Documents.Table>.  
  
#### Comportamiento del ajuste de tamaño de las columnas y las filas  
 Las columnas y las filas definidas dentro de un elemento <xref:System.Windows.Controls.Grid> pueden sacar partido del ajuste de tamaño mediante <xref:System.Windows.GridUnitType> para distribuir el espacio restante de forma proporcional.  Cuando se selecciona <xref:System.Windows.GridUnitType> como el alto o el ancho de una fila o una columna, dicha columna o fila recibe una proporción ponderada del espacio restante disponible.  Por el contrario, <xref:System.Windows.GridUnitType> distribuye el espacio de manera uniforme basándose en el tamaño del contenido de una columna o una fila.  Este valor se expresa como `*` o `2*` al utilizar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  En el primer caso, la fila o la columna recibiría una vez el espacio disponible, en el segundo caso, dos veces, y así sucesivamente.  Combinando esta técnica para distribuir proporcionalmente el espacio con un valor para <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> y <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> de `Stretch`, es posible dividir el espacio de diseño en un porcentaje del espacio de pantalla.  <xref:System.Windows.Controls.Grid> es el único panel de diseño en el que se puede distribuir el espacio de esta manera.  
  
#### Definir y utilizar una cuadrícula  
 En el ejemplo siguiente se muestra cómo compilar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] similar a la del cuadro de diálogo Ejecutar del menú Inicio de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento de cuadrícula típico.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.png "avalon\_run\_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### StackPanel  
 Un elemento <xref:System.Windows.Controls.StackPanel> le permite "apilar" los elementos en una dirección asignada.  De forma predeterminada, los elementos se apilan en dirección vertical.  Se puede utilizar la propiedad <xref:System.Windows.Controls.StackPanel.Orientation%2A> para controlar el flujo del contenido.  
  
#### Comparación entre StackPanel yDockPanel  
 Aunque <xref:System.Windows.Controls.DockPanel> también puede "apilar" elementos secundarios, <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel> no generan resultados análogos en algunos escenarios de uso.  Por ejemplo, el orden en el que se colocan los elementos secundarios puede afectar a su tamaño en un elemento <xref:System.Windows.Controls.DockPanel> pero no en un elemento <xref:System.Windows.Controls.StackPanel>.  Esto se debe a que <xref:System.Windows.Controls.StackPanel> mide en la dirección del apilado en <xref:System.Double.PositiveInfinity>, mientras que <xref:System.Windows.Controls.DockPanel> mide solo el tamaño disponible.  
  
 En el ejemplo siguiente se muestra esta diferencia fundamental.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 La diferencia en cuanto al comportamiento de representación se puede ver en esta imagen.  
  
 ![Captura de pantalla: StackPanel frente a Captura de pantalla de DockPanel](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.png "layout\_smiley\_stackpanel")  
  
#### Definir y utilizar un elemento StackPanel  
 En el ejemplo siguiente se muestra cómo utilizar un elemento <xref:System.Windows.Controls.StackPanel> para crear un conjunto de botones colocados verticalmente.  Para colocarlos horizontalmente, establezca la propiedad <xref:System.Windows.Controls.StackPanel.Orientation%2A> en <xref:System.Windows.Controls.Orientation>.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento StackPanel típico.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.png "panel\_intro\_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona una variación del elemento <xref:System.Windows.Controls.StackPanel> que "virtualiza" automáticamente el contenido secundario enlazado a datos.  En este contexto, el término "virtualizar" se refiere a una técnica por la que se genera un subconjunto de elementos a partir de un número mayor de elementos de datos en función de los elementos que están visibles en pantalla.  Generar un gran número de elementos de interfaz de usuario cuando sólo pueden estar en pantalla algunos de ellos en un momento dado, requiere un uso intensivo, tanto de la memoria como del procesador.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel>\) calcula los elementos visibles y trabaja con <xref:System.Windows.Controls.ItemContainerGenerator> desde un control <xref:System.Windows.Controls.ItemsControl> \(como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>\) para crear elementos únicamente para los elementos visibles.  
  
 El elemento <xref:System.Windows.Controls.VirtualizingStackPanel> se establece automáticamente como el host de elementos para controles como <xref:System.Windows.Controls.ListBox>.  Al hospedar una colección enlazada a datos, el contenido se virtualiza automáticamente, siempre que el contenido esté dentro de los límites de un elemento <xref:System.Windows.Controls.ScrollViewer>.  Esto mejora notablemente el rendimiento cuando se hospedan muchos elementos secundarios.  
  
 El marcado siguiente muestra cómo utilizar un elemento <xref:System.Windows.Controls.VirtualizingStackPanel> como un host de elementos.  La [propiedad adjunta](GTMT) <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> debe estar establecida en `true` \(valor predeterminado\) para que se produzca la virtualización.  
  
 [!code-xml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> se utiliza para colocar de izquierda a derecha los elementos secundarios en posición secuencial, y traslada el contenido a la línea siguiente cuando alcanza el borde de su contenedor primario.  El contenido se puede orientar en sentido horizontal o vertical.  <xref:System.Windows.Controls.WrapPanel> resulta útil para los escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de flujo sencillo.  También se puede utilizar para aplicar un tamaño uniforme a todos sus elementos secundarios.  
  
 En el ejemplo siguiente se muestra cómo crear un elemento <xref:System.Windows.Controls.WrapPanel> para mostrar controles <xref:System.Windows.Controls.Button> que se ajustan cuando llegan al borde de su contenedor.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![Elemento WrapPanel típico.](../../../../docs/framework/wpf/controls/media/wrappanel-element.png "WrapPanel\_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## Elementos Panel anidados  
 Los elementos <xref:System.Windows.Controls.Panel> pueden anidarse unos dentro de otros para generar los diseños complejos.  Esto puede resultar muy útil en situaciones en las que un elemento <xref:System.Windows.Controls.Panel> es ideal para una parte de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], pero no puede satisfacer las necesidades de otra parte de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 No existe ningún límite real a la cantidad de anidamiento que puede admitir una aplicación; sin embargo, en general conviene limitar la aplicación para que utilice sólo los paneles que son realmente necesarios para el diseño que se desea.  En muchos casos, se puede utilizar un elemento <xref:System.Windows.Controls.Grid> en lugar de paneles anidados debido a su flexibilidad como contenedor de diseño.  Esto puede aumentar el rendimiento de una aplicación al dejar fuera del árbol los elementos innecesarios.  
  
 En el ejemplo siguiente se muestra cómo crear una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que hace uso de elementos <xref:System.Windows.Controls.Panel> anidados para lograr un diseño concreto.  En este caso concreto, se usa un elemento <xref:System.Windows.Controls.DockPanel> para proporcionar la estructura de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y elementos <xref:System.Windows.Controls.StackPanel> anidados, un elemento <xref:System.Windows.Controls.Grid> y un elemento <xref:System.Windows.Controls.Canvas> para colocar con precisión los elementos secundarios dentro del elemento <xref:System.Windows.Controls.DockPanel> primario.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 La aplicación compilada produce una nueva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con esta apariencia.  
  
 ![IU que aprovecha los paneles anidados.](../../../../docs/framework/wpf/controls/media/nested-panels.png "nested\_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## Elementos Panel personalizados  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una serie de controles de diseño flexibles, también se pueden lograr comportamientos de diseño personalizados invalidando los métodos <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  Es posible ajustar de forma personalizada el tamaño y la posición definiendo nuevos comportamientos de posición mediante estos métodos de invalidación.  
  
 De igual forma, los comportamientos de diseño personalizados basados en clases derivadas \(como <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.Grid>\) se pueden definir invalidando sus métodos <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> y <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
 En el marcado siguiente se muestra cómo crear un elemento <xref:System.Windows.Controls.Panel> personalizado.  Este nuevo elemento <xref:System.Windows.Controls.Panel>, definido como `PlotPanel`, admite la posición de elementos secundarios a través del uso de coordenadas *x* e *y* incluidas en el código.  En este ejemplo, se coloca un elemento <xref:System.Windows.Shapes.Rectangle> \(no se muestra\) en las coordenadas 50 \(*x*\) y 50 \(*y*\).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Para obtener una implementación de un panel personalizado más complejo, vea [Create a Custom Content\-Wrapping Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## Compatibilidad para la localización y globalización  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite diversas características que facilitan la creación de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizable.  
  
 Todos los elementos Panel admiten de forma nativa la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>, que se puede utilizar para alterar dinámicamente el flujo del contenido basándose en la configuración regional o de idioma del usuario.  Para obtener más información, vea <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 La propiedad <xref:System.Windows.Window.SizeToContent%2A> proporciona un mecanismo que permite a los programadores de aplicaciones anticiparse a las necesidades de localización de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Con el valor <xref:System.Windows.SizeToContent> de esta propiedad, un elemento <xref:System.Windows.Window> primario siempre ajusta su tamaño dinámicamente de acuerdo con el contenido y no está sujeto a restricciones artificiales en cuanto al alto o al ancho.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.StackPanel> son buenas opciones para crear una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] localizable.  Sin embargo, <xref:System.Windows.Controls.Canvas> no es adecuada, porque sitúa el contenido de forma absoluta, lo que hace que sea difícil su localización.  
  
 Para obtener información adicional sobre cómo crear aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] localizables, vea [Información general sobre el uso del diseño automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md).  
  
## Vea también  
 [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [WPF Layout Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160054)   
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)   
 [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Create a Custom Content\-Wrapping Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159979)   
 [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [Información general sobre el uso del diseño automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)