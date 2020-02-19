---
title: Información general sobre controles ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 460d4420d5faf849a8d05a94e0170aea384f69b4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452700"
---
# <a name="toolbar-overview"></a>Información general sobre controles ToolBar
<xref:System.Windows.Controls.ToolBar> controles son contenedores de un grupo de comandos o controles que normalmente están relacionados en su función. Un <xref:System.Windows.Controls.ToolBar> normalmente contiene botones que invocan comandos.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Barra de herramientas (Control)  
 El control <xref:System.Windows.Controls.ToolBar> toma su nombre de la organización de botones u otros controles en una sola fila o columna. los controles de <xref:System.Windows.Controls.ToolBar> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporcionan un mecanismo de desbordamiento que coloca en un área de desbordamiento especial los elementos que no se ajustan de forma natural dentro de un <xref:System.Windows.Controls.ToolBar> con restricciones de tamaño. Además, los controles de <xref:System.Windows.Controls.ToolBar> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se usan normalmente con el control de <xref:System.Windows.Controls.ToolBarTray> relacionado, que proporciona un comportamiento de diseño especial, así como compatibilidad con el ajuste de tamaño y la organización de barras de herramientas iniciados por el usuario.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Especificar la posición de las barras de herramientas en un control ToolBarTray  
 Utilice las propiedades <xref:System.Windows.Controls.ToolBar.Band%2A> y <xref:System.Windows.Controls.ToolBar.BandIndex%2A> para colocar el <xref:System.Windows.Controls.ToolBar> en el <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posición en la que se coloca el <xref:System.Windows.Controls.ToolBar> dentro de su <xref:System.Windows.Controls.ToolBarTray>primario. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica el orden en el que se coloca el <xref:System.Windows.Controls.ToolBar> dentro de su banda. En el ejemplo siguiente se muestra cómo utilizar esta propiedad para colocar <xref:System.Windows.Controls.ToolBar> controles dentro de un <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Controles ToolBar con elementos de desbordamiento  
 A menudo <xref:System.Windows.Controls.ToolBar> controles contienen más elementos de los que caben en el tamaño de la barra de herramientas. Cuando esto sucede, el <xref:System.Windows.Controls.ToolBar> muestra un botón de desbordamiento. Para ver los elementos de desbordamiento, un usuario hace clic en el botón de desbordamiento y los elementos se muestran en una ventana emergente debajo del <xref:System.Windows.Controls.ToolBar>. En el gráfico siguiente se muestra un <xref:System.Windows.Controls.ToolBar> con elementos de desbordamiento:  
  
 ![Captura de pantalla que muestra una barra de herramientas con elementos de desbordamiento.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Puede especificar Cuándo se coloca un elemento en una barra de herramientas en el panel de desbordamiento estableciendo la propiedad adjunta <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> en <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>o <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. En el ejemplo siguiente se especifica que los cuatro últimos botones de la barra de herramientas siempre deben estar en el panel de desbordamiento.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 En el <xref:System.Windows.Controls.ToolBar> se usa un <xref:System.Windows.Controls.Primitives.ToolBarPanel> y un <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> en su <xref:System.Windows.Controls.ControlTemplate>.  El <xref:System.Windows.Controls.Primitives.ToolBarPanel> es responsable del diseño de los elementos de la barra de herramientas.  El <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> es responsable del diseño de los elementos que no caben en el <xref:System.Windows.Controls.ToolBar>. Para obtener un ejemplo de un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, vea.  
  
 [Estilos y plantillas de ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Aplicar estilo a controles en un elemento toolbar](how-to-style-controls-on-a-toolbar.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout) (Ejemplo de galería de controles de WPF)
