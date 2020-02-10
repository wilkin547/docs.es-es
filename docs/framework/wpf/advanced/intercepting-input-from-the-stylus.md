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
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095143"
---
# <a name="intercepting-input-from-the-stylus"></a>Interceptar entradas del lápiz óptico
La arquitectura de <xref:System.Windows.Input.StylusPlugIns> proporciona un mecanismo para implementar el control de bajo nivel sobre <xref:System.Windows.Input.Stylus> entrada y la creación de objetos <xref:System.Windows.Ink.Stroke> de entrada de lápiz digital. La clase <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> proporciona un mecanismo para implementar el comportamiento personalizado y aplicarlo a la secuencia de datos procedentes del dispositivo de lápiz para obtener el rendimiento óptimo.  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Architecture](#Architecture)  
  
- [Implementar complementos de lápiz óptico](#ImplementingStylusPlugins)  
  
- [Agregar el complemento a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architecture  
 El <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> es la evolución de las API de [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) , que se describe en [obtener acceso y manipular entradas manuscritas](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10)).  
  
 Cada <xref:System.Windows.UIElement> tiene una propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A> que es <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. Puede Agregar un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A> de un elemento para manipular los datos de <xref:System.Windows.Input.StylusPoint> a medida que se generan. <xref:System.Windows.Input.StylusPoint> datos constan de todas las propiedades que admite el digitalizador del sistema, incluidos los datos de los <xref:System.Windows.Input.StylusPoint.X%2A> y del punto de <xref:System.Windows.Input.StylusPoint.Y%2A>, así como los datos de <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>.  
  
 Los objetos de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> se insertan directamente en el flujo de datos procedente del dispositivo <xref:System.Windows.Input.Stylus> al agregar el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>. El orden en que se agregan los complementos a la colección de <xref:System.Windows.UIElement.StylusPlugIns%2A> dicta el orden en que recibirán <xref:System.Windows.Input.StylusPoint> datos. Por ejemplo, si agrega un complemento de filtro que restringe la entrada a una región determinada y, a continuación, agrega un complemento que reconoce los gestos a medida que se escriben, el complemento que reconoce los gestos recibirá datos de <xref:System.Windows.Input.StylusPoint> filtrados.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementar complementos de lápiz óptico  
 Para implementar un complemento, derive una clase de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Esta clase se aplica o el flujo de datos tal como entra en el <xref:System.Windows.Input.Stylus>. En esta clase, puede modificar los valores de los datos de <xref:System.Windows.Input.StylusPoint>.  
  
> [!CAUTION]
> Si una <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> inicia o produce una excepción, la aplicación se cerrará. Debe probar exhaustivamente los controles que consumen una <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y utilizar solo un control si está seguro de que el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> no producirá una excepción.  
  
 En el ejemplo siguiente se muestra un complemento que restringe la entrada del lápiz óptico modificando los valores de <xref:System.Windows.Input.StylusPoint.X%2A> y <xref:System.Windows.Input.StylusPoint.Y%2A> en los datos de <xref:System.Windows.Input.StylusPoint> a medida que se incluyen en el dispositivo de <xref:System.Windows.Input.Stylus>.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Agregar el complemento a un InkCanvas  
 La forma más fácil de usar el complemento personalizado es implementar una clase que derive de InkCanvas y agregarlo a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.InkCanvas> personalizado que filtra la tinta.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Si agrega una `FilterInkCanvas` a la aplicación y la ejecuta, observará que la tinta no está restringida a una región hasta que el usuario completa un trazo. Esto se debe a que el <xref:System.Windows.Controls.InkCanvas> tiene una propiedad <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, que es un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y ya es miembro de la colección de <xref:System.Windows.UIElement.StylusPlugIns%2A>. El <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizado que agregó a la colección de <xref:System.Windows.UIElement.StylusPlugIns%2A> recibe los datos de <xref:System.Windows.Input.StylusPoint> después de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> reciba los datos. Como resultado, los datos de <xref:System.Windows.Input.StylusPoint> no se filtrarán hasta que el usuario Levante el lápiz para finalizar un trazo. Para filtrar la entrada de lápiz a medida que el usuario la dibuja, debe insertar el `FilterPlugin` antes que el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 En el C# código siguiente se muestra un <xref:System.Windows.Controls.InkCanvas> personalizado que filtra la tinta a medida que se dibuja.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Al derivar sus propias clases de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e insertarlas en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> colecciones, puede mejorar considerablemente el comportamiento de la tinta digital. Tiene acceso a los datos de <xref:System.Windows.Input.StylusPoint> a medida que se generan, lo que le proporciona la oportunidad de personalizar la entrada <xref:System.Windows.Input.Stylus>. Dado que tiene acceso de bajo nivel a los datos de <xref:System.Windows.Input.StylusPoint>, puede implementar la recopilación y representación de entradas manuscritas con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Obtener acceso y manipular entradas manuscritas](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
