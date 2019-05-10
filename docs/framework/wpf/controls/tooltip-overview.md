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
ms.openlocfilehash: 097eb8c50a6a21f9d356aba562c95fd2d9d09022
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630768"
---
# <a name="tooltip-overview"></a>Información general de información sobre herramientas
Información sobre herramientas es una pequeña ventana emergente que aparece cuando un usuario detiene el puntero del mouse sobre un elemento, tal como sobreutilizado un <xref:System.Windows.Controls.Button>. En este tema se presenta la información sobre herramientas y se explica cómo crear y personalizar el contenido de la información sobre herramientas.  

<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>¿Qué es la información sobre herramientas?  
 Cuando un usuario mueve el puntero del mouse sobre un elemento que tiene información sobre herramientas, aparece una ventana con información sobre herramientas (por ejemplo, texto que describe la función de un control) durante un período de tiempo especificado. Si el usuario mueve el puntero del mouse fuera del control, la ventana desaparece porque el contenido de la información sobre herramientas deja de recibir el foco.  
  
 La información sobre herramientas puede contener una o más líneas de texto, imágenes, formas u otro contenido visual. Para definir la información sobre herramientas de un control, establezca una de las siguientes propiedades en el contenido de la información sobre herramientas.  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 La propiedad que utilice depende de si el control que define la información sobre herramientas se hereda de la <xref:System.Windows.FrameworkContentElement> o <xref:System.Windows.FrameworkElement> clase.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>Creación de una información sobre herramientas  
 El ejemplo siguiente muestra cómo crear una información sobre herramientas simple estableciendo la <xref:System.Windows.FrameworkElement.ToolTip%2A> propiedad para un <xref:System.Windows.Controls.Button> control a una cadena de texto.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 También puede definir una información sobre herramientas como un <xref:System.Windows.Controls.ToolTip> objeto. En el ejemplo siguiente se usa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para especificar un <xref:System.Windows.Controls.ToolTip> objeto como la información sobre herramientas de un <xref:System.Windows.Controls.TextBox> elemento. Tenga en cuenta que el ejemplo se especifica la <xref:System.Windows.Controls.ToolTip> estableciendo el <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> propiedad.  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 En el ejemplo siguiente se utiliza código para generar un <xref:System.Windows.Controls.ToolTip> objeto. El ejemplo se crea un <xref:System.Windows.Controls.ToolTip> (`tt`) y lo asocia a un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 También puede crear contenido de información sobre herramientas que no está definido como un <xref:System.Windows.Controls.ToolTip> objeto incluyendo el contenido de la información sobre herramientas en un elemento de diseño, como un <xref:System.Windows.Controls.DockPanel>. El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.FrameworkElement.ToolTip%2A> propiedad de un <xref:System.Windows.Controls.TextBox> al contenido incluido en un <xref:System.Windows.Controls.DockPanel> control.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Uso de las propiedades de las clases ToolTip y ToolTipService  
 Para personalizar el contenido de la información sobre herramientas, puede establecer las propiedades visuales y aplicar estilos. Si define la información sobre herramientas contenido como un <xref:System.Windows.Controls.ToolTip> objeto, puede establecer las propiedades visuales de la <xref:System.Windows.Controls.ToolTip> objeto. En caso contrario, debe establecer las propiedades adjuntas equivalentes en el <xref:System.Windows.Controls.ToolTipService> clase.  
  
 Para obtener un ejemplo de cómo establecer propiedades para especificar la posición del contenido de la información sobre herramientas mediante el <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService> propiedades, consulte [situar una información sobre herramientas](how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>Aplicar estilos a una información sobre herramientas  
 Puedes aplicar estilo a un <xref:System.Windows.Controls.ToolTip> definiendo un personalizado <xref:System.Windows.Style>. En el ejemplo siguiente se define un <xref:System.Windows.Style> llamado `Simple` que muestra cómo desplazar la ubicación de la <xref:System.Windows.Controls.ToolTip> y cambiar su apariencia estableciendo el <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, y <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Uso de las propiedades de intervalo de tiempo de ToolTipService  
 El <xref:System.Windows.Controls.ToolTipService> clase proporciona las siguientes propiedades para establecer información sobre herramientas muestran horas: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Use la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> y <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> propiedades para especificar un retraso, normalmente breve, antes un <xref:System.Windows.Controls.ToolTip> aparece y también para especificar cuánto tiempo un <xref:System.Windows.Controls.ToolTip> permanece visible. Para obtener más información, vea [Cómo: Retrasar la visualización de información sobre herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).  
  
 El <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad determina si información sobre herramientas para los distintos controles aparece sin retraso inicial al mover el puntero del mouse rápidamente entre ellos. Para obtener más información sobre la <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad, vea [usar la propiedad BetweenShowDelay](how-to-use-the-betweenshowdelay-property.md).  
  
 En el ejemplo siguiente se muestra cómo establecer estas propiedades para una información sobre herramientas.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [Temas "Cómo..."](tooltip-how-to-topics.md)
