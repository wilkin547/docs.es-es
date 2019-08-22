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
ms.openlocfilehash: 648adb34664ccb2a475e32aba4d0d76d99cf49d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666763"
---
# <a name="layout"></a>Diseño
En este tema se describe el sistema de diseño de Windows Presentation Foundation (WPF). Comprender cómo y cuándo se producen los cálculos de diseño es esencial para crear interfaces de usuario en WPF.  
  
 Este tema contiene las siguientes secciones:  
  
- [Rectángulos de selección de elementos](#LayoutSystem_BoundingBox)  
  
- [El sistema de diseño](#LayoutSystem_Overview)  
  
- [Medición y organización de elementos secundarios](#LayoutSystem_Measure_Arrange)  
  
- [Elementos de panel y comportamientos de diseño personalizados](#LayoutSystem_PanelsCustom)  
  
- [Consideraciones del rendimiento del diseño](#LayoutSystem_Performance)  
  
- [Representación de subpíxeles y redondeo del diseño](#LayoutSystem_LayoutRounding)  
  
- [Pasos adicionales](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Rectángulos de selección de elementos  
 Al pensar en el diseño en WPF, es importante comprender el rectángulo de selección que rodea todos los elementos. Cada <xref:System.Windows.FrameworkElement> consumido por el sistema de diseño puede considerarse como un rectángulo que se ranura en el diseño. La <xref:System.Windows.Controls.Primitives.LayoutInformation> clase devuelve los límites de la asignación de diseño de un elemento o de la ranura. El tamaño del rectángulo se determina calculando el espacio de la pantalla disponible, el tamaño de las restricciones, las propiedades específicas del diseño (como el margen y el relleno) y el comportamiento individual del elemento primario <xref:System.Windows.Controls.Panel> . Al procesar estos datos, el sistema de diseño puede calcular la posición de todos los elementos secundarios de un <xref:System.Windows.Controls.Panel>determinado. Es importante recordar que las características de ajuste de tamaño definidas en el elemento primario, <xref:System.Windows.Controls.Border>como, afectan a sus elementos secundarios.  
  
 En la siguiente ilustración se muestra un diseño sencillo.  
  
 ![Captura de pantalla que muestra una cuadrícula típica, sin rectángulo de selección superpuesto.](./media/layout/grid-no-bounding-box-superimpose.png)  
  
 Este diseño se puede lograr con el siguiente código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[LayoutInformation#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Un solo <xref:System.Windows.Controls.TextBlock> elemento se hospeda <xref:System.Windows.Controls.Grid>dentro de. Mientras que el texto solo rellena la esquina superior izquierda de la primera columna, el espacio asignado para el <xref:System.Windows.Controls.TextBlock> es realmente mucho mayor. El rectángulo de selección de cualquiera <xref:System.Windows.FrameworkElement> se puede recuperar mediante el <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> método. En la ilustración siguiente se muestra el cuadro de <xref:System.Windows.Controls.TextBlock> límite del elemento.  
  
 ![Captura de pantalla que muestra que el rectángulo de selección de TextBlock ahora está visible.](./media/layout/visible-textblock-bounding-box.png)  
  
 Como se muestra en el rectángulo amarillo, el espacio asignado para <xref:System.Windows.Controls.TextBlock> el elemento es realmente mucho mayor de lo que aparece. A medida que se agregan elementos <xref:System.Windows.Controls.Grid>adicionales a, esta asignación puede reducirse o expandirse, en función del tipo y el tamaño de los elementos que se agregan.  
  
 La ranura de diseño de <xref:System.Windows.Controls.TextBlock> se convierte en un <xref:System.Windows.Shapes.Path> mediante el <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> método. Esta técnica puede ser útil para mostrar el rectángulo de selección de un elemento.  
  
 [!code-csharp[LayoutInformation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>El sistema de diseño  
 En su forma más simple, el diseño es un sistema recursivo que permite dibujar y situar un elemento, así como cambiar su tamaño. Más concretamente, el diseño describe el proceso de medición y organización de los miembros <xref:System.Windows.Controls.Panel> de la <xref:System.Windows.Controls.Panel.Children%2A> colección de un elemento. El diseño es un proceso intensivo. Cuanto mayor sea <xref:System.Windows.Controls.Panel.Children%2A> la colección, mayor será el número de cálculos que se deben realizar. También se puede introducir la complejidad en función del comportamiento de diseño definido <xref:System.Windows.Controls.Panel> por el elemento que posee la colección. Una forma relativamente <xref:System.Windows.Controls.Panel>sencilla, <xref:System.Windows.Controls.Canvas>como, puede tener un rendimiento significativamente mejor que una <xref:System.Windows.Controls.Grid>más <xref:System.Windows.Controls.Panel>compleja, como.  
  
 Cada vez que un elemento <xref:System.Windows.UIElement> secundario cambia su posición, tiene la posibilidad de desencadenar un nuevo paso por el sistema de diseño. Por lo tanto, es importante comprender los eventos que pueden invocar el sistema de diseño, ya que una invocación innecesaria puede provocar un bajo rendimiento de la aplicación. A continuación, se describe el proceso que se produce cuando se invoca el sistema de diseño.  
  
1. Un elemento <xref:System.Windows.UIElement> secundario comienza el proceso de diseño mediante el cual se miden primero sus propiedades básicas.  
  
2. Se evalúan las <xref:System.Windows.FrameworkElement> propiedades de ajuste de tamaño <xref:System.Windows.FrameworkElement.Width%2A>definidas <xref:System.Windows.FrameworkElement.Height%2A>en, <xref:System.Windows.FrameworkElement.Margin%2A>como, y.  
  
3. <xref:System.Windows.Controls.Panel>se aplica la lógica específica de, como <xref:System.Windows.Controls.Dock> la dirección o el <xref:System.Windows.Controls.StackPanel.Orientation%2A>apilamiento.  
  
4. El contenido se organiza después de medir todos los elementos secundarios.  
  
5. La <xref:System.Windows.Controls.Panel.Children%2A> colección se dibuja en la pantalla.  
  
6. El proceso se invoca de nuevo si se <xref:System.Windows.Controls.Panel.Children%2A> agregan más a la colección, <xref:System.Windows.FrameworkElement.LayoutTransform%2A> se aplica un o se <xref:System.Windows.UIElement.UpdateLayout%2A> llama al método.  
  
 Este proceso y cómo se invoca se definen con más detalle en las secciones siguientes.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Medición y organización de elementos secundarios  
 El sistema de diseño completa dos pasos para cada miembro de la <xref:System.Windows.Controls.Panel.Children%2A> colección, un paso de medida y un paso de organización. Cada elemento <xref:System.Windows.Controls.Panel> secundario proporciona sus <xref:System.Windows.FrameworkElement.MeasureOverride%2A> propios <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos y para lograr su propio comportamiento de diseño específico.  
  
 Durante el paso de medida, se evalúa cada <xref:System.Windows.Controls.Panel.Children%2A> miembro de la colección. El proceso comienza con una llamada al <xref:System.Windows.UIElement.Measure%2A> método. Se llama a este método dentro de la implementación del <xref:System.Windows.Controls.Panel> elemento primario y no es necesario llamarlo explícitamente para que se produzca el diseño.  
  
 <xref:System.Windows.UIElement.Visibility%2A>En <xref:System.Windows.UIElement> primerlugar,seevalúanlaspropiedadesdetamañonativode,comoy.<xref:System.Windows.UIElement.Clip%2A> Esto genera un valor denominado `constraintSize` que se pasa a <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 En segundo lugar, se procesan <xref:System.Windows.FrameworkElement> las propiedades de marco de trabajo definidas en `constraintSize`, lo que afecta al valor de. Normalmente, estas propiedades describen las características de ajuste de <xref:System.Windows.UIElement>tamaño del subyacente, <xref:System.Windows.FrameworkElement.Height%2A>como <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, y <xref:System.Windows.FrameworkElement.Style%2A>. Cada una de estas propiedades puede cambiar el espacio necesario para mostrar el elemento. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>a continuación, se `constraintSize` llama a con como parámetro.  
  
> [!NOTE]
>  Existe una diferencia entre las <xref:System.Windows.FrameworkElement.Height%2A> propiedades de <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.ActualWidth%2A>y y. Por ejemplo, la <xref:System.Windows.FrameworkElement.ActualHeight%2A> propiedad es un valor calculado basado en otras entradas de alto y en el sistema de diseño. El propio sistema de diseño establece el valor en función de un paso de representación real y, por tanto, se puede retrasar ligeramente detrás del valor establecido de <xref:System.Windows.FrameworkElement.Height%2A>las propiedades, como, que son la base del cambio de entrada.  
>   
>  Dado <xref:System.Windows.FrameworkElement.ActualHeight%2A> que es un valor calculado, debe tener en cuenta que puede haber varios cambios o informes incrementales en él como resultado de varias operaciones realizadas por el sistema de diseño. El sistema de diseño puede calcular el espacio de medida necesario para los elementos secundarios, las restricciones impuestas por el elemento primario y así sucesivamente.  
  
 El objetivo final del paso de medida es que el elemento secundario determine <xref:System.Windows.UIElement.DesiredSize%2A>su, que se produce <xref:System.Windows.FrameworkElement.MeasureCore%2A> durante la llamada. El <xref:System.Windows.UIElement.DesiredSize%2A> valor se almacena mediante <xref:System.Windows.UIElement.Measure%2A> para su uso durante el paso de organización del contenido.  
  
 El paso de organización comienza con una llamada al <xref:System.Windows.UIElement.Arrange%2A> método. Durante el paso de organización, el <xref:System.Windows.Controls.Panel> elemento primario genera un rectángulo que representa los límites del elemento secundario. Este valor se pasa al método <xref:System.Windows.FrameworkElement.ArrangeCore%2A> para el procesamiento.  
  
 El <xref:System.Windows.FrameworkElement.ArrangeCore%2A> método evalúa el <xref:System.Windows.UIElement.DesiredSize%2A> del elemento secundario y evalúa cualquier margen adicional que pueda afectar al tamaño representado del elemento. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>genera un `arrangeSize`, que se pasa <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> al método de <xref:System.Windows.Controls.Panel> como un parámetro. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>genera el `finalSize` del elemento secundario. Por último, <xref:System.Windows.FrameworkElement.ArrangeCore%2A> el método realiza una evaluación final de las propiedades de desplazamiento, como margin y Alignment, y coloca el elemento secundario dentro de su espacio de diseño. El elemento secundario no tiene que ocupar todo el espacio asignado y con frecuencia no lo hace. A continuación, el control se devuelve <xref:System.Windows.Controls.Panel> al elemento primario y se completa el proceso de diseño.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Elementos de panel y comportamientos de diseño personalizados  
WPF incluye un grupo de elementos que derivan <xref:System.Windows.Controls.Panel>de. Estos <xref:System.Windows.Controls.Panel> elementos permiten numerosos diseños complejos. Por ejemplo, los elementos de apilamiento se pueden lograr fácilmente mediante el <xref:System.Windows.Controls.StackPanel> elemento, mientras que los diseños de flujo más complejos y libres son posibles mediante <xref:System.Windows.Controls.Canvas>el uso de.  
  
 En la tabla siguiente se resumen los elementos <xref:System.Windows.Controls.Panel> de diseño disponibles.  
  
|Nombre del panel|DESCRIPCIÓN|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Define un área en la que puede colocar explícitamente los elementos secundarios por coordenadas relativas <xref:System.Windows.Controls.Canvas> al área.|  
|<xref:System.Windows.Controls.DockPanel>|Define un área en la que se pueden organizar elementos secundarios de forma horizontal o vertical, relacionados entre sí.|  
|<xref:System.Windows.Controls.Grid>|Define un área de cuadrícula flexible que consta de columnas y filas.|  
|<xref:System.Windows.Controls.StackPanel>|Organiza elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Proporciona un marco de <xref:System.Windows.Controls.Panel> trabajo para los elementos que virtualizan su colección de datos secundaria. Esta es una clase abstracta.|  
|<xref:System.Windows.Controls.WrapPanel>|Coloca los elementos secundarios en posición secuencial de izquierda a derecha y traslada el contenido a la línea siguiente en el borde del cuadro contenedor. La ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, en función del valor de <xref:System.Windows.Controls.WrapPanel.Orientation%2A> la propiedad.|  
  
 En el caso de las aplicaciones que requieren un diseño que no sea posible mediante el uso <xref:System.Windows.Controls.Panel> de cualquiera de los elementos predefinidos, se pueden lograr <xref:System.Windows.Controls.Panel> los comportamientos de diseño personalizados <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> heredando de e invalidando los <xref:System.Windows.FrameworkElement.MeasureOverride%2A> métodos y.  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Consideraciones del rendimiento del diseño  
 El diseño es un proceso recursivo. Cada elemento secundario de una <xref:System.Windows.Controls.Panel.Children%2A> colección se procesa durante cada invocación del sistema de diseño. Como resultado, se debería evitar desencadenar el sistema de diseño cuando no sea necesario. Las consideraciones siguientes pueden ayudarle a lograr un mejor rendimiento.  
  
- Tenga en cuenta qué cambios de valor de propiedad forzarán una actualización recursiva por parte del sistema de diseño.  
  
     Las propiedades de dependencia cuyos valores pueden provocar la inicialización del sistema de diseño se marcan con marcas públicas. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>y <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> proporcionan pistas útiles en cuanto a qué cambios de valor de propiedad forzarán una actualización recursiva por parte del sistema de diseño. En general, cualquier propiedad que pueda afectar al tamaño del cuadro de límite de un elemento debe tener una <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> marca establecida en true. Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
- Cuando sea posible, utilice <xref:System.Windows.UIElement.RenderTransform%2A> en lugar <xref:System.Windows.FrameworkElement.LayoutTransform%2A>de.  
  
     Puede ser una forma muy útil de afectar al contenido [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]de. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Sin embargo, si el efecto de la transformación no tiene que afectar a la posición de otros elementos, es mejor usar <xref:System.Windows.UIElement.RenderTransform%2A> en su lugar, porque <xref:System.Windows.UIElement.RenderTransform%2A> no invoca el sistema de diseño. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>aplica su transformación y fuerza una actualización de diseño recursiva para que tenga en cuenta la nueva posición del elemento afectado.  
  
- Evite las llamadas innecesarias a <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     El <xref:System.Windows.UIElement.UpdateLayout%2A> método fuerza una actualización recursiva del diseño y no suele ser necesario. A menos que esté seguro de que se requiere una actualización completa, confíe en el sistema de diseño para que llame a este método.  
  
- Al trabajar con una colección <xref:System.Windows.Controls.Panel.Children%2A> grande, considere la <xref:System.Windows.Controls.VirtualizingStackPanel> posibilidad de usar en lugar de <xref:System.Windows.Controls.StackPanel>un normal.  
  
     Al virtualizar la colección secundaria, el <xref:System.Windows.Controls.VirtualizingStackPanel> solo conserva los objetos de la memoria que están actualmente dentro de la ventanilla del elemento primario. Como resultado, el rendimiento se mejora sustancialmente en la mayoría de escenarios.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Representación de subpíxeles y redondeo del diseño  
 El sistema de gráficos de WPF usa unidades independientes del dispositivo para habilitar la resolución y la independencia del dispositivo. Cada píxel independiente del dispositivo se escala automáticamente con la configuración de puntos por pulgada (PPP) del sistema. Esto proporciona a las aplicaciones de WPF un ajuste de escala adecuado para diferentes configuraciones de PPP y hace que la aplicación sea compatible automáticamente con el reconocimiento de PPP.  
  
 Sin embargo, esta independencia de PPP puede crear una representación irregular del borde debido al suavizado de contorno. Estos artefactos, que suelen aparecer como bordes borrosos o semitransparentes, pueden mostrarse cuando un borde se encuentra en medio de un píxel de dispositivo, en lugar de entre píxeles de dispositivo. El sistema de diseño proporciona una manera de ajustarlo con el redondeo del diseño. El redondeo del diseño se produce cuando el sistema de diseño redondea los valores de píxel no enteros durante el cálculo de diseño.  
  
 De forma predeterminada, el redondeo de diseño está deshabilitado. Para habilitar el redondeo del diseño, establezca <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> la `true` propiedad en en <xref:System.Windows.FrameworkElement>any. Dado que es una propiedad de dependencia, el valor se propagará a todos los elementos secundarios del árbol visual. Para habilitar el redondeo del diseño para toda la interfaz de <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> usuario `true` , establezca en en el contenedor raíz. Para obtener un ejemplo, consulte <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Pasos adicionales  
 Comprender cómo se miden y organizan los elementos es el primer paso para entender el diseño. Para obtener más información sobre los <xref:System.Windows.Controls.Panel> elementos disponibles, consulte [información general](../controls/panels-overview.md)de los paneles. Para entender mejor las diversas propiedades de posición que pueden afectar al diseño, consulte [Información general sobre alineación, márgenes y relleno](alignment-margins-and-padding-overview.md). Cuando esté listo para colocarlo todos juntos en una aplicación ligera, consulte [Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md)de escritorio WPF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.UIElement>
- [Información general sobre elementos Panel](../controls/panels-overview.md)
- [Información general sobre alineación, márgenes y relleno](alignment-margins-and-padding-overview.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
