---
title: Información general sobre controles ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: 711d55e46fb548787976a1f966c9fbf6dc7f12d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790863"
---
# <a name="toolbar-overview"></a>Información general sobre controles ToolBar
<xref:System.Windows.Controls.ToolBar> los controles son contenedores para un grupo de comandos o controles que suelen estar relacionados en su función. Un <xref:System.Windows.Controls.ToolBar> suele contener botones que invocan comandos.  

<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a>Barra de herramientas (Control)  
 El <xref:System.Windows.Controls.ToolBar> control toma su nombre de la organización de similares de la barra de botones u otros controles en una sola fila o columna. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> los controles proporcionan un mecanismo de desbordamiento que coloca los elementos que no caben naturalmente dentro de un tamaño limitado <xref:System.Windows.Controls.ToolBar> en un área de desbordamiento especial. Además, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> controles suelen utilizarse con relacionado <xref:System.Windows.Controls.ToolBarTray> control, que proporciona el comportamiento de diseño especial, así como soporte técnico para iniciadas por el usuario cambiar el tamaño y la disposición de las barras de herramientas.  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>Especificar la posición de las barras de herramientas en un control ToolBarTray  
 Use la <xref:System.Windows.Controls.ToolBar.Band%2A> y <xref:System.Windows.Controls.ToolBar.BandIndex%2A> propiedades para colocar el <xref:System.Windows.Controls.ToolBar> en el <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posición en la que el <xref:System.Windows.Controls.ToolBar> se coloca dentro de su elemento primario <xref:System.Windows.Controls.ToolBarTray>. <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica el orden en que el <xref:System.Windows.Controls.ToolBar> se coloca dentro de su banda. El ejemplo siguiente se muestra cómo utiliza esta propiedad para colocar <xref:System.Windows.Controls.ToolBar> controla dentro de un <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a>Controles ToolBar con elementos de desbordamiento  
 A menudo <xref:System.Windows.Controls.ToolBar> controles contienen más elementos que pueden caber en el tamaño de la barra de herramientas. Cuando esto sucede, el <xref:System.Windows.Controls.ToolBar> muestra un botón de desbordamiento. Para ver los elementos de desbordamiento, un usuario hace clic en el botón de desbordamiento y los elementos se muestran en una ventana emergente que aparece a continuación el <xref:System.Windows.Controls.ToolBar>. El gráfico siguiente muestra un <xref:System.Windows.Controls.ToolBar> con elementos de desbordamiento:  
  
 ![Captura de pantalla que muestra una barra de herramientas con elementos de desbordamiento.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 Puede especificar cuando se coloca un elemento en una barra de herramientas en el panel de desbordamiento estableciendo el <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> propiedad adjunta <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, o <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. En el ejemplo siguiente se especifica que los cuatro últimos botones de la barra de herramientas siempre deben estar en el panel de desbordamiento.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 El <xref:System.Windows.Controls.ToolBar> usa un <xref:System.Windows.Controls.Primitives.ToolBarPanel> y un <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> en su <xref:System.Windows.Controls.ControlTemplate>.  El <xref:System.Windows.Controls.Primitives.ToolBarPanel> es responsable del diseño de los elementos en la barra de herramientas.  El <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> es responsable del diseño de los elementos que no caben en la <xref:System.Windows.Controls.ToolBar>. Para obtener un ejemplo de un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, vea  
  
 [Estilos y plantillas de ToolBar](toolbar-styles-and-templates.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [Aplicar estilo a controles en un elemento toolbar](how-to-style-controls-on-a-toolbar.md)
- [WPF Controls Gallery Sample](https://go.microsoft.com/fwlink/?LinkID=160053) (Ejemplo de galería de controles de WPF)
