---
title: Procedimiento Seleccionar entradas de lápiz desde un control personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768419"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Procedimiento Seleccionar entradas de lápiz desde un control personalizado
Agregando un <xref:System.Windows.Ink.IncrementalLassoHitTester> al control personalizado, puede habilitar el control para que un usuario puede seleccionar entradas manuscritas con una herramienta de lazo, similar a la forma en que el <xref:System.Windows.Controls.InkCanvas> selecciona la entrada de lápiz con un lazo.  
  
 En este ejemplo se da por supuesto que está familiarizado con la creación de un control personalizado habilitado para tinta.  Para crear un control personalizado que acepta la entrada de lápiz, consulte [creación de un Control entrada manuscrita](creating-an-ink-input-control.md).  
  
## <a name="example"></a>Ejemplo  
 Cuando el usuario dibuja un lazo, el <xref:System.Windows.Ink.IncrementalLassoHitTester> predice qué trazos estarán dentro de los límites del trazado de lazo después de que el usuario completa el lazo.  Trazos que se determinan que dentro de los límites del trazado de lazo pueden considerarse como seleccionado.  Los trazos seleccionados también pueden convertirse en no seleccionados.  Por ejemplo, si el usuario invierte la dirección al dibujar el lazo, el <xref:System.Windows.Ink.IncrementalLassoHitTester> puede anular la selección de algunos trazos.  
  
 El <xref:System.Windows.Ink.IncrementalLassoHitTester> provoca la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos, lo que permite el control personalizado responder cuando el usuario está dibujando el lazo.  Por ejemplo, puede cambiar la apariencia de los trazos cuando el usuario selecciona y anula la selección de ellos.  
  
## <a name="managing-the-ink-mode"></a>Administrar el modo de entrada manuscrita  
 Resulta útil al usuario si el lazo aparece de forma diferente a la entrada manuscrita en el control. Para lograr esto, el control personalizado debe controlar de si el usuario está escribiendo o selección de tinta. La manera más fácil de hacerlo es declarar una enumeración con dos valores: uno para indicar que el usuario está escribiendo tinta y otro para indicar que el usuario es seleccionar entradas manuscritas.  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 A continuación, agregue dos <xref:System.Windows.Ink.DrawingAttributes> a la clase: uno que se usará cuando el usuario escribe con el lápiz, que va a utilizar cuando el usuario selecciona la entrada de lápiz.  En el constructor, inicializar el <xref:System.Windows.Ink.DrawingAttributes> y conecte ambos <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos al mismo controlador de eventos. A continuación, establezca el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la entrada de lápiz <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Agregue una propiedad que expone el modo de selección. Cuando el usuario cambia el modo de selección, establezca el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> correspondientes <xref:System.Windows.Ink.DrawingAttributes> de objetos y, a continuación, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> propiedad a la <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Exponer el <xref:System.Windows.Ink.DrawingAttributes> como propiedades, por lo que las aplicaciones pueden determinar la apariencia de los trazos de tinta y trazos de selección.  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Cuando una propiedad de un <xref:System.Windows.Ink.DrawingAttributes> objeto los cambios, el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> debe volverse a conectar el <xref:System.Windows.Controls.InkPresenter>.  En el controlador de eventos para el <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a la <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Utilizar IncrementalLassoHitTester  
 Crear e inicializar un <xref:System.Windows.Ink.StrokeCollection> que contiene los trazos seleccionados.  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Cuando el usuario empieza a dibujar un trazo, entrada de lápiz o el lazo, anule la selección de todos los trazos seleccionados. A continuación, si el usuario está dibujando un lazo, cree un <xref:System.Windows.Ink.IncrementalLassoHitTester> mediante una llamada a <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, suscribirse a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento y llamar a <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Este código puede ser un método independiente y se llama desde el <xref:System.Windows.UIElement.OnStylusDown%2A> y <xref:System.Windows.UIElement.OnMouseDown%2A> métodos.  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Agregue los puntos del lápiz a la <xref:System.Windows.Ink.IncrementalLassoHitTester> mientras el usuario dibuja el lazo.  Llame al método siguiente desde el <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, y <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> métodos.  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Controlar la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> eventos para responder cuando el usuario selecciona y anula la selección de trazos.  El <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> clase tiene el <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> y <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> que obtienen los trazos que se ha seleccionado y no está seleccionada, respectivamente.  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Cuando el usuario termina el lazo de dibujo, cancelar la suscripción a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos y llamadas <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Colocar todos los elementos.  
 El ejemplo siguiente es un control personalizado que permite al usuario seleccionar entradas manuscritas con un lazo.  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [Creación de un control de entrada a mano](creating-an-ink-input-control.md)
