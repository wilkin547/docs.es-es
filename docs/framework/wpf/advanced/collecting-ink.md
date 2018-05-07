---
title: Recopilación de entradas manuscritas
ms.date: 03/30/2017
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
ms.openlocfilehash: d441f606a577a2c0506a0f9ae510b3ea1045bba9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="collecting-ink"></a>Recopilación de entradas manuscritas
La plataforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) recopila entradas de lápiz digitales como parte esencial de su funcionalidad. Este tema describe los métodos para la recopilación de tinta en Windows Presentation Foundation (WPF).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para usar los siguientes ejemplos, debe instalar primero [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] y [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. También debe saber cómo escribir aplicaciones para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información acerca de cómo empezar a usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="using-the-inkcanvas-element"></a>Uso del elemento InkCanvas  
 El <xref:System.Windows.Controls.InkCanvas> elemento proporciona la manera más fácil de recopilar entradas manuscritas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El <xref:System.Windows.Controls.InkCanvas> elemento es similar a la [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) objeto desde el [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] y versiones anteriores.  
  
 Use un <xref:System.Windows.Controls.InkCanvas> elemento para recibir y mostrar entradas de lápiz. Normalmente, la entrada de lápiz se realiza con un lápiz, que interactúa con un digitalizador para generar trazos de lápiz. También se puede usar un mouse en lugar de un lápiz. Los trazos creados se representan como <xref:System.Windows.Ink.Stroke> objetos y se pueden manipular mediante programación y usuario de entrada. El <xref:System.Windows.Controls.InkCanvas> permite a los usuarios seleccionar, modificar o eliminar una existente <xref:System.Windows.Ink.Stroke>.  
  
 XAML permite configurar la recopilación de entrada de lápiz fácilmente: solo tiene que agregar un elemento `InkCanvas` al árbol. En el ejemplo siguiente se agrega un <xref:System.Windows.Controls.InkCanvas> a un valor predeterminado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proyecto creado en [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 El elemento `InkCanvas` también puede contener elementos secundarios, lo que permite agregar funcionalidades de anotación de entrada de lápiz a casi cualquier tipo de elemento XAML. Por ejemplo, para agregar capacidades de escritura a mano a un elemento de texto, simplemente hará que sea un elemento secundario de un <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Agregar compatibilidad para marcar una imagen con entrada de lápiz es así de fácil.  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>Modos de InkCollection  
 El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad para varios modos a través de entrada su <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> propiedad.  
  
### <a name="manipulating-ink"></a>Manipulación de la entrada de lápiz  
 El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad para muchas operaciones de edición de tinta. Por ejemplo, <xref:System.Windows.Controls.InkCanvas> es compatible con copia de la punta borrar con ningún código adicional necesario para agregar la funcionalidad para el elemento.  
  
#### <a name="selection"></a>Selección  
 Establecer el modo de selección es tan sencillo como configuración de la <xref:System.Windows.Controls.InkCanvasEditingMode> propiedad **seleccione**. El código siguiente establece el modo de edición en función del valor de un <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 Use la <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad para cambiar la apariencia de los trazos de tinta. Por ejemplo, el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> miembro de <xref:System.Windows.Ink.DrawingAttributes> establece el color de la representado <xref:System.Windows.Ink.Stroke>. En el ejemplo siguiente se cambia el color de los trazos seleccionados a rojo.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 El <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad proporciona acceso a propiedades, como el alto, ancho y color de los trazos que se creen en un <xref:System.Windows.Controls.InkCanvas>. Una vez que cambie la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros especificados en el <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.  
  
 Además de modificar la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede usar la sintaxis de XAML para especificar <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades. El siguiente código XAML muestra cómo establecer el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> propiedad. Para usar este código, cree un nuevo proyecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominado "HelloInkCanvas" en Visual Studio 2005. Reemplace el código del archivo Window1.xaml por el código siguiente.  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 A continuación, agregue los siguientes controladores de eventos de botón en el archivo de código subyacente, dentro de la clase Window1.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 Después de copiar este código, presione **F5** en Microsoft Visual Studio 2005 para ejecutar el programa en el depurador.  
  
 Observe cómo la <xref:System.Windows.Controls.StackPanel> coloca los botones en la parte superior de la <xref:System.Windows.Controls.InkCanvas>. Si trata de tinta sobre la parte superior de los botones, el <xref:System.Windows.Controls.InkCanvas> recopila y presenta la tinta detrás de los botones. Esto es porque los botones están relacionados con el <xref:System.Windows.Controls.InkCanvas> en lugar de los elementos secundarios. Además, los botones son superiores en el orden de z, por lo que la entrada de lápiz se representa detrás de ellos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
