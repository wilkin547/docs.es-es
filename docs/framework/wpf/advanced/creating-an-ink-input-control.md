---
title: Creación de un control de entrada manuscrita
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186294"
---
# <a name="creating-an-ink-input-control"></a>Creación de un control de entrada manuscrita
Puede crear un control personalizado que represente dinámica y estáticamente la tinta. Es decir, renderizar tinta a medida que un usuario dibuja un trazo, haciendo que la tinta parezca "fluir" desde el lápiz de la tableta, y mostrar la tinta después de que se agrega al control, ya sea a través del lápiz de la tableta, pegado desde el Portapapeles o cargado desde un archivo. Para representar dinámicamente la tinta, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>el control debe usar un archivo . Para representar estáticamente la tinta, debe reemplazar<xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnStylusMove%2A>los <xref:System.Windows.UIElement.OnStylusUp%2A>métodos <xref:System.Windows.Input.StylusPoint> de evento de lápiz ( <xref:System.Windows.Controls.InkPresenter> , , y ) para recopilar datos, crear trazos y agregarlos a un (que representa la tinta en el control).  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Cómo: Recopilar datos de punto de lápiz y crear trazos de tinta](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Cómo: Habilite su control para aceptar la entrada desde el ratón](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Reunión de todo](#PuttingItTogether)  
  
- [Uso de complementos adicionales y DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Conclusión](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Cómo: Recopilar datos de punto de lápiz y crear trazos de tinta  
 Para crear un control que recopile y administre trazos de tinta, haga lo siguiente:  
  
1. Derive una <xref:System.Windows.Controls.Control> clase de o una <xref:System.Windows.Controls.Control>de las <xref:System.Windows.Controls.Label>clases derivadas de , como .  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Agregue <xref:System.Windows.Controls.InkPresenter> un a la <xref:System.Windows.Controls.ContentControl.Content%2A> clase y <xref:System.Windows.Controls.InkPresenter>establezca la propiedad en el nuevo archivo .  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Adjunte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> de <xref:System.Windows.Controls.InkPresenter> la a <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> la mediante <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> una <xref:System.Windows.UIElement.StylusPlugIns%2A> llamada al método y agregue el a la colección. Esto permite <xref:System.Windows.Controls.InkPresenter> mostrar la tinta a medida que el control recopila los datos del punto del lápiz.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Invalide el método <xref:System.Windows.UIElement.OnStylusDown%2A> .  En este método, capture el <xref:System.Windows.Input.Stylus.Capture%2A>lápiz óptico con una llamada a . Al capturar el lápiz, el control <xref:System.Windows.UIElement.StylusMove> <xref:System.Windows.UIElement.StylusUp> seguirá recibiendo y se producirán eventos incluso si el lápiz deja los límites del control. Esto no es estrictamente obligatorio, pero casi siempre se desea para una buena experiencia de usuario. Cree un <xref:System.Windows.Input.StylusPointCollection> nuevo <xref:System.Windows.Input.StylusPoint> para recopilar datos. Por último, agregue <xref:System.Windows.Input.StylusPoint> el conjunto <xref:System.Windows.Input.StylusPointCollection>inicial de datos al archivo .  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Invalide <xref:System.Windows.UIElement.OnStylusMove%2A> el método <xref:System.Windows.Input.StylusPoint> y <xref:System.Windows.Input.StylusPointCollection> agregue los datos al objeto que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Invalide <xref:System.Windows.UIElement.OnStylusUp%2A> el método <xref:System.Windows.Ink.Stroke> y <xref:System.Windows.Input.StylusPointCollection> cree uno nuevo con los datos. Agregue el <xref:System.Windows.Ink.Stroke> nuevo que <xref:System.Windows.Controls.InkPresenter.Strokes%2A> ha <xref:System.Windows.Controls.InkPresenter> creado a la colección de la captura de lápiz óptico y release.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Cómo: Habilite su control para aceptar la entrada desde el ratón  
 Si agrega el control anterior a la aplicación, lo ejecuta y usa el mouse como dispositivo de entrada, observará que los trazos no se conservan. Para conservar los trazos cuando se utiliza el ratón como dispositivo de entrada, haga lo siguiente:  
  
1. Reemplazar <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> y crear <xref:System.Windows.Input.StylusPointCollection> un nuevo Obtener la posición del mouse <xref:System.Windows.Input.StylusPoint> cuando se produjo <xref:System.Windows.Input.StylusPoint> el <xref:System.Windows.Input.StylusPointCollection>evento y crear un utilizando los datos de punto y agregar el archivo .  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Invalide el método <xref:System.Windows.UIElement.OnMouseMove%2A> . Obtenga la posición del mouse cuando se <xref:System.Windows.Input.StylusPoint> produjo el evento y cree un uso de los datos de punto.  Agregue <xref:System.Windows.Input.StylusPoint> el <xref:System.Windows.Input.StylusPointCollection> objeto que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Invalide el método <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Cree un <xref:System.Windows.Ink.Stroke> nuevo <xref:System.Windows.Input.StylusPointCollection> con los datos <xref:System.Windows.Ink.Stroke> y agregue <xref:System.Windows.Controls.InkPresenter.Strokes%2A> el <xref:System.Windows.Controls.InkPresenter>nuevo que creó a la colección del archivo .  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>Reunión de todo  
 El ejemplo siguiente es un control personalizado que recopila tinta cuando el usuario utiliza el mouse o el lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Uso de complementos adicionales y DynamicRenderers  
 Al igual que InkCanvas, el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> control <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado puede tener objetos personalizados y adicionales. Añádalos a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección. El orden <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> de los <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> objetos en el afecta a la apariencia de la tinta cuando se representa. Supongamos que <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> `dynamicRenderer` tiene un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> `translatePlugin` llamado y un personalizado llamado que compensa la tinta de la pluma de la tableta. Si `translatePlugin` es <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> el <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>primero `dynamicRenderer` en el , y es el segundo, la tinta que "fluye" se compensará a medida que el usuario mueve el lápiz. Si `dynamicRenderer` es el `translatePlugin` primero, y es el segundo, la tinta no se desplazará hasta que el usuario levante la pluma.  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>Conclusión  
 Puede crear un control que recopile y represente la tinta reemplazando los métodos de evento de lápiz. Creando tu propio control, derivando tus propias <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clases, e insertándolas en, <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>puedes implementar prácticamente cualquier comportamiento imaginable con tinta digital. Tiene acceso a <xref:System.Windows.Input.StylusPoint> los datos a medida que se <xref:System.Windows.Input.Stylus> generan, lo que le da la oportunidad de personalizar la entrada y representarla en la pantalla según corresponda para su aplicación. Dado que tiene acceso de <xref:System.Windows.Input.StylusPoint> bajo nivel a los datos, puede implementar la recopilación de tinta y representarla con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Acceso y manipulación de la entrada del lápiz](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
