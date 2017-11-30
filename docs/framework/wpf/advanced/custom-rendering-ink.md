---
title: "Personalizar la representación de la entrada manuscrita"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90d2ab68f76bef8d8f437a7dd6096011889303fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="custom-rendering-ink"></a>Personalizar la representación de la entrada manuscrita
El <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad de un trazo permite especificar la apariencia de un trazo, como su tamaño, color y forma, pero puede haber ocasiones en que se desea personalizar el aspecto más allá de lo que <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> permitir. Si quiere personalizar la apariencia de la entrada de lápiz, la puede representar como un aerógrafo, pintura al óleo y muchos otros efectos. El [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] permite personalizar representa tinta implementando un personalizado <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y <xref:System.Windows.Ink.Stroke> objeto.  
  
 Este tema contiene las siguientes subsecciones:  
  
-   [Arquitectura](#Architecture)  
  
-   [Implementación de un representador dinámico](#ImplementingADynamicRenderer)  
  
-   [Implementación de trazos personalizados](#ImplementingCustomStrokes)  
  
-   [Implementación de un objeto InkCanvas personalizado](#ImplementingACustomInkCanvas)  
  
-   [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Arquitectura  
 La representación de la entrada de lápiz se produce dos veces: cuando un usuario escribe con el lápiz en una superficie de entrada de lápiz y, de nuevo, cuando el trazo se agrega a la superficie habilitada para la entrada de lápiz. El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la tinta se representa cuando el usuario mueve el lápiz de tablet PC sobre el digitalizador y <xref:System.Windows.Ink.Stroke> representa a sí misma una vez que se agrega a un elemento.  
  
 Existen tres clases que se implementan al representar la entrada de lápiz de forma dinámica.  
  
1.  **DynamicRenderer**: implementar una clase que deriva de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Esta clase es un especializado <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> que representa el trazo a medida que se dibuja. El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> realiza el procesamiento en un subproceso independiente, por lo que muestra la superficie de escritura a mano recopilar tinta incluso cuando se bloquea el subproceso de interfaz de usuario de aplicación. Para obtener más información sobre el modelo de subprocesos, consulte [Modelo de subprocesamiento de entrada manuscrita](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md). Para personalizar la representación dinámica de un trazo, invalide el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> método.  
  
2.  **Trazo**: implementar una clase que deriva de <xref:System.Windows.Ink.Stroke>. Esta clase es responsable de la representación estática de la <xref:System.Windows.Input.StylusPoint> datos después de que se ha convertido en un <xref:System.Windows.Ink.Stroke> objeto. Invalidar el <xref:System.Windows.Ink.Stroke.DrawCore%2A> método para asegurarse de esa representación estática del trazo es coherente con la representación dinámica.  
  
3.  **InkCanvas:** implementar una clase que deriva de <xref:System.Windows.Controls.InkCanvas>. Asignar la personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad. Invalidar el <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> método y agregue un trazo personalizado a la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad. Esto garantiza que la apariencia de la entrada de lápiz sea coherente.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementación de un representador dinámico  
 Aunque la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> clase es una parte estándar de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]realizar más especializado de representación, debe crear un representador dinámico personalizado que deriva de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e invalide el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> método.  
  
 En el ejemplo siguiente se muestra una personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> que dibuja tinta con un efecto de pincel de degradado lineal.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementación de trazos personalizados  
 Implemente una clase derivada de <xref:System.Windows.Ink.Stroke>. Esta clase es responsable de la representación <xref:System.Windows.Input.StylusPoint> datos después de que se ha convertido en un <xref:System.Windows.Ink.Stroke> objeto. Invalidar el <xref:System.Windows.Ink.Stroke.DrawCore%2A> clase para realizar el dibujo real.  
  
 Su clase Stroke también puede almacenar datos personalizados mediante el uso de la <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> método. Estos datos se almacenan con los datos del trazo cuando se conservan.  
  
 La <xref:System.Windows.Ink.Stroke> clase también puede realizar la prueba de posicionamiento. También puede implementar su propia prueba algoritmo mediante la invalidación de posicionamiento del <xref:System.Windows.Ink.Stroke.HitTest%2A> método en la clase actual.  
  
 El código de C# siguiente muestra un personalizado <xref:System.Windows.Ink.Stroke> clase que representa <xref:System.Windows.Input.StylusPoint> datos como un trazo 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementación de un objeto InkCanvas personalizado  
 La manera más fácil de usar su personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y trazo consiste en implementar una clase que deriva de <xref:System.Windows.Controls.InkCanvas> y usa estas clases. El <xref:System.Windows.Controls.InkCanvas> tiene un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad que especifica cómo se representa el trazo cuando el usuario lo está dibujando.  
  
 Para personalizar la representación trazos en un <xref:System.Windows.Controls.InkCanvas> haga lo siguiente:  
  
-   Cree una clase que deriva de la <xref:System.Windows.Controls.InkCanvas>.  
  
-   Asignar su personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> propiedad.  
  
-   Invalide el método <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>. En este método, quite el trazo original que se agregó al objeto InkCanvas. A continuación, cree un trazo personalizado, agréguelo a la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> propiedad y llame a la clase base con un nuevo <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> que contenga el trazo personalizado.  
  
 El código de C# siguiente muestra un personalizado <xref:System.Windows.Controls.InkCanvas> clase que utiliza un personalizada <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y recopila los trazos personalizados.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un <xref:System.Windows.Controls.InkCanvas> puede tener más de un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Puede agregar varias <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objetos a la <xref:System.Windows.Controls.InkCanvas> agregándolos a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Puede personalizar la apariencia de la tinta, derive su propia <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, y <xref:System.Windows.Controls.InkCanvas> clases. Juntas, estas clases garantizan que la apariencia del trazo sea coherente cuando el usuario dibuja el trazo y después de su recopilación.  
  
## <a name="see-also"></a>Vea también  
 [Control avanzado de entrada manuscrita](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)
