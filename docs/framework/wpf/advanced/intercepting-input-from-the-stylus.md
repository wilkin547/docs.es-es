---
title: "Interceptar entradas del l&#225;piz &#243;ptico | Microsoft Docs"
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
  - "arquitectura, System.Windows.Input.StylusPlugIns"
  - "InkCanvas, agregar complementos a"
  - "complementos, lápiz"
  - "StylusPlugIns (arquitectura)"
  - "System.Windows.Input.StylusPlugIns (arquitectura)"
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Interceptar entradas del l&#225;piz &#243;ptico
La arquitectura del espacio de nombres <xref:System.Windows.Input.StylusPlugIns> proporciona un mecanismo para implementar un control de nivel inferior sobre las entradas correspondientes a la clase <xref:System.Windows.Input.Stylus> y la creación de objetos <xref:System.Windows.Ink.Stroke> de entrada de lápiz digital.  La clase <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> proporciona un mecanismo para implementar un comportamiento personalizado y aplicarlo a la secuencia de datos procedente del dispositivo de lápiz óptico, a fin de lograr un rendimiento óptimo.  
  
 Este tema contiene las siguientes subsecciones:  
  
-   [Arquitectura](#Architecture)  
  
-   [Implementar complementos de lápiz óptico](#ImplementingStylusPlugins)  
  
-   [Agregar un complemento a una clase InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## Arquitectura  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> es la evolución de las interfaces de programación de aplicaciones \(API\) del espacio de nombres [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409), que se describen en [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), de [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409) \(todos en inglés\).  
  
 Cada <xref:System.Windows.UIElement> tiene una propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A> que es una clase <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Puede agregar un objeto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A> de un elemento para manipular los datos de <xref:System.Windows.Input.StylusPoint> a medida que generan.  Los datos de <xref:System.Windows.Input.StylusPoint> están compuestos de todas las propiedades admitidas por el digitalizador del sistema, incluidos los datos de los puntos <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A>, así como los datos de <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>.  
  
 Los objetos <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> se insertan directamente en la secuencia de datos procedente del dispositivo <xref:System.Windows.Input.Stylus> cuando se agrega <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>.  El orden en que se agregan los complementos a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A> rige el orden en el que éstos reciben los datos de <xref:System.Windows.Input.StylusPoint>.  Por ejemplo, si agrega un complemento de filtro que restringe la entrada a una región determinada, y, a continuación, agrega un complemento que reconoce los gestos a medida que se escribe, el complemento que reconoce los gestos recibe datos filtrados de <xref:System.Windows.Input.StylusPoint>.  
  
<a name="ImplementingStylusPlugins"></a>   
## Implementar complementos de lápiz óptico  
 Para implementar un complemento, derive una clase de <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  Esta clase se aplica a la secuencia de datos a medida que se recibe de <xref:System.Windows.Input.Stylus>.  En esta clase, puede modificar los valores de los datos de <xref:System.Windows.Input.StylusPoint>.  
  
> [!CAUTION]
>  Si <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> inicia o produce una excepción, la aplicación se cierra.  Debe comprobar exhaustivamente los controles que usan <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y sólo debe usar un control si está seguro de que <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> no producirá una excepción.  
  
 En el ejemplo siguiente se muestra un complemento que restringe las entradas de lápiz óptico modificando los valores de <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> en los datos de <xref:System.Windows.Input.StylusPoint> a medida que entran a través del dispositivo <xref:System.Windows.Input.Stylus>.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## Agregar un complemento a una clase InkCanvas  
 La manera más fácil de utilizar un complemento personalizado es implementar una clase derivada de InkCanvas y agregarla a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
 En el ejemplo siguiente se muestra un control <xref:System.Windows.Controls.InkCanvas> personalizado que filtra las entradas de lápiz.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Si agrega `FilterInkCanvas` a la aplicación y la ejecuta, observará que las entradas de lápiz no se restringen a una región concreta hasta que el usuario ha completado un trazo.  Esto se debe a que <xref:System.Windows.Controls.InkCanvas> tiene una propiedad <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, que es una clase <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y ya es miembro de la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>.  El complemento <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizado que agregó a la colección <xref:System.Windows.UIElement.StylusPlugIns%2A> recibe los datos de <xref:System.Windows.Input.StylusPoint> después de que <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> haya recibido los datos.  Como resultado, los datos de <xref:System.Windows.Input.StylusPoint> no se filtran hasta que el usuario levante el lápiz para finalizar un trazo.  Para filtrar las entradas de lápiz mientras el usuario las dibuja, debe insertar el filtro `FilterPlugin` antes que <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 El código C\# siguiente muestra un control <xref:System.Windows.Controls.InkCanvas> personalizado que filtra las entradas de lápiz mientras se dibujan.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## Conclusión  
 Si deriva sus propias clases <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> y las inserta en colecciones <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, puede mejorar en gran medida el comportamiento de las entradas de lápiz digitales.  El acceso a los datos de <xref:System.Windows.Input.StylusPoint> a medida que se generan, le permite personalizar la entrada de <xref:System.Windows.Input.Stylus>.  Gracias a este acceso de bajo nivel a los datos de <xref:System.Windows.Input.StylusPoint>, puede implementarse la recopilación y la representación de las entradas de lápiz con un rendimiento óptimo para la aplicación.  
  
## Vea también  
 [Control avanzado de entrada manuscrita](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Obtener acceso y manipular entradas manuscritas](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)