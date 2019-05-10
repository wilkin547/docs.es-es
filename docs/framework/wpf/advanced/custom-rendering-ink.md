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
ms.openlocfilehash: 9a62a16f4fa16cfe40bbf830de2255bea25f8d3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611984"
---
# <a name="custom-rendering-ink"></a>Personalizar la representación de la entrada manuscrita
El <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad de un trazo permite especificar la apariencia de un trazo, como su tamaño, color y forma, pero puede haber ocasiones en que desea personalizar el aspecto más allá de lo que <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> permitir. Si quiere personalizar la apariencia de la entrada de lápiz, la puede representar como un aerógrafo, pintura al óleo y muchos otros efectos. Windows Presentation Foundation (WPF) permite la representación personalizada tinta implementando un personalizado <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y <xref:System.Windows.Ink.Stroke> objeto.  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Arquitectura](#Architecture)  
  
- [Implementación de un representador dinámico](#ImplementingADynamicRenderer)  
  
- [Implementación de trazos personalizados](#ImplementingCustomStrokes)  
  
- [Implementación de un objeto InkCanvas personalizado](#ImplementingACustomInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Arquitectura  
 La representación de la entrada de lápiz se produce dos veces: cuando un usuario escribe con el lápiz en una superficie de entrada de lápiz y, de nuevo, cuando el trazo se agrega a la superficie habilitada para la entrada de lápiz. El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> representa la entrada de lápiz cuando el usuario mueve el lápiz de tablet PC del digitalizador y el <xref:System.Windows.Ink.Stroke> representa a sí mismo una vez que se agrega a un elemento.  
  
 Existen tres clases que se implementan al representar la entrada de lápiz de forma dinámica.  
  
1. **DynamicRenderer**: Implemente una clase derivada de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Esta clase es un especializada <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> que representa el trazo a medida que se dibuja. El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> realiza la representación en un subproceso independiente, por lo que aparece la superficie de escritura a mano recopilar entradas de lápiz, incluso cuando se bloquea el subproceso de interfaz de usuario de aplicación. Para obtener más información sobre el modelo de subprocesos, consulte [Modelo de subprocesamiento de entrada manuscrita](the-ink-threading-model.md). Para personalizar la representación dinámica de un trazo, invalide el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> método.  
  
2. **Trazo**: Implemente una clase derivada de <xref:System.Windows.Ink.Stroke>. Esta clase es responsable de la representación estática de la <xref:System.Windows.Input.StylusPoint> datos después de se ha convertido en un <xref:System.Windows.Ink.Stroke> objeto. Invalidar el <xref:System.Windows.Ink.Stroke.DrawCore%2A> al método para asegurar esa representación estática del trazo sea coherente con la representación dinámica.  
  
3. **InkCanvas:** Implemente una clase derivada de <xref:System.Windows.Controls.InkCanvas>. Asignar personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad. Invalidar el <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> método y agregue un trazo personalizado a la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad. Esto garantiza que la apariencia de la entrada de lápiz sea coherente.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementación de un representador dinámico  
 Aunque el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> clase es una parte estándar de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]realizar más especializados de representación, debe crear un representador dinámico personalizado que se deriva el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e invalidar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> método.  
  
 En el ejemplo siguiente se muestra una personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> que dibuja con el lápiz con un efecto de pincel de degradado lineal.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementación de trazos personalizados  
 Implemente una clase derivada de <xref:System.Windows.Ink.Stroke>. Esta clase es responsable de representar <xref:System.Windows.Input.StylusPoint> datos después de se ha convertido en un <xref:System.Windows.Ink.Stroke> objeto. Invalidar el <xref:System.Windows.Ink.Stroke.DrawCore%2A> clase para realizar el dibujo real.  
  
 La clase Stroke también puede almacenar datos personalizados mediante el uso de la <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> método. Estos datos se almacenan con los datos del trazo cuando se conservan.  
  
 La <xref:System.Windows.Ink.Stroke> clase también puede realizar la prueba de posicionamiento. También puede implementar su propia prueba algoritmo mediante la invalidación de posicionamiento del <xref:System.Windows.Ink.Stroke.HitTest%2A> método en la clase actual.  
  
 La siguiente C# código muestra un personalizado <xref:System.Windows.Ink.Stroke> clase que representa <xref:System.Windows.Input.StylusPoint> datos como un trazo 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementación de un objeto InkCanvas personalizado  
 La manera más fácil de usar su personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y trazo es implementar una clase que derive de <xref:System.Windows.Controls.InkCanvas> y usa estas clases. El <xref:System.Windows.Controls.InkCanvas> tiene un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad que especifica cómo se representa el trazo cuando el usuario lo dibuja.  
  
 Para personalizar la representación trazos en un <xref:System.Windows.Controls.InkCanvas> haga lo siguiente:  
  
- Cree una clase que deriva el <xref:System.Windows.Controls.InkCanvas>.  
  
- Asignar su personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> propiedad.  
  
- Invalide el método <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> . En este método, quite el trazo original que se agregó al objeto InkCanvas. A continuación, cree un trazo personalizado, agréguelo a la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad y llame a la clase base con un nuevo <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> que contenga el trazo personalizado.  
  
 La siguiente C# código muestra un personalizado <xref:System.Windows.Controls.InkCanvas> clase que usa una personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y recopila los trazos personalizados.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un <xref:System.Windows.Controls.InkCanvas> puede tener más de un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Puede agregar varios <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objetos a la <xref:System.Windows.Controls.InkCanvas> agregándolos a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Puede personalizar la apariencia de la entrada de lápiz, derive su propia <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, y <xref:System.Windows.Controls.InkCanvas> clases. Juntas, estas clases garantizan que la apariencia del trazo sea coherente cuando el usuario dibuja el trazo y después de su recopilación.  
  
## <a name="see-also"></a>Vea también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
