---
title: Personalizar la representación de la entrada manuscrita
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111834"
---
# <a name="custom-rendering-ink"></a>Personalizar la representación de la entrada manuscrita
La <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad de un trazo permite especificar la apariencia de un trazo, como su tamaño, color y forma, <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> pero puede haber ocasiones en las que desee personalizar la apariencia más allá de lo permitido. Si quiere personalizar la apariencia de la entrada de lápiz, la puede representar como un aerógrafo, pintura al óleo y muchos otros efectos. Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) <xref:System.Windows.Ink.Stroke> permite representar la tinta personalizada mediante la implementación de un objeto y personalizado. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Arquitectura](#Architecture)  
  
- [Implementación de un representador dinámico](#ImplementingADynamicRenderer)  
  
- [Implementación de trazos personalizados](#ImplementingCustomStrokes)  
  
- [Implementación de un objeto InkCanvas personalizado](#ImplementingACustomInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 La representación de la entrada de lápiz se produce dos veces: cuando un usuario escribe con el lápiz en una superficie de entrada de lápiz y, de nuevo, cuando el trazo se agrega a la superficie habilitada para la entrada de lápiz. Representa <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la tinta cuando el usuario mueve el lápiz <xref:System.Windows.Ink.Stroke> de tableta en el digitalizador y el se representa a sí mismo una vez que se agrega a un elemento.  
  
 Existen tres clases que se implementan al representar la entrada de lápiz de forma dinámica.  
  
1. **DynamicRenderer**: Implementar una clase <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>que deriva de . Esta clase es <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> una especializada que representa el trazo a medida que se dibuja. Hace <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la representación en un subproceso independiente, por lo que la superficie de entrada manuscrita parece recopilar tinta incluso cuando se bloquea el subproceso de interfaz de usuario (UI) de la aplicación. Para obtener más información sobre el modelo de subprocesos, consulte [Modelo de subprocesamiento de entrada manuscrita](the-ink-threading-model.md). Para personalizar la representación dinámica <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> de un trazo, invalide el método.  
  
2. **Stroke**: Implementar una clase <xref:System.Windows.Ink.Stroke>que deriva de . Esta clase es responsable de <xref:System.Windows.Input.StylusPoint> la representación estática <xref:System.Windows.Ink.Stroke> de los datos después de que se han convertido en un objeto. Invalide <xref:System.Windows.Ink.Stroke.DrawCore%2A> el método para asegurarse de que la representación estática del trazo es coherente con la representación dinámica.  
  
3. **InkCanvas:** Implemente una clase que <xref:System.Windows.Controls.InkCanvas>derive de . Asigne el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> a la propiedad. Invalide <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> el método y agregue <xref:System.Windows.Controls.InkCanvas.Strokes%2A> un trazo personalizado a la propiedad. Esto garantiza que la apariencia de la entrada de lápiz sea coherente.  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>Implementación de un representador dinámico  
 Aunque <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la clase es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]una parte estándar de , para realizar una representación más <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> especializada, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> debe crear un representador dinámico personalizado que se derive del método y reemplazarlo.  
  
 En el ejemplo siguiente <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> se muestra un personalizado que dibuja tinta con un efecto de pincel de degradado lineal.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>Implementación de trazos personalizados  
 Implemente una clase derivada de <xref:System.Windows.Ink.Stroke>. Esta clase es <xref:System.Windows.Input.StylusPoint> responsable de representar los <xref:System.Windows.Ink.Stroke> datos después de que se han convertido en un objeto. Invalide <xref:System.Windows.Ink.Stroke.DrawCore%2A> la clase para realizar el dibujo real.  
  
 La clase Stroke también puede almacenar <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> datos personalizados mediante el método. Estos datos se almacenan con los datos del trazo cuando se conservan.  
  
 La <xref:System.Windows.Ink.Stroke> clase también puede realizar pruebas de posicionación. También puede implementar su propio algoritmo de <xref:System.Windows.Ink.Stroke.HitTest%2A> prueba de posicionamiento reemplazando el método en la clase actual.  
  
 En el siguiente código de <xref:System.Windows.Ink.Stroke> Cá se <xref:System.Windows.Input.StylusPoint> muestra una clase personalizada que representa los datos como un trazo 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>Implementación de un objeto InkCanvas personalizado  
 La forma más fácil <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> de usar el personalizado y el <xref:System.Windows.Controls.InkCanvas> trazo es implementar una clase que deriva y usa estas clases. Tiene <xref:System.Windows.Controls.InkCanvas> una <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad que especifica cómo se representa el trazo cuando el usuario lo está dibujando.  
  
 Para renderizar trazos <xref:System.Windows.Controls.InkCanvas> personalizados en un haga lo siguiente:  
  
- Cree una clase que <xref:System.Windows.Controls.InkCanvas>derive del archivo .  
  
- Asigne su <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> a la propiedad.  
  
- Invalide el método <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> . En este método, quite el trazo original que se agregó al objeto InkCanvas. A continuación, cree un trazo <xref:System.Windows.Controls.InkCanvas.Strokes%2A> personalizado, agréguelo a <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> la propiedad y llame a la clase base con un nuevo que contenga el trazo personalizado.  
  
 En el siguiente código de <xref:System.Windows.Controls.InkCanvas> Cá se <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> muestra una clase personalizada que usa una personalizada y recopila trazos personalizados.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un <xref:System.Windows.Controls.InkCanvas> puede tener <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>más de un archivo . Puede agregar <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> varios objetos a <xref:System.Windows.Controls.InkCanvas> la <xref:System.Windows.UIElement.StylusPlugIns%2A> agregándolos a la propiedad.  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Conclusión  
 Puede personalizar la apariencia de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>tinta <xref:System.Windows.Ink.Stroke>derivando sus propias clases , , y <xref:System.Windows.Controls.InkCanvas> . Juntas, estas clases garantizan que la apariencia del trazo sea coherente cuando el usuario dibuja el trazo y después de su recopilación.  
  
## <a name="see-also"></a>Consulte también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
