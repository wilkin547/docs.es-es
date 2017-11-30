---
title: "Creación de un control de entrada manuscrita"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cfc6553fe9dd176d2aa557df906141c13a5f425
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-an-ink-input-control"></a>Creación de un control de entrada manuscrita
Puede crear un control personalizado dinámicamente y estáticamente representa la entrada de lápiz. Es decir, tinta se representan como un usuario dibuja un trazo que produce la tinta que aparezca "fluir" del lápiz de tablet PC y mostrar tinta después de se agrega al control, ya sea mediante el lápiz de tablet PC, pegado desde el Portapapeles o cargada desde un archivo. Para representar dinámicamente la tinta, el control debe usar un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Para representar estáticamente tinta, debe invalidar los métodos de evento de lápiz (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, y <xref:System.Windows.UIElement.OnStylusUp%2A>) para recopilar <xref:System.Windows.Input.StylusPoint> datos, crear los trazos y agregarlos a un <xref:System.Windows.Controls.InkPresenter> (que representa la entrada manuscrita en el control).  
  
 Este tema contiene las siguientes subsecciones:  
  
-   [Cómo: recopilar datos de punto de lápiz y crear trazos de tinta](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Cómo: habilitar el Control Aceptar la entrada desde el Mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Colocarlo juntos](#PuttingItTogether)  
  
-   [Uso de complementos adicionales y representadores dinámicos](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Conclusión](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Cómo: recopilar datos de punto de lápiz y crear trazos de tinta  
 Para crear un control que recopila y administra tinta trazos hacer lo siguiente:  
  
1.  Derivar una clase de <xref:System.Windows.Controls.Control> o una de las clases derivadas de <xref:System.Windows.Controls.Control>, como <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Agregar un <xref:System.Windows.Controls.InkPresenter> a la clase y establezca la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad al nuevo <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Adjuntar el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.Controls.InkPresenter> mediante una llamada a la <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> método y agregue el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección. Esto permite la <xref:System.Windows.Controls.InkPresenter> para mostrar la tinta tal y como se recopilan los datos de punto de lápiz por el control.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Invalide el método <xref:System.Windows.UIElement.OnStylusDown%2A>.  En este método, capture el lápiz con una llamada a <xref:System.Windows.Input.Stylus.Capture%2A>. Al capturar el lápiz, el control le para continuar recibiendo <xref:System.Windows.UIElement.StylusMove> y <xref:System.Windows.UIElement.StylusUp> incluso si el lápiz sale de los límites del control de eventos. Esto no es estrictamente obligatorio, pero casi siempre deseado para una buena experiencia del usuario. Crear un nuevo <xref:System.Windows.Input.StylusPointCollection> para recopilar <xref:System.Windows.Input.StylusPoint> datos. Por último, agregue el conjunto inicial de <xref:System.Windows.Input.StylusPoint> datos a la <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Invalidar el <xref:System.Windows.UIElement.OnStylusMove%2A> método y agregue el <xref:System.Windows.Input.StylusPoint> datos a la <xref:System.Windows.Input.StylusPointCollection> objeto que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Invalidar el <xref:System.Windows.UIElement.OnStylusUp%2A> método y crear un nuevo <xref:System.Windows.Ink.Stroke> con el <xref:System.Windows.Input.StylusPointCollection> datos. Agregue el nuevo <xref:System.Windows.Ink.Stroke> que ha creado para el <xref:System.Windows.Controls.InkPresenter.Strokes%2A> colección de la <xref:System.Windows.Controls.InkPresenter> y liberar la captura del lápiz.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Cómo: habilitar el Control Aceptar la entrada desde el Mouse  
 Si agrega el control anterior a la aplicación, ejecutar y usar el mouse como un dispositivo de entrada, observará que no se conservan los trazos. Para conservar los trazos cuando el mouse se usa como el dispositivo de entrada realice lo siguiente:  
  
1.  Invalidar el <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> y crear un nuevo <xref:System.Windows.Input.StylusPointCollection> obtener la posición del mouse cuando se produjo el evento y crear un <xref:System.Windows.Input.StylusPoint> con los datos de coma y agrega el <xref:System.Windows.Input.StylusPoint> a la <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Invalide el método <xref:System.Windows.UIElement.OnMouseMove%2A>. Obtener la posición del mouse cuando se produjo el evento y crear un <xref:System.Windows.Input.StylusPoint> con los datos de punto.  Agregar el <xref:System.Windows.Input.StylusPoint> a la <xref:System.Windows.Input.StylusPointCollection> objeto que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Invalide el método <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  Crear un nuevo <xref:System.Windows.Ink.Stroke> con el <xref:System.Windows.Input.StylusPointCollection> datos y agregar los nuevos <xref:System.Windows.Ink.Stroke> que ha creado para el <xref:System.Windows.Controls.InkPresenter.Strokes%2A> colección de la <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Colocarlo juntos  
 En el ejemplo siguiente es un control personalizado que recopila tinta cuando el usuario usa el mouse o lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Uso de complementos adicionales y representadores dinámicos  
 Al igual que sucede con InkCanvas, su control personalizado puede tener personalizado <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y adicionales <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objetos. Agregarlas a la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección. El orden de la <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos en el <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> afecta a la apariencia de la tinta cuando se represente. Suponga que tiene un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> llama `dynamicRenderer` y personalizado <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> denominado `translatePlugin` que desplaza la tinta del lápiz de tablet PC. Si `translatePlugin` es la primera <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> en el <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, y `dynamicRenderer` es el segundo, se desplazará la tinta que "fluye" cuando el usuario mueve el lápiz. Si `dynamicRenderer` es el primero, y `translatePlugin` es en segundo lugar, la tinta no se desplazará hasta que el usuario levanta el lápiz.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Puede crear un control que recopile y represente la tinta invalidando los métodos de eventos de lápiz. Al crear su propio control, derive su propia <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> clases e insertándolos el en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, puede implementar prácticamente cualquier comportamiento imaginable con la entrada de lápiz digital. Tener acceso a la <xref:System.Windows.Input.StylusPoint> datos a medida que se generan, lo que le ofrece la oportunidad de personalizar <xref:System.Windows.Input.Stylus> de entrada y representarlo en la pantalla según corresponda para su aplicación. Dado que tienen dicho acceso de bajo nivel a la <xref:System.Windows.Input.StylusPoint> datos, puede implementar la recopilación de tinta y representar con un rendimiento óptimo para la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Control avanzado de entrada manuscrita](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [Obtener acceso y manipular la entrada manuscrita](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
