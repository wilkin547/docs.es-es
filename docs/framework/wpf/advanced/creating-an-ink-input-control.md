---
title: "Creaci&#243;n de un control de entrada manuscrita | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "recopilar trazos de entrada manuscrita"
  - "DynamicRenderer (objetos)"
  - "controles para proporcionar entrada manuscrita"
  - "trazos de entrada manuscrita, recopilar"
  - "trazos de entrada manuscrita, administrar"
  - "entrada manuscrita, representación"
  - "entrada desde el mouse, aceptar"
  - "administrar trazos de entrada manuscrita"
  - "entrada del mouse, aceptar"
  - "representar entrada manuscrita"
  - "StylusPlugIn (objetos)"
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Creaci&#243;n de un control de entrada manuscrita
Puede crear un control personalizado que represente la entrada de lápiz de forma dinámica y estática.  Es decir, es posible representar la entrada de lápiz mientras el usuario dibuja el trazo, con lo que parece "fluir" del lápiz de Tablet PC, y mostrar la entrada de lápiz una vez agregada al control, bien a través del lápiz de Tablet PC, pegada desde el Portapapeles o cargada desde un archivo.  Para representar dinámicamente la entrada de lápiz, el control debe usar <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Para representar estáticamente la entrada de lápiz, debe invalidar los métodos de evento de lápiz \(<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A> y <xref:System.Windows.UIElement.OnStylusUp%2A>\) para recopilar los datos de <xref:System.Windows.Input.StylusPoint>, crear los trazos y agregarlos a un objeto <xref:System.Windows.Controls.InkPresenter> \(que representa la entrada de lápiz en el control\).  
  
 Este tema contiene las siguientes subsecciones:  
  
-   [Cómo: Recopilar datos de los puntos de lápiz y crear trazos de entrada de lápiz](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Cómo: Permitir que el control acepte la entrada del mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Resultado final](#PuttingItTogether)  
  
-   [Uso de complementos adicionales y representadores dinámicos](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Conclusión](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## Cómo: Recopilar datos de los puntos de lápiz y crear trazos de entrada de lápiz  
 Para crear un control que recopile y administre los trazos de entrada de lápiz, realice estas acciones:  
  
1.  Derive una clase de <xref:System.Windows.Controls.Control> o una de las clases derivadas de <xref:System.Windows.Controls.Control>, como <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  Agregue un objeto <xref:System.Windows.Controls.InkPresenter> a la clase y establezca la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> en el nuevo objeto <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  Asocie la propiedad <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> al objeto <xref:System.Windows.Controls.InkPresenter> mediante una llamada al método <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> y agregue <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la colección <xref:System.Windows.UIElement.StylusPlugIns%2A>.  Esto permite a <xref:System.Windows.Controls.InkPresenter> mostrar la entrada de lápiz a medida que el control recopila los datos de los puntos de lápiz.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  Invalide el método <xref:System.Windows.UIElement.OnStylusDown%2A>.  En este método, capture el lápiz con una llamada a <xref:System.Windows.Input.Stylus.Capture%2A>.  Al capturar el lápiz, su control seguirá recibiendo eventos <xref:System.Windows.UIElement.StylusMove> y <xref:System.Windows.UIElement.StylusUp> aun cuando el lápiz abandone los límites del control.  Esto no es estrictamente obligatorio, pero es deseable en la mayoría de los casos, para mejorar la experiencia del usuario.  Cree una nueva <xref:System.Windows.Input.StylusPointCollection> para recopilar los datos de <xref:System.Windows.Input.StylusPoint>.  Finalmente, agregue el conjunto inicial de datos de <xref:System.Windows.Input.StylusPoint> a <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  Invalide el método <xref:System.Windows.UIElement.OnStylusMove%2A> y agregue los datos de <xref:System.Windows.Input.StylusPoint> al objeto <xref:System.Windows.Input.StylusPointCollection> que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  Invalide el método <xref:System.Windows.UIElement.OnStylusUp%2A> y cree un nuevo objeto <xref:System.Windows.Ink.Stroke> con los datos de <xref:System.Windows.Input.StylusPointCollection>.  Agregue el objeto <xref:System.Windows.Ink.Stroke> que ha creado a la colección <xref:System.Windows.Controls.InkPresenter.Strokes%2A> de <xref:System.Windows.Controls.InkPresenter> y libere la captura del lápiz.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## Cómo: Permitir que el control acepte la entrada del mouse  
 Si agrega el control anterior a su aplicación, lo ejecuta y usa el mouse como dispositivo de entrada, observará que no se conservan los trazos.  Para conservar los trazos cuando se use el mouse como dispositivo de entrada realice los pasos siguientes:  
  
1.  Invalide el método <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> y cree un nuevo objeto <xref:System.Windows.Input.StylusPointCollection>. Obtenga la posición del mouse cuando se produjo el evento, cree un objeto <xref:System.Windows.Input.StylusPoint> a partir de los datos de los puntos y agregue el objeto <xref:System.Windows.Input.StylusPoint> a <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  Invalide el método <xref:System.Windows.UIElement.OnMouseMove%2A>.  Obtenga la posición del mouse cuando se produjo el evento y cree un objeto <xref:System.Windows.Input.StylusPoint> con los datos de los puntos.  Agregue <xref:System.Windows.Input.StylusPoint> al objeto <xref:System.Windows.Input.StylusPointCollection> que creó anteriormente.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  Invalide el método <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  Cree un nuevo objeto <xref:System.Windows.Ink.Stroke> con los datos de <xref:System.Windows.Input.StylusPointCollection> y agregue el nuevo <xref:System.Windows.Ink.Stroke> que creó a la colección <xref:System.Windows.Controls.InkPresenter.Strokes%2A> de <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## Resultado final  
 En el ejemplo siguiente se ilustra un control personalizado que recopila la entrada de lápiz cuando el usuario emplea el mouse o el lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## Uso de complementos adicionales y representadores dinámicos  
 Como sucede con InkCanvas, su control personalizado puede tener elementos <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizados y objetos <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> adicionales.  Agréguelos a la colección <xref:System.Windows.UIElement.StylusPlugIns%2A>.  El orden de los objetos <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> afecta a la apariencia de la entrada de lápiz cuando se representa.  Supongamos que tiene un objeto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> denominado `dynamicRenderer` y un objeto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizado denominado `translatePlugin` que desplaza la entrada de lápiz del lápiz de Tablet PC.  Si `translatePlugin` es el primer <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> de <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> y `dynamicRenderer` es el segundo, la entrada de lápiz que "fluye" se desplazará a medida que el usuario mueva el lápiz.  Si `dynamicRenderer` está primero y `translatePlugin` es el segundo, no se desplazará la entrada de lápiz hasta que el usuario levante el lápiz.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## Conclusión  
 Puede crear un control que recopile y represente la entrada de lápiz si invalida los métodos de evento de lápiz.  Si crea un control propio, deriva sus propias clases <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y las inserta en <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, podrá implementar prácticamente cualquier comportamiento imaginable con la entrada de lápiz digital.  Al tener acceso a los datos de <xref:System.Windows.Input.StylusPoint> a medida que se generan, puede personalizar la entrada de <xref:System.Windows.Input.Stylus> y representarla en pantalla según sea adecuado para su aplicación.  Dado que tiene este acceso tan detallado a los datos de <xref:System.Windows.Input.StylusPoint>, puede implementar la recopilación y representación de la entrada de lápiz con un rendimiento óptimo para su aplicación.  
  
## Vea también  
 [Control avanzado de entrada manuscrita](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Obtener acceso y manipular entradas manuscritas](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)