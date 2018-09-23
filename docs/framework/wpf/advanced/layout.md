---
title: Diseño
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
ms.openlocfilehash: 869780f2b6a625923ce869bcaafbbd2319f6cb23
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703029"
---
# <a name="layout"></a>Diseño
En este tema se describe el sistema de diseño de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Comprender cómo y cuándo se producen los cálculos de diseño es esencial para crear interfaces de usuario en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
-   [Rectángulos de selección de elementos](#LayoutSystem_BoundingBox)  
  
-   [El sistema de diseño](#LayoutSystem_Overview)  
  
-   [Medición y organización de elementos secundarios](#LayoutSystem_Measure_Arrange)  
  
-   [Elementos de panel y comportamientos de diseño personalizados](#LayoutSystem_PanelsCustom)  
  
-   [Consideraciones del rendimiento del diseño](#LayoutSystem_Performance)  
  
-   [Representación de subpíxeles y redondeo del diseño](#LayoutSystem_LayoutRounding)  
  
-   [Pasos adicionales](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Rectángulos de selección de elementos  
 Al pensar en diseño en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es importante entender el rectángulo de selección que rodea todos los elementos. Cada <xref:System.Windows.FrameworkElement> consumido por el diseño del sistema se puede considerar como un rectángulo que se ha asignado en el diseño. La <xref:System.Windows.Controls.Primitives.LayoutInformation> clase devuelve los límites de asignación del diseño de un elemento o ranura. El tamaño del rectángulo se determina calculando el espacio disponible en pantalla, el tamaño de las restricciones, las propiedades específicas del diseño (como los márgenes y relleno) y el comportamiento individual del elemento primario <xref:System.Windows.Controls.Panel> elemento. Procesamiento de estos datos, el sistema de diseño es capaz de calcular la posición de todos los elementos secundarios de una determinada <xref:System.Windows.Controls.Panel>. Es importante recordar que las características de ajuste de tamaño definido en el elemento primario, como un <xref:System.Windows.Controls.Border>, afectan a sus elementos secundarios.  
  
 En la siguiente ilustración se muestra un diseño sencillo.  
  
 ![Cuadrícula típica sin rectángulo de selección superpuesto.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Este diseño se puede lograr con el siguiente código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Una sola <xref:System.Windows.Controls.TextBlock> elemento se hospeda dentro de un <xref:System.Windows.Controls.Grid>. Aunque el texto rellena solo en la esquina superior izquierda de la primera columna, el espacio asignado para el <xref:System.Windows.Controls.TextBlock> es mucho mayor. El cuadro de límite de cualquier <xref:System.Windows.FrameworkElement> se puede recuperar mediante el <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> método. La ilustración siguiente muestra el cuadro de límite para el <xref:System.Windows.Controls.TextBlock> elemento.  
  
 ![El rectángulo de selección de TextBlock está visible ahora.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Como se muestra en el rectángulo amarillo, el espacio asignado para el <xref:System.Windows.Controls.TextBlock> elemento es mucho mayor de lo que parece. Cuando se agregan elementos adicionales a la <xref:System.Windows.Controls.Grid>, podría reducir o expandir, dependiendo del tipo y tamaño de los elementos que se agregan esta asignación.  
  
 La ranura de diseño de la <xref:System.Windows.Controls.TextBlock> se traduce en un <xref:System.Windows.Shapes.Path> utilizando el <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> método. Esta técnica puede ser útil para mostrar el rectángulo de selección de un elemento.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>El sistema de diseño  
 En su forma más simple, el diseño es un sistema recursivo que permite dibujar y situar un elemento, así como cambiar su tamaño. Más concretamente, el diseño describe el proceso de medir y organizar los miembros de un <xref:System.Windows.Controls.Panel> del elemento <xref:System.Windows.Controls.Panel.Children%2A> colección. El diseño es un proceso intensivo. Cuanto mayor sea el <xref:System.Windows.Controls.Panel.Children%2A> colección, mayor es el número de cálculos que se deben realizar. También se puede introducir complejidad según el comportamiento de diseño definido por el <xref:System.Windows.Controls.Panel> elemento al que pertenece la colección. Relativamente sencilla <xref:System.Windows.Controls.Panel>, tales como <xref:System.Windows.Controls.Canvas>, puede tener un rendimiento significativamente mejor que más complejo <xref:System.Windows.Controls.Panel>, tales como <xref:System.Windows.Controls.Grid>.  
  
 Cada vez que un elemento secundario <xref:System.Windows.UIElement> cambia de posición, tiene potencial para desencadenar un nuevo pase por el sistema de diseño. Por lo tanto, es importante comprender los eventos que pueden invocar el sistema de diseño, ya que una invocación innecesaria puede provocar un bajo rendimiento de la aplicación. A continuación, se describe el proceso que se produce cuando se invoca el sistema de diseño.  
  
1.  Un elemento secundario <xref:System.Windows.UIElement> empezar el proceso de diseño, se miden las propiedades del núcleo.  
  
2.  Ajustar el tamaño de las propiedades definidas en <xref:System.Windows.FrameworkElement> se evalúan, tales como <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, y <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  <xref:System.Windows.Controls.Panel>-se aplica la lógica específica, como <xref:System.Windows.Controls.Dock> dirección o apilamiento <xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  El contenido se organiza después de medir todos los elementos secundarios.  
  
5.  El <xref:System.Windows.Controls.Panel.Children%2A> colección se dibuja en la pantalla.  
  
6.  El proceso se vuelve a invocar si adicionales <xref:System.Windows.Controls.Panel.Children%2A> se agregan a la colección, un <xref:System.Windows.FrameworkElement.LayoutTransform%2A> se aplica, o el <xref:System.Windows.UIElement.UpdateLayout%2A> se llama al método.  
  
 Este proceso y cómo se invoca se definen con más detalle en las secciones siguientes.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Medición y organización de elementos secundarios  
 El sistema de diseño completa dos pases por cada miembro de la <xref:System.Windows.Controls.Panel.Children%2A> colección, un paso de medida y un paso de organización. Cada elemento secundario <xref:System.Windows.Controls.Panel> proporciona su propio <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos para lograr su propio comportamiento de diseño específico.  
  
 Durante el paso de medida, cada miembro de la <xref:System.Windows.Controls.Panel.Children%2A> se evalúa la colección. El proceso comienza con una llamada a la <xref:System.Windows.UIElement.Measure%2A> método. Este método se llama dentro de la implementación del elemento primario <xref:System.Windows.Controls.Panel> elemento y no es necesario llamarlo explícitamente para que el diseño que se produzca.  
  
 Propiedades de tamaño en primer lugar, nativo de la <xref:System.Windows.UIElement> se evalúan, tales como <xref:System.Windows.UIElement.Clip%2A> y <xref:System.Windows.UIElement.Visibility%2A>. Esto genera un valor denominado `constraintSize` que se pasa a <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 En segundo lugar, las propiedades de marco de trabajo definieron en <xref:System.Windows.FrameworkElement> se procesan, lo que afecta al valor de `constraintSize`. Estas propiedades suelen describir las características de ajuste de tamaño de subyacente <xref:System.Windows.UIElement>, como su <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, y <xref:System.Windows.FrameworkElement.Style%2A>. Cada una de estas propiedades puede cambiar el espacio necesario para mostrar el elemento. <xref:System.Windows.FrameworkElement.MeasureOverride%2A> a continuación, se llama con `constraintSize` como un parámetro.  
  
> [!NOTE]
>  Hay una diferencia entre las propiedades de <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A>. Por ejemplo, el <xref:System.Windows.FrameworkElement.ActualHeight%2A> propiedad es un valor calculado en función de otras entradas de altura y el sistema de diseño. El valor se establece mediante el propio sistema de diseño, basándose en un paso de representación real y es posible que, por tanto, quedarse ligeramente por detrás del valor del conjunto de propiedades, como <xref:System.Windows.FrameworkElement.Height%2A>, que son la base del cambio de entrada.  
>   
>  Dado que <xref:System.Windows.FrameworkElement.ActualHeight%2A> es un valor calculado, debe tener en cuenta que puede haber varios incremental notificados o cambian a él como resultado varias operaciones por el sistema de diseño. El sistema de diseño puede calcular el espacio de medida necesario para los elementos secundarios, las restricciones impuestas por el elemento primario y así sucesivamente.  
  
 El objetivo final del paso de medida es para que el elemento secundario determine su <xref:System.Windows.UIElement.DesiredSize%2A>, que se produce durante el <xref:System.Windows.FrameworkElement.MeasureCore%2A> llamar. El <xref:System.Windows.UIElement.DesiredSize%2A> almacena valor <xref:System.Windows.UIElement.Measure%2A> para su uso durante el paso de organización de contenido.  
  
 El paso de organización comienza con una llamada a la <xref:System.Windows.UIElement.Arrange%2A> método. Durante el paso de organización, el elemento primario <xref:System.Windows.Controls.Panel> elemento genera un rectángulo que representa los límites del elemento secundario. Este valor se pasa a la <xref:System.Windows.FrameworkElement.ArrangeCore%2A> método para su procesamiento.  
  
 El <xref:System.Windows.FrameworkElement.ArrangeCore%2A> método evalúa el <xref:System.Windows.UIElement.DesiredSize%2A> del elemento secundario y evalúa cualquier margen adicional que puede afectar al tamaño representado del elemento. <xref:System.Windows.FrameworkElement.ArrangeCore%2A> genera un `arrangeSize`, que se pasa a la <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> método de la <xref:System.Windows.Controls.Panel> como un parámetro. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> genera el `finalSize` del elemento secundario. Por último, el <xref:System.Windows.FrameworkElement.ArrangeCore%2A> método realiza una evaluación final de las propiedades de desplazamiento, como los márgenes y la alineación y coloca el elemento secundario dentro de su ranura de diseño. El elemento secundario no tiene que ocupar todo el espacio asignado y con frecuencia no lo hace. A continuación, se devuelve el control al elemento primario <xref:System.Windows.Controls.Panel> y se completa el proceso de diseño.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Elementos de panel y comportamientos de diseño personalizados  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un grupo de elementos que se derivan de <xref:System.Windows.Controls.Panel>. Estos <xref:System.Windows.Controls.Panel> elementos permiten numerosos diseños complejos. Por ejemplo, apilar elementos fácilmente se consigue mediante el uso de la <xref:System.Windows.Controls.StackPanel> elemento mientras diseños flujo más libres y complejos son posibles con un <xref:System.Windows.Controls.Canvas>.  
  
 La siguiente tabla resume el diseño disponible <xref:System.Windows.Controls.Panel> elementos.  
  
|Nombre del panel|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Define un área en la cual puede colocar explícitamente los elementos secundarios utilizando las coordenadas relativas a la <xref:System.Windows.Controls.Canvas> área.|  
|<xref:System.Windows.Controls.DockPanel>|Define un área en la que se pueden organizar elementos secundarios de forma horizontal o vertical, relacionados entre sí.|  
|<xref:System.Windows.Controls.Grid>|Define un área de cuadrícula flexible que consta de columnas y filas.|  
|<xref:System.Windows.Controls.StackPanel>|Organiza elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Proporciona un marco para <xref:System.Windows.Controls.Panel> elementos que virtualizan su recolección de datos secundarios. Esta es una clase abstracta.|  
|<xref:System.Windows.Controls.WrapPanel>|Coloca los elementos secundarios en posición secuencial de izquierda a derecha y traslada el contenido a la línea siguiente en el borde del cuadro contenedor. Ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, dependiendo del valor de la <xref:System.Windows.Controls.WrapPanel.Orientation%2A> propiedad.|  
  
 Para las aplicaciones que requieren un diseño que no es posible utilizando cualquiera de las predefinidas <xref:System.Windows.Controls.Panel> elementos, comportamientos de diseño personalizados pueden lograrse mediante la herencia de <xref:System.Windows.Controls.Panel> e invalidar la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos. Para obtener un ejemplo, consulte [Custom Radial Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159982) (Ejemplo de panel radial personalizado).  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Consideraciones del rendimiento del diseño  
 El diseño es un proceso recursivo. Cada elemento secundario de un <xref:System.Windows.Controls.Panel.Children%2A> colección se procesa durante cada invocación del sistema de diseño. Como resultado, se debería evitar desencadenar el sistema de diseño cuando no sea necesario. Las consideraciones siguientes pueden ayudarle a lograr un mejor rendimiento.  
  
-   Tenga en cuenta qué cambios de valor de propiedad forzarán una actualización recursiva por parte del sistema de diseño.  
  
     Las propiedades de dependencia cuyos valores pueden provocar la inicialización del sistema de diseño se marcan con marcas públicas. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> y <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> proporcionan pistas útiles en cuanto a la propiedad que cambia el valor de forzará una recursiva actualización el sistema de diseño. En general, cualquier propiedad que puede afectar al tamaño del rectángulo de selección de un elemento debe tener un <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> marca establecida en true. Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Cuando sea posible, use un <xref:System.Windows.UIElement.RenderTransform%2A> en lugar de un <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     Un <xref:System.Windows.FrameworkElement.LayoutTransform%2A> puede ser una forma muy útil para influir en el contenido de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Sin embargo, si no tiene el efecto de la transformación de afectar a la posición de otros elementos, es mejor usar un <xref:System.Windows.UIElement.RenderTransform%2A> en su lugar, porque <xref:System.Windows.UIElement.RenderTransform%2A> no invoca el sistema de diseño. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> se aplica su transformación y fuerza una actualización recursiva del diseño para tener en cuenta la nueva posición del elemento afectado.  
  
-   Evitar llamadas innecesarias al <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     El <xref:System.Windows.UIElement.UpdateLayout%2A> método fuerza una actualización recursiva del diseño y con frecuencia no es necesario. A menos que esté seguro de que se requiere una actualización completa, confíe en el sistema de diseño para que llame a este método.  
  
-   Cuando se trabaja con un gran <xref:System.Windows.Controls.Panel.Children%2A> colección, considere el uso de un <xref:System.Windows.Controls.VirtualizingStackPanel> en lugar de normal <xref:System.Windows.Controls.StackPanel>.  
  
     Al virtualizar la colección secundaria, la <xref:System.Windows.Controls.VirtualizingStackPanel> solo mantiene los objetos en memoria que están actualmente en la ventanilla del elemento primario. Como resultado, el rendimiento se mejora sustancialmente en la mayoría de escenarios.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Representación de subpíxeles y redondeo del diseño  
 El sistema de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa unidades independientes del dispositivo para habilitar la resolución y la independencia del dispositivo. Cada píxel independiente del dispositivo se escala automáticamente con el sistema [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] configuración. Esto proporciona a las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un escalado adecuado para diferentes configuraciones de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] y hace que la aplicación detecte el valor de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] automáticamente.  
  
 Sin embargo, esta independencia de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] puede crear representaciones de bordes irregulares debido al suavizado de contorno. Estos artefactos, que suelen aparecer como bordes borrosos o semitransparentes, pueden mostrarse cuando un borde se encuentra en medio de un píxel de dispositivo, en lugar de entre píxeles de dispositivo. El sistema de diseño proporciona una manera de ajustarlo con el redondeo del diseño. El redondeo del diseño se produce cuando el sistema de diseño redondea los valores de píxel no enteros durante el cálculo de diseño.  
  
 De forma predeterminada, el redondeo de diseño está deshabilitado. Para habilitar el redondeo del diseño, establezca la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> propiedad `true` en cualquier <xref:System.Windows.FrameworkElement>. Dado que es una propiedad de dependencia, el valor se propagará a todos los elementos secundarios del árbol visual. Para habilitar el redondeo del diseño para toda la interfaz de usuario, establezca <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> a `true` en el contenedor raíz. Para obtener un ejemplo, consulta <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Pasos adicionales  
 Comprender cómo se miden y organizan los elementos es el primer paso para entender el diseño. Para obtener más información acerca de la disponible <xref:System.Windows.Controls.Panel> elementos, vea [información general sobre](../../../../docs/framework/wpf/controls/panels-overview.md). Para entender mejor las diversas propiedades de posición que pueden afectar al diseño, consulte [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md). Para obtener un ejemplo de un personalizado <xref:System.Windows.Controls.Panel> elemento, vea [ejemplo de Panel Radial personalizado](https://go.microsoft.com/fwlink/?LinkID=159982). Cuando esté listo para poner todo junto en una aplicación ligera, consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.UIElement>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
