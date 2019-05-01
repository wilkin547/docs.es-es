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
ms.openlocfilehash: 5c22c2862ae8b948787fd5e6ca16109aa2f52aef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031257"
---
# <a name="intercepting-input-from-the-stylus"></a>Interceptar entradas del lápiz óptico
El <xref:System.Windows.Input.StylusPlugIns> arquitectura proporciona un mecanismo para implementar el control de bajo nivel a través de <xref:System.Windows.Input.Stylus> de entrada y la creación de la entrada de lápiz digital <xref:System.Windows.Ink.Stroke> objetos. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clase proporciona un mecanismo para implementar un comportamiento personalizado y aplicarlo a la secuencia de datos procedente del dispositivo de lápiz para un rendimiento óptimo.  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Arquitectura](#Architecture)  
  
- [Implementar complementos de lápiz](#ImplementingStylusPlugins)  
  
- [Agregar el complemento a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Arquitectura  
 El <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> es la evolución de la [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) API, se describe en [acceder y manipular entradas manuscritas](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), en el [Software de Microsoft Windows XP Tablet PC Edition Kit de desarrollo 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Cada <xref:System.Windows.UIElement> tiene un <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad que es un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Puede agregar un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a un elemento <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad manipular <xref:System.Windows.Input.StylusPoint> datos a medida que se generan. <xref:System.Windows.Input.StylusPoint> constan de datos de todas las propiedades admitidas por el digitalizador del sistema, incluidos el <xref:System.Windows.Input.StylusPoint.X%2A> y <xref:System.Windows.Input.StylusPoint.Y%2A> punto de datos, así como <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> datos.  
  
 Su <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos se insertan directamente en el flujo de datos procedentes de la <xref:System.Windows.Input.Stylus> dispositivo cuando se agrega el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad. El orden en que se agregan los complementos a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección determina el orden en el que recibirán <xref:System.Windows.Input.StylusPoint> datos. Por ejemplo, si agrega un complemento de filtro que restringe la entrada a una región determinada y, a continuación, agregar un complemento que reconoce los gestos de medida que se escriben, el complemento que reconoce los gestos recibirá filtrados <xref:System.Windows.Input.StylusPoint> datos.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementar complementos de lápiz  
 Para implementar un complemento, derive una clase de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Esta clase es aplica a la secuencia de datos a medida que llegan desde la <xref:System.Windows.Input.Stylus>. En esta clase se pueden modificar los valores de la <xref:System.Windows.Input.StylusPoint> datos.  
  
> [!CAUTION]
>  Si un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> inicia o produce una excepción, la aplicación que se cerrará. Debe probar exhaustivamente los controles que consumen un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y solo puede utilizar un control si está seguro de que el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> no se iniciará una excepción.  
  
 En el ejemplo siguiente se muestra un complemento que restringe la entrada de lápiz óptico modificando el <xref:System.Windows.Input.StylusPoint.X%2A> y <xref:System.Windows.Input.StylusPoint.Y%2A> valores en el <xref:System.Windows.Input.StylusPoint> datos a medida que proceden la <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Agregar el complemento a un InkCanvas  
 Es la manera más fácil de utilizar un complemento personalizado implementar una clase que derive de InkCanvas y agregarla a la <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad.  
  
 En el ejemplo siguiente se muestra un personalizado <xref:System.Windows.Controls.InkCanvas> que filtra la entrada de lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Si agrega un `FilterInkCanvas` a su aplicación y la ejecución, observará que la entrada de lápiz no se restringen a una región hasta después de que el usuario completa un trazo. Esto es porque el <xref:System.Windows.Controls.InkCanvas> tiene un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> propiedad, que es un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y ya es miembro de la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección. Personalizado <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> que ha agregado a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección recibe el <xref:System.Windows.Input.StylusPoint> datos después de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> recibe los datos. Como resultado, el <xref:System.Windows.Input.StylusPoint> datos no se filtrarán hasta después de que el usuario levanta el lápiz para finalizar un trazo. Para filtrar la entrada de lápiz como el usuario lo dibuja, debe insertar el `FilterPlugin` antes de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 El código de C# siguiente muestra un personalizado <xref:System.Windows.Controls.InkCanvas> que filtra la entrada de lápiz mientras se dibuja.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Al derivar sus propias <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clases e insertándolos en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> colecciones, puede mejorar considerablemente el comportamiento de la entrada de lápiz digital. Tener acceso a la <xref:System.Windows.Input.StylusPoint> datos a medida que se generan, lo que le ofrece la oportunidad de personalizar el <xref:System.Windows.Input.Stylus> entrada. Dado que tienen ese acceso de bajo nivel para el <xref:System.Windows.Input.StylusPoint> datos, puede implementar la recopilación de tinta y la representación con un rendimiento óptimo de la aplicación.  
  
## <a name="see-also"></a>Vea también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Obtener acceso y manipular la entrada manuscrita](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
