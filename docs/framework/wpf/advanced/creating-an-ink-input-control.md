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
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095221"
---
# <a name="creating-an-ink-input-control"></a>Creación de un control de entrada manuscrita
Puede crear un control personalizado que represente la tinta de forma dinámica y estática. Es decir, representar la entrada de lápiz como un usuario dibuja un trazo, haciendo que la tinta parezca "fluir" desde el lápiz de Tablet PC y mostrar la tinta después de agregarla al control, ya sea a través del lápiz de Tablet PC, pegado desde el portapapeles o se cargó desde un archivo. Para representar la entrada de lápiz dinámicamente, el control debe usar un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Para representar la entrada de lápiz estáticamente, debe invalidar los métodos de evento de lápiz (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>y <xref:System.Windows.UIElement.OnStylusUp%2A>) para recopilar datos de <xref:System.Windows.Input.StylusPoint>, crear trazos y agregarlos a un <xref:System.Windows.Controls.InkPresenter> (que representa la entrada de lápiz en el control).  
  
 Este tema contiene las siguientes subsecciones:  
  
- [Cómo: recopilar datos de punto de lápiz y crear trazos de lápiz](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Cómo: habilitar el control para aceptar la entrada del mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Reunir](#PuttingItTogether)  
  
- [Uso de complementos adicionales y DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Conclusión](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Cómo: recopilar datos de punto de lápiz y crear trazos de lápiz  
 Para crear un control que recopile y administre los trazos de lápiz, haga lo siguiente:  
  
1. Derive una clase de <xref:System.Windows.Controls.Control> o de una de las clases derivadas de <xref:System.Windows.Controls.Control>, como <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Agregue un <xref:System.Windows.Controls.InkPresenter> a la clase y establezca la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> en el nuevo <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Asocie el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> al <xref:System.Windows.Controls.InkPresenter> llamando al método <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> y agregue la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la colección <xref:System.Windows.UIElement.StylusPlugIns%2A>. Esto permite que el <xref:System.Windows.Controls.InkPresenter> muestre la tinta a medida que el control recopila los datos del punto de lápiz.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Invalide el método <xref:System.Windows.UIElement.OnStylusDown%2A> .  En este método, Capture el lápiz óptico con una llamada a <xref:System.Windows.Input.Stylus.Capture%2A>. Al capturar el lápiz, el control seguirá recibiendo <xref:System.Windows.UIElement.StylusMove> y <xref:System.Windows.UIElement.StylusUp> eventos incluso si el lápiz sale de los límites del control. Esto no es estrictamente obligatorio, pero casi siempre se desea para una buena experiencia del usuario. Cree una nueva <xref:System.Windows.Input.StylusPointCollection> para recopilar datos de <xref:System.Windows.Input.StylusPoint>. Por último, agregue el conjunto inicial de datos de <xref:System.Windows.Input.StylusPoint> al <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Invalide el método <xref:System.Windows.UIElement.OnStylusMove%2A> y agregue los datos de <xref:System.Windows.Input.StylusPoint> al objeto <xref:System.Windows.Input.StylusPointCollection> que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Invalide el método <xref:System.Windows.UIElement.OnStylusUp%2A> y cree un nuevo <xref:System.Windows.Ink.Stroke> con los datos de <xref:System.Windows.Input.StylusPointCollection>. Agregue el nuevo <xref:System.Windows.Ink.Stroke> que ha creado a la colección <xref:System.Windows.Controls.InkPresenter.Strokes%2A> de la <xref:System.Windows.Controls.InkPresenter> y la captura del lápiz de versión.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Cómo: habilitar el control para aceptar la entrada del mouse  
 Si agrega el control anterior a la aplicación, lo ejecuta y usa el mouse como dispositivo de entrada, observará que los trazos no se conservan. Para conservar los trazos cuando se usa el mouse como dispositivo de entrada, haga lo siguiente:  
  
1. Invalide el <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> y cree un nuevo <xref:System.Windows.Input.StylusPointCollection> obtener la posición del mouse cuando se produjo el evento y crear un <xref:System.Windows.Input.StylusPoint> con los datos del punto y agregar el <xref:System.Windows.Input.StylusPoint> al <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Invalide el método <xref:System.Windows.UIElement.OnMouseMove%2A> . Obtiene la posición del mouse cuando se produjo el evento y crea un <xref:System.Windows.Input.StylusPoint> con los datos del punto.  Agregue el <xref:System.Windows.Input.StylusPoint> al objeto <xref:System.Windows.Input.StylusPointCollection> que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Invalide el método <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Cree una nueva <xref:System.Windows.Ink.Stroke> con los datos de <xref:System.Windows.Input.StylusPointCollection> y agregue el nuevo <xref:System.Windows.Ink.Stroke> que creó a la colección de <xref:System.Windows.Controls.InkPresenter.Strokes%2A> del <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Reunir  
 El ejemplo siguiente es un control personalizado que recopila entradas manuscritas cuando el usuario usa el mouse o el lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Uso de complementos adicionales y DynamicRenderers  
 Al igual que el InkCanvas, el control personalizado puede tener <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizados y objetos de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> adicionales. Agréguelos a la colección de <xref:System.Windows.UIElement.StylusPlugIns%2A>. El orden de los objetos <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> en el <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> afecta a la apariencia de la tinta cuando se representa. Supongamos que tiene una <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> llamada `dynamicRenderer` y una <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizada llamada `translatePlugin` que desplaza la tinta desde el lápiz de Tablet PC. Si `translatePlugin` es el primer <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> de la <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>y `dynamicRenderer` es el segundo, la tinta que "fluye" se desplazará cuando el usuario mueva el lápiz. Si `dynamicRenderer` es primero y `translatePlugin` es segundo, la tinta no se desplazará hasta que el usuario Levante el lápiz.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Puede crear un control que recopile y represente la entrada de lápiz invalidando los métodos de evento del lápiz óptico. Al crear su propio control, derivar sus propias clases de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e insertarlos en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, puede implementar prácticamente cualquier comportamiento imaginable con tinta digital. Tiene acceso a los datos de <xref:System.Windows.Input.StylusPoint> a medida que se generan, lo que le proporciona la oportunidad de personalizar <xref:System.Windows.Input.Stylus> entrada y representarlo en la pantalla según sea necesario para la aplicación. Dado que tiene acceso de bajo nivel a los datos de <xref:System.Windows.Input.StylusPoint>, puede implementar la recopilación de entradas manuscritas y presentarla con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Control avanzado de entrada manuscrita](advanced-ink-handling.md)
- [Obtener acceso y manipular entradas manuscritas](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
