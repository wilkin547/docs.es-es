---
title: Recopilar entrada manuscrita digital
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747028"
---
# <a name="collect-ink"></a>Recopilar entrada de lápiz

La plataforma [Windows Presentation Foundation](../index.md) recopila entradas de lápiz digitales como parte esencial de su funcionalidad. En este tema se describen los métodos para la recopilación de entradas manuscritas en Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Prerequisites

Para usar los ejemplos siguientes, primero debe instalar Visual Studio y el Windows SDK. También debe saber cómo escribir aplicaciones para WPF. Para obtener más información sobre cómo empezar a usar WPF, vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Usar el elemento InkCanvas

El elemento <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> proporciona la manera más fácil de recopilar entradas de lápiz en WPF. Use un elemento <xref:System.Windows.Controls.InkCanvas> para recibir y Mostrar entradas manuscritas. Normalmente, la entrada de lápiz se realiza con un lápiz, que interactúa con un digitalizador para generar trazos de lápiz. También se puede usar un mouse en lugar de un lápiz. Los trazos creados se representan como objetos <xref:System.Windows.Ink.Stroke> y se pueden manipular mediante programación y mediante la entrada del usuario. El <xref:System.Windows.Controls.InkCanvas> permite a los usuarios seleccionar, modificar o eliminar una <xref:System.Windows.Ink.Stroke>existente.

Mediante el uso de XAML, puede configurar la colección de entradas manuscritas tan fácilmente como agregar un elemento **InkCanvas** al árbol. En el ejemplo siguiente se agrega una <xref:System.Windows.Controls.InkCanvas> a un proyecto de WPF predeterminado creado en Visual Studio:

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

El elemento **InkCanvas** también puede contener elementos secundarios, lo que permite agregar capacidades de anotación manuscrita a casi cualquier tipo de elemento XAML. Por ejemplo, para agregar capacidades de entrada de lápiz a un elemento de texto, simplemente conviértalo en un elemento secundario de un <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Agregar compatibilidad para marcar una imagen con tinta es igual de fácil:

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Modos de InkCollection

El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con varios modos de entrada a través de su propiedad <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.

### <a name="manipulate-ink"></a>Manipular la entrada manuscrita

El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con muchas operaciones de edición de tinta. Por ejemplo, <xref:System.Windows.Controls.InkCanvas> admite el borrado de la parte trasera del lápiz y no se necesita ningún código adicional para agregar la funcionalidad al elemento.

#### <a name="selection"></a>Número de selección

Establecer el modo de selección es tan sencillo como establecer la propiedad <xref:System.Windows.Controls.InkCanvasEditingMode> en **Select**.

El código siguiente establece el modo de edición basándose en el valor de un <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Use la propiedad <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> para cambiar la apariencia de los trazos de tinta. Por ejemplo, el miembro <xref:System.Windows.Ink.DrawingAttributes.Color%2A> de <xref:System.Windows.Ink.DrawingAttributes> establece el color de la <xref:System.Windows.Ink.Stroke>representada.

En el ejemplo siguiente se cambia el color de los trazos seleccionados a rojo:

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

La propiedad <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proporciona acceso a propiedades como el alto, el ancho y el color de los trazos que se van a crear en un <xref:System.Windows.Controls.InkCanvas>. Una vez que se cambia el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros especificados en el <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.

Además de modificar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede usar la sintaxis XAML para especificar <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades.

En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Ink.DrawingAttributes.Color%2A>. Para usar este código, cree un nuevo proyecto de WPF denominado "HelloInkCanvas" en Visual Studio. Reemplace el código del archivo *MainWindow. Xaml* por el código siguiente:

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

A continuación, agregue los siguientes controladores de eventos de botón al archivo de código subyacente, dentro de la clase MainWindow:

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Después de copiar este código, presione **F5** en Visual Studio para ejecutar el programa en el depurador.

Observe cómo el <xref:System.Windows.Controls.StackPanel> coloca los botones encima de la <xref:System.Windows.Controls.InkCanvas>. Si intenta realizar una entrada manuscrita sobre la parte superior de los botones, el <xref:System.Windows.Controls.InkCanvas> recopila y representa la tinta detrás de los botones. Esto se debe a que los botones son del mismo nivel que el <xref:System.Windows.Controls.InkCanvas> en lugar de secundarios. Además, los botones son superiores en el orden de z, por lo que la entrada de lápiz se representa detrás de ellos.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
