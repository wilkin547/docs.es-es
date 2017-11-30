---
title: "Cómo: Seleccionar entradas manuscritas desde un control personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd9693209cc35ecd3c0473133b7c21639a239ff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="8ddb6-102">Cómo: Seleccionar entradas manuscritas desde un control personalizado</span><span class="sxs-lookup"><span data-stu-id="8ddb6-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="8ddb6-103">Mediante la adición de un <xref:System.Windows.Ink.IncrementalLassoHitTester> para el control personalizado, puede habilitar el control para que un usuario puede seleccionar una entrada manuscrita con una herramienta de lazo, similar a la forma en que el <xref:System.Windows.Controls.InkCanvas> selecciona entradas de lápiz con un lazo.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="8ddb6-104">En este ejemplo se da por supuesto que está familiarizado con la creación de un control personalizado habilitado para entradas manuscritas.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="8ddb6-105">Para crear un control personalizado que acepta datos proporcionados por tinta, consulte [crear un Control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="8ddb6-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddb6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ddb6-106">Example</span></span>  
 <span data-ttu-id="8ddb6-107">Cuando el usuario dibuja un lazo, la <xref:System.Windows.Ink.IncrementalLassoHitTester> predice qué trazos estarán dentro de los límites de la ruta de acceso del lazo después de que el usuario completa el lazo.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="8ddb6-108">Trazos que van a ser dentro de los límites de la ruta de acceso del lazo pueden considerarse como que se selecciona.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="8ddb6-109">Trazos seleccionados también pueden convertirse en no seleccionados.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="8ddb6-110">Por ejemplo, si el usuario invierte la dirección al dibujar el lazo, el <xref:System.Windows.Ink.IncrementalLassoHitTester> puede anular la selección de algunos trazos.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="8ddb6-111">El <xref:System.Windows.Ink.IncrementalLassoHitTester> provoca la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos, lo que permite el control personalizado responder cuando el usuario está dibujando el lazo.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="8ddb6-112">Por ejemplo, puede cambiar la apariencia de los trazos cuando el usuario selecciona y anula la selección de ellas.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="8ddb6-113">Administrar el modo de entrada manuscrita</span><span class="sxs-lookup"><span data-stu-id="8ddb6-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="8ddb6-114">Resulta útil para el usuario si el lazo aparece de forma diferente a la entrada manuscrita en el control.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="8ddb6-115">Debe realizar para lograr esto, un seguimiento de las del control personalizado si el usuario es escribir o seleccionar la tinta.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="8ddb6-116">La manera más fácil de hacerlo es declarar una enumeración con dos valores: uno para indicar que el usuario está escribiendo tinta y otro para indicar que el usuario está seleccionando tinta.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="8ddb6-117">A continuación, agregue dos <xref:System.Windows.Ink.DrawingAttributes> a la clase: uno que se usará cuando el usuario escribe trazos de tinta, que va a utilizar cuando el usuario selecciona tinta.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="8ddb6-118">En el constructor, inicializar el <xref:System.Windows.Ink.DrawingAttributes> y adjuntar ambos <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos al mismo controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="8ddb6-119">A continuación, establezca el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> a la entrada manuscrita <xref:System.Windows.Ink.DrawingAttributes>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="8ddb6-120">Agregar una propiedad que expone el modo de selección.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="8ddb6-121">Cuando el usuario cambia el modo de selección, establezca la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> propiedad de la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> correspondientes <xref:System.Windows.Ink.DrawingAttributes> objeto y, a continuación, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> propiedad a la <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="8ddb6-122">Exponer el <xref:System.Windows.Ink.DrawingAttributes> como propiedades para que las aplicaciones puedan determinar la apariencia de los trazos de tinta y trazos de selección.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="8ddb6-123">Cuando una propiedad de un <xref:System.Windows.Ink.DrawingAttributes> los cambios, un objeto del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> debe volverse a adjuntar a la <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="8ddb6-124">En el controlador de eventos para el <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventos, volver a adjuntar la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a la <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="8ddb6-125">Utilizar IncrementalLassoHitTester</span><span class="sxs-lookup"><span data-stu-id="8ddb6-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="8ddb6-126">Crear e inicializar un <xref:System.Windows.Ink.StrokeCollection> que contiene los trazos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="8ddb6-127">Cuando el usuario empieza a dibujar un trazo, tinta o el lazo, anule la selección de todos los trazos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="8ddb6-128">A continuación, si el usuario está dibujando un lazo, cree un <xref:System.Windows.Ink.IncrementalLassoHitTester> mediante una llamada a <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, suscribirse a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos y llamadas <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="8ddb6-129">Este código puede ser un método independiente y se llama desde el <xref:System.Windows.UIElement.OnStylusDown%2A> y <xref:System.Windows.UIElement.OnMouseDown%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="8ddb6-130">Agregue los puntos de lápiz a la <xref:System.Windows.Ink.IncrementalLassoHitTester> mientras el usuario dibuja el lazo.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="8ddb6-131">Llamar al método desde el <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, y <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="8ddb6-132">Controlar la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> evento para responder cuando el usuario selecciona y anula la selección de trazos.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="8ddb6-133">El <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> clase tiene la <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> y <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> propiedades que obtienen los trazos que se seleccionaron y no está seleccionadas, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="8ddb6-134">Cuando el usuario termina de dibujar el lazo, cancelar la suscripción a la <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventos y llame al método <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="8ddb6-135">Colocar todo en uno.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-135">Putting it All Together.</span></span>  
 <span data-ttu-id="8ddb6-136">El ejemplo siguiente es un control personalizado que permite al usuario seleccionar entradas de lápiz con un lazo.</span><span class="sxs-lookup"><span data-stu-id="8ddb6-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8ddb6-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ddb6-137">See Also</span></span>  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [<span data-ttu-id="8ddb6-138">Creación de un control de entrada a mano</span><span class="sxs-lookup"><span data-stu-id="8ddb6-138">Creating an Ink Input Control</span></span>](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
