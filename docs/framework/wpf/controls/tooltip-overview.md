---
title: Información general de información sobre herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181945"
---
# <a name="tooltip-overview"></a>Información general de información sobre herramientas
Una información sobre herramientas es una pequeña ventana emergente que aparece cuando un usuario <xref:System.Windows.Controls.Button>detiene el puntero del mouse sobre un elemento, como sobre un archivo . En este tema se presenta la información sobre herramientas y se explica cómo crear y personalizar el contenido de la información sobre herramientas.  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a>¿Qué es la información sobre herramientas?  
 Cuando un usuario mueve el puntero del mouse sobre un elemento que tiene información sobre herramientas, aparece una ventana con información sobre herramientas (por ejemplo, texto que describe la función de un control) durante un período de tiempo especificado. Si el usuario mueve el puntero del mouse fuera del control, la ventana desaparece porque el contenido de la información sobre herramientas deja de recibir el foco.  
  
 La información sobre herramientas puede contener una o más líneas de texto, imágenes, formas u otro contenido visual. Para definir la información sobre herramientas de un control, establezca una de las siguientes propiedades en el contenido de la información sobre herramientas.  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 La propiedad que utilice depende de si el control <xref:System.Windows.FrameworkContentElement> <xref:System.Windows.FrameworkElement> que define la información sobre herramientas hereda de la clase o.  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a>Creación de una información sobre herramientas  
 En el ejemplo siguiente se muestra cómo <xref:System.Windows.FrameworkElement.ToolTip%2A> crear <xref:System.Windows.Controls.Button> una información sobre herramientas simple estableciendo la propiedad de un control en una cadena de texto.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 También puede definir una <xref:System.Windows.Controls.ToolTip> información sobre herramientas como un objeto. En el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo siguiente <xref:System.Windows.Controls.ToolTip> se utiliza para <xref:System.Windows.Controls.TextBox> especificar un objeto como información sobre herramientas de un elemento. Tenga en cuenta que <xref:System.Windows.Controls.ToolTip> en <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> el ejemplo se especifica el estableciendo la propiedad.  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.ToolTip> se utiliza código para generar un objeto. En el <xref:System.Windows.Controls.ToolTip> ejemplo`tt`se crea un <xref:System.Windows.Controls.Button>( ) y se asocia con un archivo .  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 También puede crear contenido de información <xref:System.Windows.Controls.ToolTip> sobre herramientas que no esté definido como un <xref:System.Windows.Controls.DockPanel>objeto encerrando el contenido de información sobre herramientas en un elemento de diseño, como un archivo . En el ejemplo siguiente <xref:System.Windows.FrameworkElement.ToolTip%2A> se muestra <xref:System.Windows.Controls.TextBox> cómo establecer la propiedad <xref:System.Windows.Controls.DockPanel> de un contenido a contenido que se incluye en un control.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Uso de las propiedades de las clases ToolTip y ToolTipService  
 Para personalizar el contenido de la información sobre herramientas, puede establecer las propiedades visuales y aplicar estilos. Si define el contenido <xref:System.Windows.Controls.ToolTip> de información sobre herramientas como <xref:System.Windows.Controls.ToolTip> un objeto, puede establecer las propiedades visuales del objeto. De lo contrario, debe establecer <xref:System.Windows.Controls.ToolTipService> propiedades adjuntas equivalentes en la clase.  
  
 Para obtener un ejemplo de cómo establecer propiedades para especificar <xref:System.Windows.Controls.ToolTip> la <xref:System.Windows.Controls.ToolTipService> posición del contenido de información sobre herramientas mediante las propiedades y, vea [Colocar una información sobre herramientas](how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a>Aplicar estilos a una información sobre herramientas  
 Puede aplicar <xref:System.Windows.Controls.ToolTip> estilo a definiendo un <xref:System.Windows.Style>archivo . En el ejemplo <xref:System.Windows.Style> `Simple` siguiente se define un llamado <xref:System.Windows.Controls.ToolTip> que muestra cómo <xref:System.Windows.Controls.Control.Background%2A>compensar <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A>la <xref:System.Windows.Controls.Control.FontWeight%2A>colocación y cambiar su apariencia estableciendo el valor , , , y .  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Uso de las propiedades de intervalo de tiempo de ToolTipService  
 La <xref:System.Windows.Controls.ToolTipService> clase proporciona las siguientes propiedades para <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>establecer <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>los <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>tiempos de visualización de información sobre herramientas: , , y .  
  
 Utilice <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> las <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> propiedades y para especificar un retraso, normalmente breve, antes de que aparezca un <xref:System.Windows.Controls.ToolTip> y también para especificar cuánto tiempo permanece visible un. <xref:System.Windows.Controls.ToolTip> Para obtener más información, consulte [How to: Delay the Display of a ToolTip](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)) (Cómo: Retrasar la visualización de una información sobre herramientas).  
  
 La <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad determina si la información sobre herramientas para diferentes controles aparece sin un retraso inicial al mover el puntero del mouse rápidamente entre ellos. Para obtener más <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> información acerca de la propiedad, vea [Usar la propiedad BetweenShowDelay](how-to-use-the-betweenshowdelay-property.md).  
  
 En el ejemplo siguiente se muestra cómo establecer estas propiedades para una información sobre herramientas.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [Temas de información](tooltip-how-to-topics.md)
