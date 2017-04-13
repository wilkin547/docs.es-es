---
title: "Informaci&#243;n general sobre el uso del dise&#241;o autom&#225;tico | Microsoft Docs"
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
  - "diseño automático"
  - "diseño, automáticamente"
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Informaci&#243;n general sobre el uso del dise&#241;o autom&#225;tico
En este tema se introducen instrucciones para los programadores sobre cómo escribir aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] localizables.  En el pasado, la localización de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] era un proceso largo.  Se necesitaba un ajuste píxel a píxel para cada idioma al que se adaptaba la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  En la actualidad, con un diseño correcto y siguiendo las normas de codificación apropiadas, se puede construir la [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de modo que los localizadores tengan que realizar menos cambios de tamaño y posición.  El enfoque al escribir aplicaciones cuyo tamaño y posición pueda cambiarse con mayor facilidad se denomina diseño automático y se puede lograr utilizando el diseño de aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Este tema contiene las secciones siguientes.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Ventajas de utilizar el diseño automático](#advantages_of_autolayout)  
  
-   [Diseño automático y controles](#autolayout_controls)  
  
-   [Diseño automático y normas de codificación](#autolayout_coding)  
  
-   [Diseño automático y cuadrículas](#autolay_grids)  
  
-   [Diseño automático y cuadrículas mediante la propiedad IsSharedSizeScope](#autolay_grids_issharedsizescope)  
  
-   [Temas relacionados](#seeAlsoToggle)  
  
<a name="advantages_of_autolayout"></a>   
## Ventajas de utilizar el diseño automático  
 Dado que el sistema de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es eficaz y flexible, proporciona la capacidad de diseñar elementos en una aplicación que se puedan ajustar para adaptarlos a los requisitos de los distintos idiomas.  En la lista siguiente se señalan algunas de las ventajas del diseño automático.  
  
-   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se muestra correctamente en todos los idiomas.  
  
-   Se reduce la necesidad de reajustar la posición y el tamaño de los controles una vez traducido el texto.  
  
-   Se reduce la necesidad de reajustar el tamaño de la ventana.  
  
-   El diseño de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se representa correctamente en cualquier idioma.  
  
-   La localización se puede reducir hasta el punto de consistir en poco más que la traducción de las cadenas.  
  
<a name="autolayout_controls"></a>   
## Diseño automático y controles  
 El diseño automático permite ajustar automáticamente el tamaño de los controles en la aplicación.  Por ejemplo, un control puede cambiar para alojar la longitud de una cadena.  Esta función permite a los localizadores traducir la cadena; ya no tienen que cambiar el tamaño del control para ajustar el texto traducido.  En el ejemplo siguiente se crea un botón con contenido en inglés.  
  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 En el ejemplo, lo único que hay que hacer para obtener un botón en español es cambiar el texto.  Por ejemplo,  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra el resultado de los ejemplos de código.  
  
 ![El mismo botón con texto en diferentes idiomas](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Botón cuyo tamaño se ajusta automáticamente  
  
<a name="autolayout_coding"></a>   
## Diseño automático y normas de codificación  
 El uso del enfoque del diseño automático exige aplicar un conjunto de normas y reglas de codificación y diseño a fin de generar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se puede localizar plenamente.  Las instrucciones siguientes le ayudarán a codificar el diseño automático.  
  
|Normas de codificación|Descripción|  
|----------------------------|-----------------|  
|No utilice posiciones absolutas.|-   No utilice el objeto <xref:System.Windows.Controls.Canvas>, porque coloca los elementos con posiciones absolutas.<br />-   Utilice <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.Grid> para colocar los controles.<br />-   Para obtener una explicación de los distintos tipos de paneles, consulte [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|No se establezca un tamaño fijo para una ventana.|-   Utilice <xref:System.Windows.Window.SizeToContent%2A>.<br />-   Por ejemplo:<br /><br /> [!code-xml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Agregar una propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>.|<ul><li>Agregue una propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> al elemento raíz de la aplicación.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera cómoda de admitir diseños horizontales, bidireccionales y verticales.  En el marco de trabajo de presentación, se puede utilizar la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> para definir el diseño.  Los modelos de dirección de flujo son:<br /><br /> <ul><li><xref:System.Windows.FlowDirection> \(LrTb\): diseño horizontal para fuentes latinas, de Asia oriental, etc.</li><li><xref:System.Windows.FlowDirection> \(RlTb\): diseño bidireccional para fuentes árabes, hebreas, etc.</li></ul></li></ul>|  
|Utilice fuentes compuestas en lugar de fuentes físicas.|<ul><li>Con las fuentes compuestas, no es preciso localizar la propiedad <xref:System.Windows.Controls.Control.FontFamily%2A>.</li><li>Los programadores pueden utilizar una de las fuentes siguientes o crear la suya propia.<br /><br /> <ul><li>Interfaz de usuario global</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Agregue xml:lang.|-   Agregue el atributo `xml:lang` en el elemento raíz de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; por ejemplo, `xml:lang="en-US"` para una aplicación en inglés de Estados Unidos.<br />-   Dado que las fuentes compuestas utilizan `xml:lang` para determinar qué fuente utilizar, establezca esta propiedad para admitir escenarios multilingües.|  
  
<a name="autolay_grids"></a>   
## Diseño automático y cuadrículas  
 El elemento <xref:System.Windows.Controls.Grid> resulta útil para el diseño automático porque permite al programador colocar los elementos.  Un control <xref:System.Windows.Controls.Grid> es capaz de distribuir el espacio disponible entre sus elementos secundarios, que se organizan en columnas y filas.  Los elementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] pueden abarcar varias celdas y es posible que haya cuadrículas dentro de otras cuadrículas.  Las cuadrículas son útiles porque permiten crear y colocar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] compleja.  En el ejemplo siguiente se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto.  Observe que el alto y ancho de las celdas están establecidos en <xref:System.Windows.GridUnitType>; por consiguiente, la celda que contiene el botón con una imagen se ajusta a la imagen.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra la cuadrícula generada por el código anterior.  
  
 ![Ejemplo de cuadrícula](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Cuadrícula  
  
<a name="autolay_grids_issharedsizescope"></a>   
## Diseño automático y cuadrículas mediante la propiedad IsSharedSizeScope  
 El elemento <xref:System.Windows.Controls.Grid> resulta útil en las aplicaciones localizables para crear controles que se ajusten a su contenido.  Sin embargo, a veces se desea que los controles mantengan un tamaño determinado sin tener en cuenta su contenido.  Por ejemplo, probablemente no desee que el tamaño de los botones "Aceptar", "Cancelar" o "Examinar" se ajuste al contenido.  En este caso la propiedad adjunta <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=fullName> resulta útil para compartir el mismo tamaño entre varios elementos de la cuadrícula.  En el ejemplo siguiente se muestra cómo compartir el tamaño de las columnas y filas entre varios elementos de <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Nota**: para obtener el ejemplo de código completo, consulte [Compartir propiedades de ajuste de tamaño entre elementos Grid](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## Vea también  
 [Globalización de WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Usar el diseño automático para crear un botón](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [Usar una cuadrícula para el diseño automático](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)