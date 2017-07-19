---
title: "Personalizar la representaci&#243;n de la entrada manuscrita | Microsoft Docs"
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
  - "clases, DynamicRenderer"
  - "clases, InkCanvas"
  - "clases, Trazo"
  - "personalizar la representación de la entrada manuscrita"
  - "DynamicRenderer (clase)"
  - "entrada manuscrita, representación personalizada"
  - "InkCanvas (clase)"
  - "Stroke (clase)"
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Personalizar la representaci&#243;n de la entrada manuscrita
La propiedad <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> de un trazo permite especificar su apariencia \(por ejemplo, su tamaño, color y forma\), pero puede haber ocasiones en las que desee personalizar la apariencia más de lo que <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> permite.  Quizás desee personalizar la apariencia de la entrada de lápiz representándola con la apariencia de un aerógrafo, pintura al óleo y muchos otros efectos.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] permite personalizar la representación de la entrada de lápiz mediante la implementación de un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado y un objeto <xref:System.Windows.Ink.Stroke>.  
  
 Este tema contiene las siguientes subsecciones:  
  
-   [Arquitectura](#Architecture)  
  
-   [Implementación de un representador dinámico](#ImplementingADynamicRenderer)  
  
-   [Implementing a Custom Stroke](#ImplementingACustomStroke)  
  
-   [Implementación de una clase InkCanvas personalizada](#ImplementingACustomInkCanvas)  
  
-   [Conclusión](#Conclusion)  
  
<a name="Architecture"></a>   
## Arquitectura  
 La representación de la entrada de lápiz se produce en dos tiempos: cuando el usuario escribe en una superficie habilitada para entrada de lápiz y después de que se agrega el trazo a dicha superficie.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> representa la entrada de lápiz cuando el usuario mueve el lápiz de Tablet PC en el digitalizador y <xref:System.Windows.Ink.Stroke> se representa después de que se ha agregado a un elemento.  
  
 Al representar la entrada de lápiz de forma dinámica, se implementan tres clases.  
  
1.  **DynamicRenderer**: implemente una clase que se derive de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Esta clase es un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> especializado que representa el trazo a medida que se dibuja.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> realiza la representación en un subproceso aparte, por lo que la superficie de entrada de lápiz parece recopilar la entrada de lápiz incluso cuando el subproceso de la interfaz de usuario de la aplicación está bloqueado.  Para obtener más información acerca del modelo de subprocesos, consulte [Modelo de subprocesamiento de entrada manuscrita](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  Para personalizar la representación dinámica de un trazo, invalide el método <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>.  
  
2.  **Stroke**: implemente una clase que se derive de <xref:System.Windows.Ink.Stroke>.  Esta clase es responsable de la representación estática de los datos de <xref:System.Windows.Input.StylusPoint> una vez convertidos en un objeto <xref:System.Windows.Ink.Stroke>.  Invalide el método <xref:System.Windows.Ink.Stroke.DrawCore%2A> para asegurarse de que la representación estática del trazo es coherente con la representación dinámica.  
  
3.  **InkCanvas:** implemente una clase que se derive de <xref:System.Windows.Controls.InkCanvas>.  Asigne el objeto <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado a la propiedad <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>.  Invalide el método <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> y agregue un trazo personalizado a la propiedad <xref:System.Windows.Controls.InkCanvas.Strokes%2A>.  De esta forma se garantiza que la apariencia de la entrada de lápiz es coherente.  
  
<a name="ImplementingADynamicRenderer"></a>   
## Implementación de un representador dinámico  
 Aunque la clase <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> es una parte estándar de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], para realizar una representación más especializada, debe crear un representador dinámico personalizado que se derive de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e invalidar el método <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>.  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado que dibuja la entrada de lápiz con un efecto de pincel de degradado lineal.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## Implementación de trazos personalizados  
 Implemente una clase que se derive de <xref:System.Windows.Ink.Stroke>.  Esta clase es responsable de la representación de los datos de <xref:System.Windows.Input.StylusPoint> una vez convertidos en un objeto <xref:System.Windows.Ink.Stroke>.  Invalide la clase <xref:System.Windows.Ink.Stroke.DrawCore%2A> para crear el verdadero dibujo.  
  
 Su clase Stroke también puede almacenar datos personalizados si usa el método <xref:System.Windows.Ink.Stroke.AddPropertyData%2A>.  Estos datos se almacenan con los datos de trazo cuando se guardan.  
  
 La clase <xref:System.Windows.Ink.Stroke> también puede realizar pruebas de posicionamiento.  También puede implementar un algoritmo de prueba de posicionamiento propio si invalida el método <xref:System.Windows.Ink.Stroke.HitTest%2A> en la clase actual.  
  
 El código de C\# siguiente muestra una clase <xref:System.Windows.Ink.Stroke> personalizada que representa los datos de <xref:System.Windows.Input.StylusPoint> como un trazo 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## Implementación de una clase InkCanvas personalizada  
 La manera más fácil de usar su <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> y trazo personalizados es implementar una clase que se derive de <xref:System.Windows.Controls.InkCanvas> y use estas clases.  <xref:System.Windows.Controls.InkCanvas> tiene una propiedad <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> que especifica cómo se representa el trazo cuando el usuario está dibujándolo.  
  
 Para personalizar la representación de trazos en <xref:System.Windows.Controls.InkCanvas>, realice estos pasos:  
  
-   Cree una clase que se derive de <xref:System.Windows.Controls.InkCanvas>.  
  
-   Asigne su <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado a la propiedad <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=fullName>.  
  
-   Invalide el método <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>.  En este método, quite el trazo original que se agregó a InkCanvas.  A continuación, cree un trazo personalizado, agréguelo a la propiedad <xref:System.Windows.Controls.InkCanvas.Strokes%2A> y llame a la clase base con una nueva clase <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> que contenga el trazo personalizado.  
  
 El código de C\# siguiente muestra una clase <xref:System.Windows.Controls.InkCanvas> personalizada que usa un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizado y recopila los trazos personalizados.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <xref:System.Windows.Controls.InkCanvas> puede tener más de un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  Para agregar varios objetos <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a <xref:System.Windows.Controls.InkCanvas>, agréguelos a la propiedad <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
<a name="Conclusion"></a>   
## Conclusión  
 Puede personalizar la apariencia de la entrada de lápiz al derivar sus propias clases <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke> y <xref:System.Windows.Controls.InkCanvas>.  Juntas, estas clases garantizan que la apariencia del trazo es coherente cuando el usuario dibuja el trazo y después de que se ha recopilado.  
  
## Vea también  
 [Control avanzado de entrada manuscrita](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)