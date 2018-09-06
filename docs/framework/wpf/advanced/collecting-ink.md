---
title: Recopilar entradas de lápiz en aplicaciones WPF
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
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787449"
---
# <a name="collect-ink"></a>Recopilar entradas de lápiz

La plataforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) recopila entradas de lápiz digitales como parte esencial de su funcionalidad. En este tema se describe métodos para la recopilación de tinta en Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Requisitos previos

Para usar los ejemplos siguientes, debe instalar primero Visual Studio y el [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. También debe entender cómo escribir aplicaciones para WPF. Para obtener más información acerca de la introducción a WPF, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Utilice el elemento InkCanvas

El <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento proporciona la manera más fácil de recopilar entradas de lápiz en WPF. Use un <xref:System.Windows.Controls.InkCanvas> elemento para recibir y mostrar entradas de lápiz. Normalmente, la entrada de lápiz se realiza con un lápiz, que interactúa con un digitalizador para generar trazos de lápiz. También se puede usar un mouse en lugar de un lápiz. Los trazos creados se representan como <xref:System.Windows.Ink.Stroke> objetos y se pueden manipular mediante programación y por el usuario de entrada. El <xref:System.Windows.Controls.InkCanvas> permite a los usuarios seleccionar, modificar o eliminar una existente <xref:System.Windows.Ink.Stroke>.

Mediante el uso de XAML, puede configurar la recopilación de tinta tan fácilmente como agregar un **InkCanvas** elemento al árbol. En el ejemplo siguiente se agrega un <xref:System.Windows.Controls.InkCanvas> a un proyecto WPF predeterminado creado en Visual Studio:

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

El **InkCanvas** elemento también puede contener elementos secundarios, lo que permite agregar funcionalidades de anotación de tinta a casi cualquier tipo de elemento XAML. Por ejemplo, para agregar capacidades de tinta a un elemento de texto, simplemente convertirlo en un elemento secundario de un <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Agregar compatibilidad para marcar una imagen con tinta es igual de fácil:

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Modos de InkCollection

El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con varios modos a través de la entrada su <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> propiedad.

### <a name="manipulate-ink"></a>Manipular entradas de lápiz

El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con muchas operaciones de edición de tinta. Por ejemplo, <xref:System.Windows.Controls.InkCanvas> borrar admite back del lápiz, y no es necesario ningún código adicional para agregar la funcionalidad para el elemento.

#### <a name="selection"></a>Selección

Establecer el modo de selección es tan sencillo como la configuración de la <xref:System.Windows.Controls.InkCanvasEditingMode> propiedad **seleccione**.

El código siguiente establece el modo de edición en función del valor de un <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Use el <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad para cambiar la apariencia de los trazos de tinta. Por ejemplo, el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> miembro de <xref:System.Windows.Ink.DrawingAttributes> establece el color de la representado <xref:System.Windows.Ink.Stroke>.

El ejemplo siguiente cambia el color de los trazos seleccionados a rojo:

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

El <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad proporciona acceso a propiedades como el alto, ancho y color de los trazos que se creará en un <xref:System.Windows.Controls.InkCanvas>. Una vez que cambie el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros que se celebra el <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.

Además de modificar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede usar sintaxis XAML para especificar <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades.

En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> propiedad. Para usar este código, cree un nuevo proyecto WPF denominado "HelloInkCanvas" en Visual Studio. Reemplace el código en el *MainWindow.xaml* archivo con el código siguiente:

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

A continuación, agregue los siguientes controladores de eventos de botón en el archivo de código subyacente, dentro de la clase MainWindow:

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Después de copiar este código, presione **F5** en Visual Studio para ejecutar el programa en el depurador.

Observe cómo el <xref:System.Windows.Controls.StackPanel> coloca los botones en la parte superior de la <xref:System.Windows.Controls.InkCanvas>. Si trata de entrada de lápiz encima de los botones, el <xref:System.Windows.Controls.InkCanvas> recopila y procesa la entrada de lápiz detrás de los botones. Esto es porque los botones están relacionados con el <xref:System.Windows.Controls.InkCanvas> en lugar de los elementos secundarios. Además, los botones son superiores en el orden de z, por lo que la entrada de lápiz se representa detrás de ellos.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>