---
title: "Informaci&#243;n general sobre la representaci&#243;n de gr&#225;ficos en WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "gráficos, representación"
  - "representar gráficos"
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: 51
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 48
---
# Informaci&#243;n general sobre la representaci&#243;n de gr&#225;ficos en WPF
En este tema se proporciona información general sobre la capa visual de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Se centra en el rol de la clase <xref:System.Windows.Media.Visual> para admitir la representación del modelo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="role_of_visual_object"></a>   
## Rol de los objetos visuales  
 La clase <xref:System.Windows.Media.Visual> es la abstracción básica de la que se derivan todos los objetos <xref:System.Windows.FrameworkElement>.  También actúa como punto de entrada para escribir nuevos controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], y en muchos sentidos se puede considerar como el identificador de ventana \(HWND\) del modelo de aplicaciones de Win32.  
  
 El objeto <xref:System.Windows.Media.Visual> es un objeto básico de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], cuyo rol principal es proporcionar la compatibilidad con la representación.  Los controles de interfaz de usuario, tales como <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.TextBox>, se derivan de la clase <xref:System.Windows.Media.Visual> y la utilizan para conservar sus datos de representación.  El objeto <xref:System.Windows.Media.Visual> proporciona compatibilidad con:  
  
-   Presentación de salida: representación del contenido conservado y serializado de un elemento visual.  
  
-   Transformaciones: ejecución de las transformaciones de un elemento visual.  
  
-   Recorte: compatibilidad con la zona de recorte para un elemento visual.  
  
-   Pruebas de posicionamiento: determinación de si una coordenada o geometría está contenida dentro de los límites de un elemento visual.  
  
-   Cálculos del rectángulo de selección: determinación del rectángulo delimitador de un elemento visual.  
  
 Sin embargo, el objeto <xref:System.Windows.Media.Visual> no incluye compatibilidad con características que no son de representación, tales como:  
  
-   Control de eventos  
  
-   Diseño  
  
-   Estilos  
  
-   Enlace de datos  
  
-   Globalización  
  
 <xref:System.Windows.Media.Visual> se expone como una clase abstracta pública de la que se deben derivar las clases secundarias.  En la ilustración siguiente se muestra la jerarquía de los objetos visuales que se exponen en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 ![Diagrama de clases derivadas del objeto Visual](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
Jerarquía de la clase Visual  
  
### Clase DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto.  Esta clase se considera ligera porque no proporciona administración del diseño ni control de eventos, lo que mejora su rendimiento en tiempo de ejecución.  Por esta razón, los dibujos son idóneos para fondos e imágenes prediseñadas.  <xref:System.Windows.Media.DrawingVisual> se puede utilizar para crear un objeto visual personalizado.  Para obtener más información, consulte [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
### Clase Viewport3DVisual  
 <xref:System.Windows.Media.Media3D.Viewport3DVisual> proporciona un puente entre los objetos 2D <xref:System.Windows.Media.Visual> y <xref:System.Windows.Media.Media3D.Visual3D>.  La clase <xref:System.Windows.Media.Media3D.Visual3D> es la clase base para los elementos visuales 3D.  <xref:System.Windows.Media.Media3D.Viewport3DVisual> requiere que se defina un valor <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> y un valor <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A>.  La cámara permite ver la escena.  La ventanilla establece dónde se asigna la proyección a la superficie 2D.  Para obtener más información sobre 3D en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  
  
### Clase ContainerVisual  
 La clase <xref:System.Windows.Media.ContainerVisual> se utiliza como contenedor de una colección de objetos <xref:System.Windows.Media.Visual>.  La clase <xref:System.Windows.Media.DrawingVisual> se deriva de la clase <xref:System.Windows.Media.ContainerVisual>, lo que le permite contener una colección de objetos visuales.  
  
### Dibujar contenido en objetos visuales  
 Un objeto <xref:System.Windows.Media.Visual> almacena sus datos de representación como una **lista de instrucciones de gráficos vectoriales**.  Cada elemento de la lista de instrucciones representa un conjunto de bajo nivel de datos de los gráficos y de recursos asociados en un formato serializado.  Hay cuatro tipos diferentes de datos de representación que pueden incluir contenido de dibujo.  
  
|Tipo de contenido de los dibujos|Descripción|  
|--------------------------------------|-----------------|  
|Gráficos vectoriales|Representa datos de gráficos vectoriales y e información de cualquier <xref:System.Windows.Media.Brush> y <xref:System.Windows.Media.Pen> asociado.|  
|Image|Representa una imagen dentro de una región definida por un <xref:System.Windows.Rect>.|  
|Glifo|Representa un dibujo que representa un <xref:System.Windows.Media.GlyphRun>, que es una secuencia de glifos de un recurso de fuente especificado.  Así es como se representa el texto.|  
|Vídeo|Representa un dibujo que representa el vídeo.|  
  
 <xref:System.Windows.Media.DrawingContext> permite rellenar un objeto <xref:System.Windows.Media.Visual> con contenido visual.  Cuando se utilizan los comandos de dibujo de un objeto <xref:System.Windows.Media.DrawingContext>, en realidad se está almacenando un conjunto de datos de representación que el sistema de gráficos utilizará más adelante; no se dibuja en la pantalla en tiempo real.  
  
 Al crear un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como <xref:System.Windows.Controls.Button>, el control genera implícitamente datos de representación para dibujarse a sí mismo.  Por ejemplo, al establecer la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> de <xref:System.Windows.Controls.Button> hace que el control almacene una representación de la representación de un glifo.  
  
 Un objeto <xref:System.Windows.Media.Visual> describe su contenido como uno o más objetos <xref:System.Windows.Media.Drawing> contenidos dentro de un <xref:System.Windows.Media.DrawingGroup>.  Un objeto <xref:System.Windows.Media.DrawingGroup> también describe las máscaras de opacidad, las transformaciones, los efectos de imagen y otras operaciones que se aplican a su contenido.  Las operaciones de <xref:System.Windows.Media.DrawingGroup> se aplican en el orden siguiente al representar contenido: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> y, a continuación, <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 En la ilustración siguiente se muestra el orden en el que se aplican las operaciones de <xref:System.Windows.Media.DrawingGroup> durante la secuencia de representación.  
  
 ![Orden de operaciones de DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
Orden de las operaciones de DrawingGroup  
  
 Para obtener más información, vea [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
#### Dibujar contenido en la capa visual  
 Nunca se crea directamente una instancia de <xref:System.Windows.Media.DrawingContext>; sin embargo, se puede adquirir un contexto de dibujo a partir de determinados métodos, como <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> y <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>.  En el ejemplo siguiente se recupera un objeto <xref:System.Windows.Media.DrawingContext> de un objeto <xref:System.Windows.Media.DrawingVisual> y se utiliza para dibujar un rectángulo.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### Enumerar contenido de dibujo en la capa visual  
 Además de sus otros usos, los objetos <xref:System.Windows.Media.Drawing> también proporcionan un modelo de objetos para enumerar el contenido de <xref:System.Windows.Media.Visual>.  
  
> [!NOTE]
>  Al enumerar el contenido del elemento visual, se recuperan objetos <xref:System.Windows.Media.Drawing>, no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales.  
  
 En el ejemplo siguiente se utiliza el método <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> para recuperar el valor de <xref:System.Windows.Media.DrawingGroup> de un objeto <xref:System.Windows.Media.Visual> y enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## Cómo utilizar los objetos visuales para crear controles  
 Muchos de los objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] están compuestos de otros objetos visuales, lo que significa que pueden contener diversas jerarquías de objetos descendientes.  Muchos de los elementos de interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como los controles, están compuestos de varios objetos visuales, que constituyen diferentes tipos de de representar los elementos.  Por ejemplo, el control <xref:System.Windows.Controls.Button> puede contener varios otros objetos, incluso <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter> y <xref:System.Windows.Controls.TextBlock>.  
  
 En el ejemplo de código siguiente se muestra un control <xref:System.Windows.Controls.Button> definido en el marcado.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Si enumerase los objetos visuales que comprenden el control <xref:System.Windows.Controls.Button> predeterminado, hallaría la jerarquía de objetos visuales ilustrada a continuación:  
  
 ![Diagrama de jerarquía de árbol visual](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.png "VisualLayerOverview03")  
Diagrama de jerarquía de árbol de elementos visuales  
  
 El control <xref:System.Windows.Controls.Button> contiene un elemento <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> que, a su vez, contiene un elemento <xref:System.Windows.Controls.ContentPresenter>.  El elemento <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> es responsable de dibujar un borde y un fondo para <xref:System.Windows.Controls.Button>.  El elemento <xref:System.Windows.Controls.ContentPresenter> es responsable de mostrar el contenido de <xref:System.Windows.Controls.Button>.  En este caso, puesto que se muestra texto, el elemento <xref:System.Windows.Controls.ContentPresenter> contiene un elemento <xref:System.Windows.Controls.TextBlock>.  El hecho de que el control <xref:System.Windows.Controls.Button> utilice <xref:System.Windows.Controls.ContentPresenter> quiere decir que el contenido podría representarse por otros elementos, como <xref:System.Windows.Controls.Image> o por una geometría, como <xref:System.Windows.Media.EllipseGeometry>.  
  
### Plantillas de control  
 La clave para la expansión de un control en una jerarquía de controles es <xref:System.Windows.Controls.ControlTemplate>.  Una plantilla de control especifica la jerarquía visual predeterminada de un control.  Al hacer referencia explícitamente a un control, se hace referencia implícitamente a su jerarquía visual.  Puede invalidar los valores predeterminados de una plantilla a fin de crear un aspecto visual personalizado para un control.  Por ejemplo, podría modificar el valor de color de fondo del control <xref:System.Windows.Controls.Button> de modo que utilice un valor de color de degradado lineal en lugar de un valor de color sólido.  Para obtener más información, vea [Estilos y plantillas de Button](../../../../docs/framework/wpf/controls/button-styles-and-templates.md).  
  
 Un elemento de interfaz de usuario, como un control <xref:System.Windows.Controls.Button>, contiene varias listas de instrucciones de gráficos vectoriales que describen la definición de representación completa de un control.  En el ejemplo de código siguiente se muestra un control <xref:System.Windows.Controls.Button> definido en el marcado.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Si enumerase los objetos visuales y las listas de instrucciones de gráficos vectoriales que comprenden el control <xref:System.Windows.Controls.Button>, hallaría la jerarquía de objetos ilustrada a continuación:  
  
 ![Diagrama de árbol visual y datos de representación](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
Diagrama de árbol visual y datos de representación  
  
 El control <xref:System.Windows.Controls.Button> contiene un elemento <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> que, a su vez, contiene un elemento <xref:System.Windows.Controls.ContentPresenter>.  El elemento <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> es responsable de dibujar todos los elementos gráficos discretos que constituyen el borde y el fondo de un botón.  El elemento <xref:System.Windows.Controls.ContentPresenter> es responsable de mostrar el contenido de <xref:System.Windows.Controls.Button>.  En este caso, puesto que se muestra una imagen, el elemento <xref:System.Windows.Controls.ContentPresenter> contiene un elemento <xref:System.Windows.Controls.Image>.  
  
 Deben tenerse en cuenta varios puntos sobre la jerarquía de objetos visuales y las listas de instrucciones de gráficos vectoriales:  
  
-   El orden en la jerarquía representa el orden de representación de la información de dibujo.  Partiendo del elemento visual raíz, los elementos secundarios se recorren de izquierda a derecha y de arriba abajo.  Si un elemento tiene elementos visuales secundarios, se recorren antes que los elementos del mismo nivel.  
  
-   Los elementos de nodos que no sean de hoja de la jerarquía, tales como <xref:System.Windows.Controls.ContentPresenter>, se utilizan para contener elementos secundarios, no contienen listas de instrucciones.  
  
-   Si un elemento visual contiene una lista de instrucciones de gráficos vectoriales y elementos visuales secundarios, la lista de instrucciones del elemento visual primario se representará antes que los dibujos de cualquiera de los objetos visuales secundarios.  
  
-   Los elementos de la lista de instrucciones de gráficos vectoriales se representan de izquierda a derecha.  
  
<a name="visual_tree"></a>   
## Árbol visual  
 El árbol visual contiene todos los elementos visuales utilizados en la interfaz de usuario de una aplicación.  Puesto que un elemento visual contiene información de dibujo conservada, puede considerar el árbol visual como una representación gráfica de la escena, que contiene toda la información de representación necesaria para crear la salida al dispositivo de pantalla.  Este árbol es la acumulación de todos los elementos visuales creados directamente por la aplicación, ya sea en el código o en el marcado.  El árbol visual también contiene todos los elementos visuales creados por la expansión de la plantilla de elementos tales como controles y objetos de datos.  
  
 En el ejemplo de código siguiente se muestra un elemento <xref:System.Windows.Controls.StackPanel> definido en el marcado.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Si enumerase los objetos visuales que comprenden el elemento <xref:System.Windows.Controls.StackPanel> del ejemplo de marcado, hallaría la jerarquía de objetos visuales ilustrada a continuación:  
  
 ![Diagrama de jerarquía de árbol visual](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.png "VisualLayerOverview05")  
Diagrama de jerarquía de árbol de elementos visuales  
  
### Orden de representación  
 El árbol visual determina el orden de representación de los objetos visuales y de dibujo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El orden del recorrido comienza en el elemento visual raíz, que es el nodo del nivel superior del árbol visual.  A continuación se recorren los elementos secundarios del elemento visual raíz, de izquierda a derecha.  Si un elemento visual tiene elementos secundarios, éstos últimos se recorren antes que los elementos que están en el mismo nivel que el elemento visual.  Esto significa que el contenido de un elemento visual secundario se representa delante del propio contenido del elemento visual.  
  
 ![Diagrama de orden de representación de árbol visual](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.png "VisualLayerOverview06")  
Diagrama del orden de representación del árbol visual  
  
### Elemento visual raíz  
 El **elemento visual raíz** es el elemento de nivel superior de la jerarquía de un árbol visual.  En la mayoría de las aplicaciones, la clase base del elemento visual raíz es <xref:System.Windows.Window> o <xref:System.Windows.Navigation.NavigationWindow>.  Sin embargo, si hospedase objetos visuales en una aplicación de Win32, el elemento visual raíz sería el elemento visual de nivel superior que hospedase en la ventana de Win32.  Para obtener más información, vea [Tutorial: Hospedar objetos visuales en una aplicación Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### Relaciones con el árbol lógico  
 El árbol lógico de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] representa los elementos de una aplicación en tiempo de ejecución.  Aunque no se manipula directamente este árbol, esta vista de la aplicación es útil para entender la herencia de propiedades y el enrutamiento de eventos.  A diferencia del árbol visual, el árbol lógico puede representar objetos de datos no visuales, tales como <xref:System.Windows.Documents.ListItem>.  En muchos casos, el árbol lógico se corresponde muy estrechamente con las definiciones de marcado de una aplicación.  En el ejemplo de código siguiente se muestra un elemento <xref:System.Windows.Controls.DockPanel> definido en el marcado.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Si enumerase los objetos lógicos que comprenden el elemento <xref:System.Windows.Controls.DockPanel> del ejemplo de marcado, hallaría la jerarquía de objetos lógicos ilustrada a continuación:  
  
 ![Diagrama de árbol](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.png "Tree1\_wcp")  
Diagrama de árbol lógico  
  
 El árbol visual y el árbol lógico se sincronizan con el conjunto actual de elementos de aplicación, con lo que se refleja cualquier adición, eliminación o modificación de elementos.  Sin embargo, los árboles presentan vistas diferentes de la aplicación.  A diferencia del árbol visual, el árbol lógico no expande el elemento <xref:System.Windows.Controls.ContentPresenter> de un control.  Esto significa que no existe una correspondencia unívoca directa entre un árbol lógico y un árbol visual para el mismo conjunto de objetos.  De hecho, al invocar el método <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> del objeto **LogicalTreeHelper** y el método <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> **VisualTreeHelper** del objeto utilizando el mismo elemento como parámetro se obtienen resultados diferentes.  
  
 Para obtener más información sobre el árbol lógico, vea [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
### Ver el árbol visual con XamlPad  
 La herramienta XamlPad de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una opción para ver y explorar el árbol visual que corresponde al contenido de [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] actualmente definido.  Haga clic en el botón **Show Visual Tree** en la barra de menús para mostrar el árbol visual.  A continuación se ilustra la expansión del contenido de [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] en los nodos del árbol visual en el panel **Visual Tree Explorer** de XamlPad:  
  
 ![Panel del explorador de árbol visual en XamlPad](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
Panel del explorador de árboles visuales de XamlPad  
  
 Observe que cada uno de los controles <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.Button> muestra una jerarquía de objetos visuales independiente en el panel **Visual Tree Explorer** de XamlPad.  Esto se debe a que los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen una <xref:System.Windows.Controls.ControlTemplate> que contiene el árbol visual de ese control.  Al hacer referencia explícitamente a un control, se hace referencia implícitamente a su jerarquía visual.  
  
### Crear perfiles de rendimiento visual  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de herramientas de generación de perfiles de rendimiento que permiten analizar el funcionamiento de la aplicación en tiempo de ejecución y determinar los tipos de optimización de rendimiento que se pueden aplicar.  La herramienta generador de perfiles de Visual proporciona una vista gráfica y completa de los datos de rendimiento a través de una asignación directa al árbol visual de la aplicación.  En esta captura de pantalla, la sección **CPU Usage** de Visual Profiler ofrece un desglose preciso del uso, por parte de un objeto, de servicios de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tales como la representación y el diseño.  
  
 ![Resultados del generador de perfiles de Visual](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf\_VisualProfiler\_04")  
Salida de la presentación de Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## Comportamiento de la representación visual  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] introduce varias características que afectan al comportamiento de representación de los objetos visuales: gráficos de modo retenido, gráficos vectoriales y gráficos independientes del dispositivo.  
  
### Gráficos de modo retenido  
 Una de las claves para entender el rol de los objetos visuales es comprender la diferencia entre los sistemas de gráficos de **modo inmediato** y de **modo retenido**.  Una aplicación de Win32 estándar basada en GDI o GDI\+ utiliza un sistema de gráficos de modo inmediato.  Esto significa que la aplicación es responsable de volver a dibujar la parte del área cliente que se ha invalidado, ya sea debido a una acción como el cambio de tamaño de una ventana, o a la modificación del aspecto visual de un objeto.  
  
 ![Diagrama de secuencia de representación de Win32](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
Diagrama de la secuencia de representación de Win32  
  
 En cambio, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un sistema de modo retenido.  Esto significa que los objetos de la aplicación que tienen aspecto visual definen un conjunto de datos de dibujo serializados.  Una vez definidos los datos de dibujo, el sistema se hace responsable en lo sucesivo de responder a todas las solicitudes de repetición del dibujo para representar los objetos de aplicación.  Incluso en tiempo de ejecución, se puede modificar o crear los objetos de aplicación y, aún así, confiar en que el sistema responderá a las solicitudes de dibujo.  La eficacia de un sistema de gráficos de modo retenido reside en que la aplicación conserva en todo momento la información de dibujo siempre en un estado serializado, pero deja al sistema la responsabilidad de la representación.  En el diagrama siguiente se muestra cómo delega la aplicación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para que responda a las solicitudes de dibujo.  
  
 ![Diagrama de secuencia de representación de WPF](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
Diagrama de la secuencia de representación de WPF  
  
#### Actualización inteligente del dibujo  
 Una de las mayores ventajas que aporta el uso de gráficos de modo retenidos es que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede optimizar con eficacia lo que es preciso volver a dibujar en la aplicación.  Aunque se trate de una escena compleja con varios niveles de opacidad, generalmente no se necesita escribir código específico para optimizar la actualización del dibujo.  Compare esto con la programación de Win32, en la que se puede llegar a dedicar mucho esfuerzo a optimizar la aplicación minimizando la cantidad de actualizaciones del dibujo que se efectúan en la región de actualización.  Vea [Redrawing in the Update Region](_win32_Redrawing_in_the_Update_Region) para obtener un ejemplo del tipo de complejidad que conlleva la optimización de la actualización del dibujo en las aplicaciones de Win32.  
  
### Gráficos vectoriales  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza **gráficos vectoriales** como su formato de representación de datos.  Los gráficos vectoriales, que incluyen gráficos vectoriales escalables \(SVG\), metarchivos de Windows \(.wmf\) y fuentes TrueType, almacenan los datos de representación y los transmiten como una lista de instrucciones que describen cómo volver a crear la imagen mediante los elementos primitivos de los gráficos.  Por ejemplo, las fuentes TrueType son fuentes de contorno que describen un conjunto de líneas, curvas y comandos, en lugar de una matriz de píxeles.  Una de las ventajas fundamentales de los gráficos vectoriales es la capacidad de adaptar su escala a cualquier tamaño y resolución.  
  
 Al contrario que los gráficos vectoriales, los gráficos de mapa de bits almacenan los datos de representación como una representación píxel por píxel de una imagen, previamente representada para una resolución específica.  Una de las diferencias fundamentales entre los formatos de gráficos de mapa de bits y vectorial es la fidelidad con respecto a la imagen de origen inicial.  Por ejemplo, cuando se modifica el tamaño de la imagen de origen, los sistemas de gráficos de mapa de bits ajustan la imagen, mientras que los sistemas de gráficos vectoriales adaptan su escala, conservando la fidelidad con la imagen inicial.  
  
 En la ilustración siguiente se muestra una imagen de origen cuyo tamaño se ha cambiado al 300%.  Observe las distorsiones que aparecen cuando se amplía la imagen de origen como imagen de gráficos de mapa de bits en lugar de ajustarla a escala como imagen de gráficos vectoriales.  
  
 ![Diferencias entre gráficos de trama y vectoriales](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
Diferencias entre gráficos de tramas y vectoriales  
  
 En el marcado siguiente se muestran dos elementos <xref:System.Windows.Shapes.Path> definidos.  El segundo elemento utiliza un objeto <xref:System.Windows.Media.ScaleTransform> para cambiar el tamaño de las instrucciones de dibujo del primer elemento al 300%.  Observe que las instrucciones de dibujo de los elementos <xref:System.Windows.Shapes.Path> no sufren cambio alguno.  
  
 [!code-xml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### Gráficos independientes de la resolución y del dispositivo  
 Existen dos factores del sistema que determinan el tamaño del texto y los gráficos en la pantalla: la resolución y los píxeles por pulgada \(PPP\).  La resolución describe el número de píxeles que aparecen en la pantalla.  A medida que aumenta la resolución, se reducen los píxeles, lo que hace que los gráficos y el texto parezcan menores.  Un gráfico mostrado en un monitor configurado con una resolución de 1024 x 768 parece mucho menor cuando la resolución se cambia a 1600 x 1200.  
  
 El otro valor del sistema, PPP, describe el tamaño de una pulgada de pantalla en píxeles.  La mayoría de los sistemas [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] tienen un valor de PPP de 96, lo que significa que pulgada de pantalla tiene 96 píxeles.  Al aumentar el valor de PPP se incrementa el tamaño de la pulgada de pantalla; al disminuir el valor de PPP se reduce el tamaño de la pulgada de pantalla.  Esto significa que una pulgada de pantalla no tiene el mismo tamaño que una pulgada real; en la mayoría de los sistemas, probablemente ambas pulgadas no sean iguales.  Cuando se incrementa el valor de PPP, los gráficos y el texto que tienen en cuenta los PPP aumentan, porque se ha incrementado el tamaño de la pulgada de pantalla.  Al aumentar el valor de PPP se puede facilitar la lectura del texto, especialmente con las resoluciones más altas.  
  
 No todas las aplicaciones tienen en cuenta el valor de PPP: algunas utilizan los píxeles de hardware como unidad de medida principal; en estas aplicaciones, cambiar los PPP del sistema no surte ningún efecto.  Muchas otras aplicaciones utilizan unidades que tienen en cuenta el valor de PPP para describir los tamaños de fuente, pero utilizan píxeles para describir todo lo demás.  Un valor de PPP demasiado pequeño o demasiado grande puede causar problemas del diseño en estas aplicaciones, porque el texto de la aplicación adapta su escala de acuerdo con el valor de PPP del sistema, pero, en cambio, la interfaz de usuario de la aplicación no lo hace.  Este problema se ha eliminado para las aplicaciones programadas mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite el ajuste automático de la escala, ya que utiliza píxeles independientes del dispositivo como unidad de medida principal, en lugar de los píxeles del hardware; la escala de los gráficos y del texto se adapta correctamente sin que el desarrollador de la aplicación tenga que realizar ninguna labor adicional.  En la ilustración siguiente se muestra un ejemplo de cómo aparecen el texto y los gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con distintos valores de PPP.  
  
 ![Gráficos y texto en diferentes valores de PPP](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm\_dpi\_setting\_examples")  
Gráficos y texto con distintos valores de PPP  
  
<a name="visualtreehelper_class"></a>   
## Clase VisualTreeHelper  
 La clase <xref:System.Windows.Media.VisualTreeHelper> es una clase auxiliar estática que proporciona funcionalidad de bajo nivel para programar en el nivel de objetos visuales, lo que resulta útil en escenarios muy concretos, como el de la programación de controles personalizados de alto rendimiento.  En la mayoría de los casos, los objetos del marco de trabajo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de nivel superior, tales como <xref:System.Windows.Controls.Canvas> y <xref:System.Windows.Controls.TextBlock>, proporcionan mayor flexibilidad y facilidad de uso.  
  
### Pruebas de posicionamiento  
 La clase <xref:System.Windows.Media.VisualTreeHelper> proporciona métodos para efectuar las pruebas de posicionamiento de los objetos visuales la compatibilidad de pruebas de posicionamiento predeterminada no satisface sus necesidades.  Puede utilizar los métodos <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> en la clase <xref:System.Windows.Media.VisualTreeHelper> para determinar si una geometría o el valor de coordenada de punto está dentro del límite de un objeto determinado, como un control o elemento gráfico.  Por ejemplo, podría utilizar las pruebas de posicionamiento para determinar si un clic del mouse dentro del rectángulo delimitador de un objeto pertenece a la geometría de un círculo. Si lo desea, también puede invalidar la implementación predeterminada de las pruebas de posicionamiento y realizar sus propios cálculos de pruebas de posicionamiento personalizadas.  
  
 Para obtener más información sobre pruebas de posicionamiento, vea [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
### Enumerar el árbol visual  
 La clase <xref:System.Windows.Media.VisualTreeHelper> proporciona la funcionalidad de enumerar los miembros de un árbol visual.  Para recuperar un objeto primario, llame al método <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A>.  Para recuperar un elemento secundario o un descendiente directo de un objeto visual, llame al método <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A>.  Este método devuelve el elemento secundario <xref:System.Windows.Media.Visual> del elemento primario en el índice especificado.  
  
 En el ejemplo siguiente se muestra cómo enumerar todos los descendientes de un objeto visual, que es una técnica que se puede utilizar si se desea serializar toda la información de representación de una jerarquía de objetos visuales.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 En la mayoría de los casos, el árbol lógico constituye una representación más útil de los elementos de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Aunque no se modifica directamente el árbol lógico, esta vista de la aplicación es útil para entender la herencia de propiedades y el enrutamiento de eventos.  A diferencia del árbol visual, el árbol lógico puede representar objetos de datos no visuales, tales como <xref:System.Windows.Documents.ListItem>.  Para obtener más información sobre el árbol lógico, vea [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 La clase <xref:System.Windows.Media.VisualTreeHelper> proporciona métodos para devolver el rectángulo delimitador de los objetos visuales.  Puede devolver el rectángulo delimitador de un objeto visual llamando a <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>.  Puede devolver el rectángulo delimitador de todos los descendientes de un objeto visual, incluido el propio objeto visual, llamando a <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>.  En el código siguiente se muestra cómo se calcularía el rectángulo delimitador de un objeto visual y todos sus descendientes.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## Vea también  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 <xref:System.Windows.Media.DrawingVisual>   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)   
 [Tutorial: Hospedar objetos visuales en una aplicación Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)   
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)