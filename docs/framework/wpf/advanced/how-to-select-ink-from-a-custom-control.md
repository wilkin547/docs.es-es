---
title: 'Cómo: Seleccionar entradas manuscritas desde un control personalizado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 6c85855cda4f74d557539ed7aea3f725550512e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548373"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Cómo: Seleccionar entradas manuscritas desde un control personalizado
Mediante la adición de un <xref:System.Windows.Ink.IncrementalLassoHitTester> para el control personalizado, puede habilitar el control para que un usuario puede seleccionar una entrada manuscrita con una herramienta de lazo, similar a la forma en que el <xref:System.Windows.Controls.InkCanvas> selecciona entradas de lápiz con un lazo.  
  
 En este ejemplo se da por supuesto que está familiarizado con la creación de un control personalizado habilitado para entradas manuscritas.  Para crear un control personalizado que acepta datos proporcionados por tinta, consulte [crear un Control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## <a name="example"></a>Ejemplo  
 Cuando el usuario dibuja un lazo, la <xref:System.Windows.Ink.IncrementalLassoHitTester> predice qué trazos estarán dentro de los límites de la ruta de acceso del lazo después de que el usuario completa el lazo.  Trazos que van a ser dentro de los límites de la ruta de acceso del lazo pueden considerarse como que se selecciona.  Trazos seleccionados también pueden convertirse en no seleccionados.  Por ejemplo, si el usuario invierte la dirección al dibujar el lazo, el <xref:System.Windows.Ink.IncrementalLassoHitTester> puede anular la selección de algunos trazos.  
  
 El <xref:System.Windows.Ink.IncrementalLassoHitTester> provoca la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos, lo que permite el control personalizado responder cuando el usuario está dibujando el lazo.  Por ejemplo, puede cambiar la apariencia de los trazos cuando el usuario selecciona y anula la selección de ellas.  
  
## <a name="managing-the-ink-mode"></a>Administrar el modo de entrada manuscrita  
 Resulta útil para el usuario si el lazo aparece de forma diferente a la entrada manuscrita en el control. Debe realizar para lograr esto, un seguimiento de las del control personalizado si el usuario es escribir o seleccionar la tinta. La manera más fácil de hacerlo es declarar una enumeración con dos valores: uno para indicar que el usuario está escribiendo tinta y otro para indicar que el usuario está seleccionando tinta.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 A continuación, agregue dos <xref:System.Windows.Ink.DrawingAttributes> a la clase: uno que se usará cuando el usuario escribe trazos de tinta, que va a utilizar cuando el usuario selecciona tinta.  En el constructor, inicializar el <xref:System.Windows.Ink.DrawingAttributes> y adjuntar ambos <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos al mismo controlador de eventos. A continuación, establezca el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la entrada manuscrita <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Agregar una propiedad que expone el modo de selección. Cuando el usuario cambia el modo de selección, establezca la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> correspondientes <xref:System.Windows.Ink.DrawingAttributes> objeto y, a continuación, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> propiedad a la <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Exponer el <xref:System.Windows.Ink.DrawingAttributes> como propiedades para que las aplicaciones puedan determinar la apariencia de los trazos de tinta y trazos de selección.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Cuando una propiedad de un <xref:System.Windows.Ink.DrawingAttributes> los cambios, un objeto del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> debe volverse a adjuntar a la <xref:System.Windows.Controls.InkPresenter>.  En el controlador de eventos para el <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a la <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Utilizar IncrementalLassoHitTester  
 Crear e inicializar un <xref:System.Windows.Ink.StrokeCollection> que contiene los trazos seleccionados.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Cuando el usuario empieza a dibujar un trazo, tinta o el lazo, anule la selección de todos los trazos seleccionados. A continuación, si el usuario está dibujando un lazo, cree un <xref:System.Windows.Ink.IncrementalLassoHitTester> mediante una llamada a <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, suscribirse a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos y llamadas <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Este código puede ser un método independiente y se llama desde el <xref:System.Windows.UIElement.OnStylusDown%2A> y <xref:System.Windows.UIElement.OnMouseDown%2A> métodos.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Agregue los puntos de lápiz a la <xref:System.Windows.Ink.IncrementalLassoHitTester> mientras el usuario dibuja el lazo.  Llamar al método desde el <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, y <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> métodos.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Controlar la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> evento para responder cuando el usuario selecciona y anula la selección de trazos.  El <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> clase tiene la <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> y <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> propiedades que obtienen los trazos que se seleccionaron y no está seleccionadas, respectivamente.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Cuando el usuario termina de dibujar el lazo, cancelar la suscripción a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos y llame al método <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Colocar todo en uno.  
 El ejemplo siguiente es un control personalizado que permite al usuario seleccionar entradas de lápiz con un lazo.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [Creación de un control de entrada a mano](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
