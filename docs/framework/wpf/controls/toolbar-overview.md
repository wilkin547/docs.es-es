---
title: Información general sobre controles ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186608"
---
# <a name="toolbar-overview"></a>Información general sobre controles ToolBar
<xref:System.Windows.Controls.ToolBar>Los controles son contenedores para un grupo de comandos o controles que normalmente están relacionados en su función. A <xref:System.Windows.Controls.ToolBar> normalmente contiene botones que invocan comandos.  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>Barra de herramientas (Control)  
 El <xref:System.Windows.Controls.ToolBar> control toma su nombre de la disposición de tipo barra de botones u otros controles en una sola fila o columna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> Los controles proporcionan un mecanismo de desbordamiento que coloca los <xref:System.Windows.Controls.ToolBar> elementos que no caben naturalmente dentro de un tamaño restringido en un área de desbordamiento especial. Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> los controles <xref:System.Windows.Controls.ToolBarTray> se suelen usar con el control relacionado, que proporciona un comportamiento de diseño especial, así como compatibilidad con el tamaño iniciado por el usuario y la organización de barras de herramientas.  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Especificar la posición de las barras de herramientas en un control ToolBarTray  
 Utilice <xref:System.Windows.Controls.ToolBar.Band%2A> las <xref:System.Windows.Controls.ToolBar.BandIndex%2A> propiedades y <xref:System.Windows.Controls.ToolBar> para <xref:System.Windows.Controls.ToolBarTray>colocar el archivo . <xref:System.Windows.Controls.ToolBar.Band%2A>indica la posición en <xref:System.Windows.Controls.ToolBar> la que <xref:System.Windows.Controls.ToolBarTray>se coloca el elemento primario. <xref:System.Windows.Controls.ToolBar.BandIndex%2A>indica el orden en <xref:System.Windows.Controls.ToolBar> el que se coloca dentro de su banda. En el ejemplo siguiente se <xref:System.Windows.Controls.ToolBar> muestra cómo <xref:System.Windows.Controls.ToolBarTray>utilizar esta propiedad para colocar controles dentro de un archivo .  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>Controles ToolBar con elementos de desbordamiento  
 A <xref:System.Windows.Controls.ToolBar> menudo, los controles contienen más elementos de los que caben en el tamaño de la barra de herramientas. Cuando esto sucede, el <xref:System.Windows.Controls.ToolBar> muestra un botón de desbordamiento. Para ver los elementos de desbordamiento, un usuario hace clic en el <xref:System.Windows.Controls.ToolBar>botón de desbordamiento y los elementos se muestran en una ventana emergente debajo de la . El gráfico siguiente <xref:System.Windows.Controls.ToolBar> muestra un elemento con desbordamiento:  
  
 ![Captura de pantalla que muestra una barra de herramientas con elementos de desbordamiento.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Puede especificar cuándo se coloca un elemento de una <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> barra de <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType> <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>herramientas <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>en el panel de desbordamiento estableciendo la propiedad adjunta en , , o . En el ejemplo siguiente se especifica que los cuatro últimos botones de la barra de herramientas siempre deben estar en el panel de desbordamiento.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 El <xref:System.Windows.Controls.ToolBar> utiliza <xref:System.Windows.Controls.Primitives.ToolBarPanel> a <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> y <xref:System.Windows.Controls.ControlTemplate>a en su .  El <xref:System.Windows.Controls.Primitives.ToolBarPanel> es responsable del diseño de los elementos en la barra de herramientas.  El <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> es responsable del diseño de los elementos que no caben en el <xref:System.Windows.Controls.ToolBar>archivo . Para ver un <xref:System.Windows.Controls.ControlTemplate> ejemplo <xref:System.Windows.Controls.ToolBar>de un fora , véase  
  
 [Estilos y plantillas de la barra](toolbar-styles-and-templates.md)de herramientas .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Aplicar estilo a controles en un elemento toolbar](how-to-style-controls-on-a-toolbar.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
