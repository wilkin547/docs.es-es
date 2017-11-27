---
title: "Información general sobre el uso del diseño automático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c9f5b9a6665778bc313febb039aeeeb2e484a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="use-automatic-layout-overview"></a>Información general sobre el uso del diseño automático
Este tema presentan las directrices para desarrolladores sobre cómo escribir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones con localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]. En el pasado, la localización de un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] era un proceso lento. Cada idioma que el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se adaptó para un ajuste de píxel por píxel es necesario. Hoy en día con un diseño correcto y derecha normas de codificación, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] puede crearse para que los localizadores tengan menor cambiando el tamaño y posición. El enfoque para escribir aplicaciones que pueden resultar más fácilmente cuyo tamaño ha cambiado y cambia de posición se denomina diseño automático y se consigue mediante el uso de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño de la aplicación.  
  
<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a>Ventajas de usar el diseño automático  
 Dado que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de presentación es eficaz y flexible, proporciona la capacidad de elementos de diseño en una aplicación que se pueden ajustar para ajustarse a los requisitos de los distintos idiomas. En la lista siguiente se indican algunas de las ventajas del diseño automático.  
  
-   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se muestra correctamente en cualquier idioma.  
  
-   Reduce la necesidad de reajustar la posición y el tamaño de los controles una vez traducido el texto.  
  
-   Reduce la necesidad de reajustar el tamaño de la ventana.  
  
-   El diseño de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se representa correctamente en cualquier lenguaje.  
  
-   La localización se puede reducir hasta el punto de que es poco más que la traducción de cadenas.  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a>Diseño automático y controles  
 El diseño automático permite que una aplicación ajuste automáticamente el tamaño de un control. Por ejemplo, un control puede cambiar para adaptarse a la longitud de una cadena. Esta capacidad permite a los localizadores traducir la cadena sin necesidad de cambiar el tamaño del control para que se ajuste al texto traducido. En el ejemplo siguiente se crea un botón con contenido en inglés.  
  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 En el ejemplo, lo único que debe hacer para crear un botón en español es cambiar el texto. Por ejemplo,  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra la salida de los ejemplos de código.  
  
 ![El mismo botón con texto en diferentes idiomas](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Botón ajustable automáticamente  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a>Diseño automático y estándares de codificación  
 Utiliza el enfoque de diseño automático requiere un conjunto de estándares de codificación y diseño y las reglas para generar un totalmente localizable [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Las instrucciones siguientes le ayudarán en la codificación del diseño automático.  
  
|Estándares de codificación|Descripción|  
|----------------------|-----------------|  
|No use posiciones absolutas.|-No utilice <xref:System.Windows.Controls.Canvas> porque coloca los elementos sin duda.<br />-Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, y <xref:System.Windows.Controls.Grid> para colocar los controles.<br />-Para obtener información sobre los distintos tipos de paneles, consulte [paneles de información general sobre](../../../../docs/framework/wpf/controls/panels-overview.md).|  
|No establezca un tamaño fijo para una ventana.|-Use <xref:System.Windows.Window.SizeToContent%2A>.<br />- Por ejemplo:<br /><br /> [!code-xaml[LocalizationGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]|  
|Agregue <xref:System.Windows.FrameworkElement.FlowDirection%2A>.|<ul><li>Agregar un <xref:System.Windows.FrameworkElement.FlowDirection%2A> para el elemento raíz de la aplicación.</li><li>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera cómoda de admitir diseños horizontales, bidireccionales y verticales. En el marco de presentación, el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad puede utilizarse para definir el diseño. Los patrones de dirección de flujo son:<br /><br /> <ul><li><xref:System.Windows.FlowDirection.LeftToRight>(LrTb): diseño horizontal para latino, Asia oriental y así sucesivamente.</li><li><xref:System.Windows.FlowDirection.RightToLeft>(RlTb): bidireccional para árabe, hebreo y así sucesivamente.</li></ul></li></ul>|  
|Use fuentes compuestas en vez de fuentes físicas.|<ul><li>Con las fuentes compuestas, el <xref:System.Windows.Controls.Control.FontFamily%2A> propiedad no necesita va a localizar.</li><li>Los desarrolladores pueden usar una de las fuentes siguientes o crear sus propias fuentes.<br /><br /> <ul><li>Interfaz de usuario global</li><li>Global San Serif</li><li>Global Serif</li></ul></li></ul>|  
|Agregue xml:lang.|-Agregar el `xml:lang` atributo en el elemento raíz de su [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], como `xml:lang="en-US"` para una aplicación de inglés.<br />-Dado que las fuentes compuestas utilizan `xml:lang` para determinar qué fuente que se va a utilizar, establezca esta propiedad para admitir escenarios multilingües.|  
  
<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a>Diseño automático y cuadrículas  
 El <xref:System.Windows.Controls.Grid> elemento, es útil para el diseño automático porque permite al programador colocar los elementos. Un <xref:System.Windows.Controls.Grid> control es capaz de distribuir el espacio disponible entre sus elementos secundarios, con una organización de fila y columna. El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos pueden abarcar varias celdas, y es posible que haya cuadrículas dentro de cuadrículas. Las cuadrículas son útiles porque le permiten crear y colocar complejo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En el ejemplo siguiente se muestra cómo se usa una cuadrícula para colocar algunos botones y texto. Observe que el alto y ancho de las celdas se establecen en <xref:System.Windows.GridUnitType.Auto>; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra la cuadrícula que ha producido el código anterior.  
  
 ![Ejemplo de cuadrícula](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Cuadrícula  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>Diseño automático y cuadrículas mediante el uso de la propiedad IsSharedSizeScope  
 Un <xref:System.Windows.Controls.Grid> elemento resulta útil en aplicaciones localizables para crear controles que se ajustan para ajustar el contenido. Pero en ocasiones le interesará que los controles conserven un tamaño determinado independientemente del contenido. Por ejemplo, si tiene los botones "Aceptar", "Cancelar" y "Examinar", probablemente no le interesará que su tamaño se ajuste el contenido. En este caso el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> propiedad adjunta es útil para compartir el mismo tamaño entre varios elementos de la cuadrícula. En el ejemplo siguiente se muestra cómo compartir datos entre varios de ajuste de tamaño de fila y columna <xref:System.Windows.Controls.Grid> elementos.  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 **Tenga en cuenta** para el ejemplo de código completo, vea [propiedades de recurso compartido de ajuste de tamaño entre cuadrículas](../../../../docs/framework/wpf/controls/how-to-share-sizing-properties-between-grids.md)  
  
## <a name="see-also"></a>Vea también  
 [Globalización de WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [Usar el diseño automático para crear un botón](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [Usar una cuadrícula para el diseño automático](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
