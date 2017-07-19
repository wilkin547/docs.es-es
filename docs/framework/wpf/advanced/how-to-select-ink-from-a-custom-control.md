---
title: "C&#243;mo: Seleccionar entradas manuscritas desde un control personalizado | Microsoft Docs"
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
  - "controles, selección de entrada manuscrita"
  - "controles personalizados, selección de entrada manuscrita"
  - "entrada manuscrita, seleccionar en un control personalizado"
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Seleccionar entradas manuscritas desde un control personalizado
Si agrega una clase <xref:System.Windows.Ink.IncrementalLassoHitTester> a su control personalizado, puede habilitarlo para que un usuario seleccione entradas de lápiz con una herramienta de lazo, similar a la manera en que <xref:System.Windows.Controls.InkCanvas> selecciona entradas de lápiz con un lazo.  
  
 En este ejemplo se supone que está familiarizado con la creación de un control personalizado habilitado para entradas de lápiz.  Para crear un control personalizado que acepta la entrada de entradas de lápiz, vea [Creación de un control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## Ejemplo  
 Cuando el usuario dibuja un lazo, <xref:System.Windows.Ink.IncrementalLassoHitTester> predice qué trazos estarán dentro de los límites de la trayectoria del lazo después de que el usuario lo complete.  Los trazos que se determina que están dentro de los límites de la trayectoria del lazo pueden considerarse como seleccionados.  También puede anularse la selección de los trazos seleccionados.  Por ejemplo, si el usuario invierte la dirección al dibujar el lazo, <xref:System.Windows.Ink.IncrementalLassoHitTester> puede anular la selección de algunos trazos.  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester> provoca el evento <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>, que permite que el control personalizado responda mientras el usuario está dibujando el lazo.  Por ejemplo, puede cambiar la apariencia de los trazos cuando el usuario los selecciona y anula su selección.  
  
## Administrar el modo de entrada de lápiz  
 Resulta útil para el usuario que el lazo tenga una apariencia diferente de la entrada de lápiz en el control.  Para conseguirlo, el control personalizado debe mantener un seguimiento para saber si el usuario está escribiendo o seleccionando entradas de lápiz.  La manera más fácil de hacerlo es declarar una enumeración con dos valores: uno para indicar que el usuario está realizando entradas de lápiz y otro para indicar que el usuario está seleccionando entradas de lápiz.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 A continuación, agregue dos atributos <xref:System.Windows.Ink.DrawingAttributes> a la clase: uno para utilizarlo cuando el usuario realice entradas de lápiz y otro para utilizarlo cuando el usuario seleccione entradas de lápiz.  En el constructor, inicialice <xref:System.Windows.Ink.DrawingAttributes> y asocie ambos eventos <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> al mismo controlador de eventos.  A continuación, establezca la propiedad <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> en la clase <xref:System.Windows.Ink.DrawingAttributes> de entrada de lápiz.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Agregue una propiedad que exponga el modo de selección.  Cuando el usuario cambie el modo de selección, establezca la propiedad <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> de <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> en el objeto <xref:System.Windows.Ink.DrawingAttributes> adecuado y, a continuación, vuelva a adjuntar la propiedad <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Exponga el objeto <xref:System.Windows.Ink.DrawingAttributes> como propiedades para que las aplicaciones puedan determinar la apariencia de los trazos de las entradas de lápiz y de los trazos de selección.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Cuando cambia una propiedad de un objeto <xref:System.Windows.Ink.DrawingAttributes>, es preciso volver a adjuntar <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a <xref:System.Windows.Controls.InkPresenter>.  En el controlador de eventos correspondiente al evento <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>, vuelva a adjuntar la propiedad <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> al objeto <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## Utilizar IncrementalLassoHitTester  
 Cree e inicialice una clase <xref:System.Windows.Ink.StrokeCollection> que contenga los trazos seleccionados.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Cuando el usuario empiece a dibujar un trazo, ya sea una entrada de lápiz o el lazo, anule la selección de todos los trazos seleccionados.  A continuación, si el usuario está dibujando un lazo, cree un objeto <xref:System.Windows.Ink.IncrementalLassoHitTester> mediante una llamada a <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, suscríbase al evento <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> y llame a <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.  Este código puede ser un método independiente al que se puede llamar desde los métodos <xref:System.Windows.UIElement.OnStylusDown%2A> y <xref:System.Windows.UIElement.OnMouseDown%2A>.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Agregue los puntos del lápiz óptico a <xref:System.Windows.Ink.IncrementalLassoHitTester> mientras el usuario dibuja el lazo.  Llame al método siguiente desde los métodos <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A> y <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Administre el evento <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=fullName> para que responda cuando el usuario seleccione trazos o anule su selección.  La clase <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> tiene las propiedades <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> y <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A>, que obtienen los trazos que se han seleccionado y cuya selección se ha anulado, respectivamente.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Cuando el usuario termina de dibujar el lazo, cancele la suscripción al evento <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> y llame a <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## Realizar el proceso completo  
 El ejemplo siguiente es un control personalizado que permite al usuario seleccionar entradas de lápiz con un lazo.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>   
 <xref:System.Windows.Ink.StrokeCollection>   
 <xref:System.Windows.Input.StylusPointCollection>   
 [Creación de un control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)