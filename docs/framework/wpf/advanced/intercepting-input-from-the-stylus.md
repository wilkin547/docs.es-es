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
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181919"
---
# <a name="intercepting-input-from-the-stylus"></a>Interceptar entradas del lápiz óptico
La <xref:System.Windows.Input.StylusPlugIns> arquitectura proporciona un mecanismo para <xref:System.Windows.Input.Stylus> implementar el control de <xref:System.Windows.Ink.Stroke> bajo nivel sobre la entrada y la creación de objetos de tinta digital. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clase proporciona un mecanismo para implementar un comportamiento personalizado y aplicarlo a la secuencia de datos procedentes del dispositivo de lápiz óptico para obtener un rendimiento óptimo.  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Arquitectura](#Architecture)  
  
- [Implementación de plug-ins Stylus](#ImplementingStylusPlugins)  
  
- [Adición de su plug-in a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 Es <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> la evolución de las API [de StylusInput,](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) descritas en [Acceso y manipulación](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))de la entrada del lápiz .  
  
 Cada <xref:System.Windows.UIElement> uno <xref:System.Windows.UIElement.StylusPlugIns%2A> tiene una <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>propiedad que es un archivo . Puede agregar <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> una <xref:System.Windows.UIElement.StylusPlugIns%2A> propiedad a a <xref:System.Windows.Input.StylusPoint> un elemento para manipular los datos a medida que se generan. <xref:System.Windows.Input.StylusPoint>los datos consisten en todas las propiedades <xref:System.Windows.Input.StylusPoint.X%2A> admitidas por el digitalizador del sistema, incluidos los datos y <xref:System.Windows.Input.StylusPoint.Y%2A> los datos de puntos, así como <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> los datos.  
  
 Los <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos se insertan directamente en <xref:System.Windows.Input.Stylus> el flujo <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> de <xref:System.Windows.UIElement.StylusPlugIns%2A> datos procedentes del dispositivo cuando se agrega la propiedad. El orden en que se agregan <xref:System.Windows.UIElement.StylusPlugIns%2A> los complementos a la colección determina el orden en el que recibirán <xref:System.Windows.Input.StylusPoint> los datos. Por ejemplo, si agrega un complemento de filtro que restringe la entrada a una región determinada y, a continuación, agrega un complemento <xref:System.Windows.Input.StylusPoint> que reconoce los gestos a medida que se escriben, el complemento que reconoce los gestos recibirá datos filtrados.  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>Implementación de plug-ins Stylus  
 Para implementar un complemento, derive <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>una clase de . Esta clase se aplica o el flujo de <xref:System.Windows.Input.Stylus>datos a medida que proviene de la . En esta clase puede modificar <xref:System.Windows.Input.StylusPoint> los valores de los datos.  
  
> [!CAUTION]
> Si <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> un produce o produce una excepción, la aplicación se cerrará. Debe probar a fondo los <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> controles que consumen a y <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> solo usan un control si está seguro de que no producirá una excepción.  
  
 En el ejemplo siguiente se muestra un complemento que <xref:System.Windows.Input.StylusPoint.X%2A> restringe la entrada del lápiz modificando los valores y <xref:System.Windows.Input.StylusPoint.Y%2A> de los <xref:System.Windows.Input.StylusPoint> datos a medida que proceden del <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Adición de su plug-in a un InkCanvas  
 La forma más fácil de usar el complemento personalizado es implementar una clase que <xref:System.Windows.UIElement.StylusPlugIns%2A> deriva de InkCanvas y agregarla a la propiedad.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.InkCanvas> se muestra una personalizada que filtra la entrada manuscrita.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Si agrega `FilterInkCanvas` una a la aplicación y la ejecuta, observará que la tinta no está restringida a una región hasta que el usuario complete un trazo. Esto se <xref:System.Windows.Controls.InkCanvas> debe <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> a que tiene <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> una propiedad, que <xref:System.Windows.UIElement.StylusPlugIns%2A> es un y ya es un miembro de la colección. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizada que <xref:System.Windows.UIElement.StylusPlugIns%2A> agregó a <xref:System.Windows.Input.StylusPoint> la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> colección recibe los datos después de recibir datos. Como resultado, <xref:System.Windows.Input.StylusPoint> los datos no se filtrarán hasta después de que el usuario levante el lápiz para finalizar un trazo. Para filtrar la tinta a medida que el `FilterPlugin` usuario <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>la dibuja, debe insertar el archivo antes del archivo .  
  
 En el siguiente código de <xref:System.Windows.Controls.InkCanvas> C- se muestra una personalizada que filtra la entrada manuscrita a medida que se dibuja.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Conclusión  
 Al derivar sus <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> propias clases <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> e insertarlas en colecciones, puede mejorar en gran medida el comportamiento de su tinta digital. Tiene acceso a <xref:System.Windows.Input.StylusPoint> los datos a medida que se generan, lo que le da la oportunidad de personalizar la <xref:System.Windows.Input.Stylus> entrada. Dado que tiene acceso de <xref:System.Windows.Input.StylusPoint> bajo nivel a los datos, puede implementar la recopilación y representación de tinta con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Acceso y manipulación de la entrada del lápiz](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
