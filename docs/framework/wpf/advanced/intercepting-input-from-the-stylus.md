---
title: Interceptar entradas del lápiz óptico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 2547c0aa2f3a14080868c2760fa8999eb99d3d16
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046327"
---
# <a name="intercepting-input-from-the-stylus"></a>Interceptar entradas del lápiz óptico
La <xref:System.Windows.Input.StylusPlugIns> arquitectura proporciona un mecanismo para implementar el control de bajo nivel <xref:System.Windows.Input.Stylus> sobre la entrada y la creación de <xref:System.Windows.Ink.Stroke> objetos de entrada de lápiz digital. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clase proporciona un mecanismo para implementar el comportamiento personalizado y aplicarlo a la secuencia de datos procedentes del dispositivo de lápiz para obtener el rendimiento óptimo.  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Arquitectura](#Architecture)  
  
- [Implementar complementos de lápiz óptico](#ImplementingStylusPlugins)  
  
- [Agregar el complemento a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Arquitectura  
 Es la evolución de las API de [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) , que se describen en [obtener acceso a la entrada de lápiz y manipularla](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), en el [Kit de desarrollo de software 1,7 de Microsoft Windows XP Tablet PC Edition.](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409) <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>  
  
 Cada <xref:System.Windows.UIElement> tiene una <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad que es un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Puede agregar <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la propiedad de <xref:System.Windows.UIElement.StylusPlugIns%2A> un elemento para manipular <xref:System.Windows.Input.StylusPoint> los datos a medida que se generan. <xref:System.Windows.Input.StylusPoint>los datos se componen de todas las propiedades que admite el digitalizador <xref:System.Windows.Input.StylusPoint.X%2A> del <xref:System.Windows.Input.StylusPoint.Y%2A> sistema, incluidos los datos de <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> los puntos y, así como los datos.  
  
 Los <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos se insertan directamente en el flujo de datos procedente <xref:System.Windows.Input.Stylus> del <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> dispositivo al agregar a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad. El orden en que se agregan los complementos a <xref:System.Windows.UIElement.StylusPlugIns%2A> la colección determina el orden en que recibirán <xref:System.Windows.Input.StylusPoint> los datos. Por ejemplo, si agrega un complemento de filtro que restringe la entrada a una región determinada y, a continuación, agrega un complemento que reconoce los gestos a medida que se escriben, el complemento que reconoce los gestos recibirá <xref:System.Windows.Input.StylusPoint> datos filtrados.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementar complementos de lápiz óptico  
 Para implementar un complemento, derive una clase de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Esta clase se aplica o el flujo de datos tal y como entra en <xref:System.Windows.Input.Stylus>. En esta clase, puede modificar los valores de los <xref:System.Windows.Input.StylusPoint> datos.  
  
> [!CAUTION]
> Si se <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> produce una excepción o se produce una excepción, la aplicación se cerrará. Debe probar exhaustivamente los controles que consumen <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y solo usar un control si está seguro de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> que no producirá una excepción.  
  
 En el ejemplo siguiente se muestra un complemento que restringe la entrada del lápiz óptico modificando <xref:System.Windows.Input.StylusPoint.X%2A> los <xref:System.Windows.Input.StylusPoint.Y%2A> valores y de <xref:System.Windows.Input.StylusPoint> los datos a medida que entran <xref:System.Windows.Input.Stylus> en el dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Agregar el complemento a un InkCanvas  
 La forma más fácil de usar el complemento personalizado es implementar una clase que derive de InkCanvas y agregarlo a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad.  
  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.InkCanvas> un personalizado que filtra la tinta.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Si agrega un `FilterInkCanvas` a la aplicación y lo ejecuta, observará que la tinta no está restringida a una región hasta que el usuario completa un trazo. <xref:System.Windows.Controls.InkCanvas> Esto se debe a que tiene <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> una propiedad, que es <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> un y ya es un miembro de <xref:System.Windows.UIElement.StylusPlugIns%2A> la colección. El personalizado <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> que ha agregado a <xref:System.Windows.UIElement.StylusPlugIns%2A> la colección recibe <xref:System.Windows.Input.StylusPoint> los datos <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> después de recibir los datos. Como resultado, los <xref:System.Windows.Input.StylusPoint> datos no se filtrarán hasta que el usuario Levante el lápiz para finalizar un trazo. Para filtrar la entrada de lápiz cuando el usuario la dibuja, debe `FilterPlugin` insertar antes <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>de la.  
  
 En el C# código siguiente se muestra <xref:System.Windows.Controls.InkCanvas> un personalizado que filtra la tinta a medida que se dibuja.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Al derivar sus propias <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clases e insertarlas en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> colecciones, puede mejorar considerablemente el comportamiento de la tinta digital. Tiene acceso a los <xref:System.Windows.Input.StylusPoint> datos a medida que se generan, lo que le proporciona la oportunidad de personalizar la <xref:System.Windows.Input.Stylus> entrada. Dado que tiene acceso de bajo nivel a los datos <xref:System.Windows.Input.StylusPoint> , puede implementar la recopilación y representación de entradas manuscritas con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Vea también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Obtener acceso y manipular entradas manuscritas](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
