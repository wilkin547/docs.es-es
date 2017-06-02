---
title: "Dise&#241;o | Microsoft Docs"
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
  - "controles [WPF], sistema de diseño"
  - "sistema de diseño [WPF]"
  - "sistema de diseño WPF"
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Dise&#241;o
En este tema se describe el sistema de diseño de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Es esencial entender cómo y cuándo se realizan los cálculos de diseño para crear interfaces de usuario en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
-   [Cuadros de límite de elementos](#LayoutSystem_BoundingBox)  
  
-   [Sistema de diseño](#LayoutSystem_Overview)  
  
-   [Medir y organizar elementos secundarios](#LayoutSystem_Measure_Arrange)  
  
-   [Elementos de panel y comportamientos de diseño personalizado](#LayoutSystem_PanelsCustom)  
  
-   [Consideraciones sobre el rendimiento del diseño](#LayoutSystem_Performance)  
  
-   [Representación de subpíxeles y redondeo del diseño](#LayoutSystem_LayoutRounding)  
  
-   [Pasos adicionales](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## Cuadros de límite de elementos  
 Al pensar en el diseño en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es importante entender el cuadro de límite que rodea todos los elementos.  Cada <xref:System.Windows.FrameworkElement> usado por el sistema de diseño se puede considerar como un rectángulo que se inserta en el diseño.  La clase <xref:System.Windows.Controls.Primitives.LayoutInformation> devuelve los límites de la asignación del diseño de un elemento o ranura.  El tamaño del rectángulo se determina calculando el espacio de pantalla disponible, el tamaño de cualquier restricción, las propiedades específicas del diseño \(como el margen y el relleno\) y el comportamiento individual del elemento <xref:System.Windows.Controls.Panel> primario.  Al procesar estos datos, el sistema de diseño puede calcular la posición de todos los elementos secundarios de un <xref:System.Windows.Controls.Panel> determinado.  Es importante recordar que las características de tamaño definidas en el elemento primario, como un <xref:System.Windows.Controls.Border>, afectan a sus elementos secundarios.  
  
 En la ilustración siguiente se muestra un diseño sencillo.  
  
 ![Cuadrícula típica sin rectángulo de selección superpuesto.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Este diseño se puede lograr usando el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siguiente.  
  
 [!code-xml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Un único elemento <xref:System.Windows.Controls.TextBlock> se hospeda dentro de un <xref:System.Windows.Controls.Grid>.  Aunque el texto rellena solo la esquina superior izquierda de la primera columna, el espacio asignado para <xref:System.Windows.Controls.TextBlock> es mucho mayor realmente.  El cuadro de límite de cualquier objeto <xref:System.Windows.FrameworkElement> se puede recuperar usando el método <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>.  En la ilustración siguiente se muestra el cuadro de límite para el elemento <xref:System.Windows.Controls.TextBlock>.  
  
 ![El rectángulo de selección de TextBlock está visible ahora.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Como muestra el rectángulo amarillo, el espacio asignado para el elemento <xref:System.Windows.Controls.TextBlock> es realmente mucho mayor de lo que parece.  Al agregar elementos adicionales a <xref:System.Windows.Controls.Grid>, esta asignación se puede reducir o expandir, dependiendo del tipo y el tamaño de los elementos que se agregan.  
  
 La ranura de diseño de <xref:System.Windows.Controls.TextBlock> se traduce en <xref:System.Windows.Shapes.Path> usando el método <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>.  Esta técnica puede ser útil para mostrar el cuadro de límite de un elemento.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## Sistema de diseño  
 En su versión más simple, el diseño es un sistema recursivo que conduce a la configuración del tamaño, posición y presentación de un elemento.  Más específicamente, el diseño describe el proceso de medir y organizar los miembros de una colección <xref:System.Windows.Controls.Panel.Children%2A> de un elemento <xref:System.Windows.Controls.Panel>.  El diseño es un proceso intensivo.  Cuanto mayor sea la colección <xref:System.Windows.Controls.Panel.Children%2A>, mayor será el número de cálculos que se deben realizar.  También se puede incluir mayor complejidad según el comportamiento de diseño definido por el elemento <xref:System.Windows.Controls.Panel> que posee la colección.  Un <xref:System.Windows.Controls.Panel> relativamente sencillo, como <xref:System.Windows.Controls.Canvas>, puede tener un rendimiento mucho mejor que un <xref:System.Windows.Controls.Panel> más complejo, como <xref:System.Windows.Controls.Grid>.  
  
 Cada vez que un <xref:System.Windows.UIElement> secundario cambia su posición, tiene el potencial de desencadenar un nuevo paso del sistema de diseño.  Por tanto, es importante entender los eventos que pueden invocar el sistema de diseño, ya que una invocación innecesaria puede deteriorar el rendimiento de la aplicación.  A continuación se describe el proceso que tiene lugar cuando se invoca el sistema de diseño.  
  
1.  Un <xref:System.Windows.UIElement> secundario comienza el proceso de diseño midiendo en primer lugar sus propiedades básicas.  
  
2.  Se evalúan las propiedades de tamaño definidas en <xref:System.Windows.FrameworkElement>, como <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  Se aplica la lógica concreta de <xref:System.Windows.Controls.Panel>, como la dirección de <xref:System.Windows.Controls.Dock> o la <xref:System.Windows.Controls.StackPanel.Orientation%2A> de apilado.  
  
4.  El contenido se organiza después de medir todos los elementos secundarios.  
  
5.  Se dibuja la colección <xref:System.Windows.Controls.Panel.Children%2A> en la pantalla.  
  
6.  Se invoca el proceso de nuevo si se agregan <xref:System.Windows.Controls.Panel.Children%2A> adicionales a la colección, se aplica una <xref:System.Windows.FrameworkElement.LayoutTransform%2A> o se llama al método <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
 Este proceso y cómo se invoca se definen con más detalle en las próximas secciones.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## Medir y organizar elementos secundarios  
 El sistema de diseño completa dos pasos por cada miembro de la colección <xref:System.Windows.Controls.Panel.Children%2A>: un paso de medida y un paso de organización.  Cada <xref:System.Windows.Controls.Panel> secundario proporciona sus propios métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> para lograr su propio comportamiento de diseño concreto.  
  
 Durante el paso de medida, se evalúa cada miembro de la colección <xref:System.Windows.Controls.Panel.Children%2A>.  El proceso comienza con una llamada al método <xref:System.Windows.UIElement.Measure%2A>.  Se llama a este método dentro de la implementación del elemento <xref:System.Windows.Controls.Panel> primario y no es preciso llamarla explícitamente para que el diseño tenga lugar.  
  
 En primer lugar, se evalúan las propiedades de tamaño nativas de <xref:System.Windows.UIElement>, como <xref:System.Windows.UIElement.Clip%2A> y <xref:System.Windows.UIElement.Visibility%2A>.  Esto genera un valor denominado `constraintSize` que se pasa a <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 En segundo lugar, se procesan las propiedades de marco definidas en <xref:System.Windows.FrameworkElement>, lo que afecta al valor de `constraintSize`.  Estas propiedades suelen describir las características de tamaño del <xref:System.Windows.UIElement> subyacente, como <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> y <xref:System.Windows.FrameworkElement.Style%2A>.  Cada una de estas propiedades puede modificar el espacio necesario para mostrar el elemento.  A continuación se llama a <xref:System.Windows.FrameworkElement.MeasureOverride%2A> con `constraintSize` como parámetro.  
  
> [!NOTE]
>  Existe una diferencia entre las propiedades de <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A>, y <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A>.  Por ejemplo, la propiedad <xref:System.Windows.FrameworkElement.ActualHeight%2A> es un valor calculado que se basa en otras entradas de alto y en el sistema de diseño.  El propio sistema de diseño establece el valor, basándose en un paso de representación real; por tanto, puede existir un pequeño desfase con respecto al valor establecido de propiedades como <xref:System.Windows.FrameworkElement.Height%2A>, que constituyen la base del cambio de entrada.  
>   
>  Puesto que <xref:System.Windows.FrameworkElement.ActualHeight%2A> es un valor calculado, debe tener en cuenta que puede haber cambios notificados múltiples o incrementales del mismo como resultado de las diversas operaciones realizadas por el sistema de diseño.  El sistema de diseño puede calcular el espacio de medidas necesario para los elementos secundarios, las restricciones impuestas por el elemento principal, etc.  
  
 El objetivo final del paso de medida es que el elemento secundario determine su <xref:System.Windows.UIElement.DesiredSize%2A>, lo que sucede durante la llamada a <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  <xref:System.Windows.UIElement.Measure%2A> almacena el valor <xref:System.Windows.UIElement.DesiredSize%2A> para usarlo durante el paso de organización del contenido.  
  
 El paso de organización se inicia con una llamada al método <xref:System.Windows.UIElement.Arrange%2A>.  Durante el paso de organización, el elemento <xref:System.Windows.Controls.Panel> primario genera un rectángulo que representa los límites del elemento secundario.  Este valor se pasa al método <xref:System.Windows.FrameworkElement.ArrangeCore%2A> para procesarlo.  
  
 El método <xref:System.Windows.FrameworkElement.ArrangeCore%2A> evalúa el <xref:System.Windows.UIElement.DesiredSize%2A> del elemento secundario y evalúa cualquier margen adicional que pueda afectar al tamaño representado del elemento.  <xref:System.Windows.FrameworkElement.ArrangeCore%2A> genera un parámetro `arrangeSize`, que se pasa al método <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> de <xref:System.Windows.Controls.Panel> como un parámetro.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> genera el `finalSize` del elemento secundario.  Por último, el método <xref:System.Windows.FrameworkElement.ArrangeCore%2A> realiza una última evaluación de las propiedades de desplazamiento, como los márgenes y la alineación, y coloca el elemento secundario dentro de su ranura de diseño.  El elemento secundario no tiene que rellenar todo el espacio asignado, y con frecuencia no lo hace.  A continuación, el control se devuelve al <xref:System.Windows.Controls.Panel> primario y el proceso de diseño se completa.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## Elementos de panel y comportamientos de diseño personalizado  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye un grupo de elementos que derivan de <xref:System.Windows.Controls.Panel>.  Estos elementos<xref:System.Windows.Controls.Panel> hacen posibles muchos diseños complejos.  Por ejemplo, se consigue fácilmente apilar elementos usando el elemento <xref:System.Windows.Controls.StackPanel>, mientras que otros diseños dinámicos más libres y complejos son posibles gracias a <xref:System.Windows.Controls.Canvas>.  
  
 En la tabla siguiente se resumen los elementos <xref:System.Windows.Controls.Panel> de diseño disponibles.  
  
|Nombre del panel|Descripción|  
|----------------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Define un área en la que pueden colocarse explícitamente los elementos secundarios utilizando las coordenadas relativas al área del control <xref:System.Windows.Controls.Canvas>.|  
|<xref:System.Windows.Controls.DockPanel>|Define un área en la que se pueden organizar horizontal o verticalmente los elementos secundarios, uno respecto al otro.|  
|<xref:System.Windows.Controls.Grid>|Define un área de cuadrícula flexible que está compuesta de columnas y filas.|  
|<xref:System.Windows.Controls.StackPanel>|Organiza los elementos secundarios en una única línea que se puede orientar horizontal o verticalmente.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Proporciona un marco para elementos <xref:System.Windows.Controls.Panel> que virtualizan su recolección de datos secundarios.  Ésta es una clase abstracta.|  
|<xref:System.Windows.Controls.WrapPanel>|Organiza los elementos secundarios secuencialmente de izquierda a derecha y traslada el contenido a la línea siguiente cuando alcanza el borde del cuadro contenedor.  La ordenación siguiente se realiza secuencialmente de arriba abajo o de izquierda a derecha, dependiendo del valor de la propiedad <xref:System.Windows.Controls.WrapPanel.Orientation%2A>.|  
  
 En el caso de las aplicaciones que necesitan un diseño que no es posible lograr usando cualquiera de los elementos <xref:System.Windows.Controls.Panel> predefinidos, se pueden conseguir comportamientos de diseño personalizados heredando de <xref:System.Windows.Controls.Panel> e invalidando los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  Para obtener un ejemplo, vea [Ejemplo Custom Radial Panel](http://go.microsoft.com/fwlink/?LinkID=159982).  
  
<a name="LayoutSystem_Performance"></a>   
## Consideraciones sobre el rendimiento del diseño  
 El diseño es un proceso recursivo.  Cada elemento secundario de una colección <xref:System.Windows.Controls.Panel.Children%2A> se procesa durante cada invocación del sistema de diseño.  Por tanto, debe evitarse activar el sistema de diseño cuando no es necesario.  Las consideraciones siguientes pueden ayudarle a lograr un rendimiento mejor.  
  
-   Sea consciente de que los cambios del valor de propiedad forzarán una actualización recursiva por parte del sistema de diseño.  
  
     Las propiedades de dependencia cuyos valores pueden producir la inicialización del sistema de diseño se marcan con marcas públicas.  <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> y <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> proporcionan pistas útiles acerca de qué cambios del valor de propiedad forzarán una actualización recursiva por parte del sistema de diseño.  En general, cualquier propiedad que puede afectar al tamaño del cuadro de límite de un elemento debe establecer la marca <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> en true.  Para obtener más información, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Siempre que sea posible, use una propiedad <xref:System.Windows.UIElement.RenderTransform%2A> en lugar de <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     <xref:System.Windows.FrameworkElement.LayoutTransform%2A> puede ser una manera muy útil de afectar al contenido de una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Sin embargo, si el efecto de la transformación no tiene que afectar a la posición de otros elementos, es mejor emplear una propiedad <xref:System.Windows.UIElement.RenderTransform%2A> en su lugar, porque<xref:System.Windows.UIElement.RenderTransform%2A> no invoca el sistema de diseño.  <xref:System.Windows.FrameworkElement.LayoutTransform%2A> aplica su transformación y fuerza una actualización recursiva del diseño para tener en cuenta la nueva posición del elemento afectado.  
  
-   Evite las llamadas innecesarias a <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     El método <xref:System.Windows.UIElement.UpdateLayout%2A> fuerza una actualización recursiva del diseño y no suele ser necesario.  A menos que esté seguro de que se necesita una actualización completa, deje que el sistema de diseño llame a este método en su lugar.  
  
-   Cuando se trabaja con una colección <xref:System.Windows.Controls.Panel.Children%2A> grande, puede ser conveniente usar un <xref:System.Windows.Controls.VirtualizingStackPanel> en lugar de un <xref:System.Windows.Controls.StackPanel> normal.  
  
     Al virtualizar la colección secundaria, <xref:System.Windows.Controls.VirtualizingStackPanel> únicamente conserva en la memoria los objetos que se encuentran actualmente dentro de la [ventanilla](GTMT) del elemento primario.  Como resultado, el rendimiento se mejora sustancialmente en la mayoría de los escenarios.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## Representación de subpíxeles y redondeo del diseño  
 El sistema de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza unidades independientes del dispositivo para que sean independientes de la resolución y del dispositivo.  Cada píxel independiente del dispositivo ajusta su escala automáticamente al valor de [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] del sistema.  De esta forma, se proporciona a las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un ajuste de escala correcto para las distintas configuraciones de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] y hace que la aplicación distinga este valor de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] automáticamente.  
  
 Sin embargo, esta independencia de [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] puede crear representaciones de bordes irregulares debido al suavizado de contorno.  Estas anomalías de la imagen, que suelen aparecer como bordes borrosos o semitransparentes, pueden producirse cuando un borde se encuentra en medio de un píxel de dispositivo en vez de situarse entre píxeles de dispositivo.  El sistema de diseño ofrece una manera de ajustarlo con el redondeo del diseño.  El redondeo del diseño es donde el sistema de diseño redondea cualquier valor de píxel no entero durante el paso de diseño.  
  
 El redondeo del diseño está deshabilitado de forma predeterminada.  Para habilitar el redondeo del diseño, establezca la propiedad <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> en `true` en cualquier <xref:System.Windows.FrameworkElement>.  Como se trata de una propiedad de dependencia, el valor se propagará a todos los elementos secundarios del árbol visual.  Para habilitar el redondeo del diseño para toda la interfaz de usuario, establezca <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> en `true` en el contenedor raíz.  Para obtener un ejemplo, vea <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## Pasos adicionales  
 Entender cómo se miden y organizan los elementos es el primer paso para entender el diseño.  Para obtener más información sobre los elementos <xref:System.Windows.Controls.Panel> disponibles, vea [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  Para entender mejor las diversas propiedades de posición que pueden afectar al diseño, consulte [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  Para obtener un ejemplo de un elemento <xref:System.Windows.Controls.Panel> personalizado, vea [Ejemplo Custom Radial Panel](http://go.microsoft.com/fwlink/?LinkID=159982).  Cuando esté preparado para aplicar todos estos conocimientos a la creación de una aplicación ligera, vea [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Vea también  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.UIElement>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Información general sobre alineación, márgenes y relleno](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)