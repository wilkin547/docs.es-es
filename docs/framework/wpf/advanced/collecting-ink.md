---
title: Recopilar entrada manuscrita digital
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747028"
---
# <a name="collect-ink"></a><span data-ttu-id="ffdef-102">Recopilar entrada de lápiz</span><span class="sxs-lookup"><span data-stu-id="ffdef-102">Collect Ink</span></span>

<span data-ttu-id="ffdef-103">La plataforma [Windows Presentation Foundation](../index.md) recopila entradas de lápiz digitales como parte esencial de su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ffdef-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="ffdef-104">En este tema se describen los métodos para la recopilación de entradas manuscritas en Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ffdef-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffdef-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ffdef-105">Prerequisites</span></span>

<span data-ttu-id="ffdef-106">Para usar los ejemplos siguientes, primero debe instalar Visual Studio y el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="ffdef-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="ffdef-107">También debe saber cómo escribir aplicaciones para WPF.</span><span class="sxs-lookup"><span data-stu-id="ffdef-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="ffdef-108">Para obtener más información sobre cómo empezar a usar WPF, vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="ffdef-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="ffdef-109">Usar el elemento InkCanvas</span><span class="sxs-lookup"><span data-stu-id="ffdef-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="ffdef-110">El elemento <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> proporciona la manera más fácil de recopilar entradas de lápiz en WPF.</span><span class="sxs-lookup"><span data-stu-id="ffdef-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="ffdef-111">Use un elemento <xref:System.Windows.Controls.InkCanvas> para recibir y Mostrar entradas manuscritas.</span><span class="sxs-lookup"><span data-stu-id="ffdef-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="ffdef-112">Normalmente, la entrada de lápiz se realiza con un lápiz, que interactúa con un digitalizador para generar trazos de lápiz.</span><span class="sxs-lookup"><span data-stu-id="ffdef-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="ffdef-113">También se puede usar un mouse en lugar de un lápiz.</span><span class="sxs-lookup"><span data-stu-id="ffdef-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="ffdef-114">Los trazos creados se representan como objetos <xref:System.Windows.Ink.Stroke> y se pueden manipular mediante programación y mediante la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="ffdef-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="ffdef-115">El <xref:System.Windows.Controls.InkCanvas> permite a los usuarios seleccionar, modificar o eliminar una <xref:System.Windows.Ink.Stroke>existente.</span><span class="sxs-lookup"><span data-stu-id="ffdef-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="ffdef-116">Mediante el uso de XAML, puede configurar la colección de entradas manuscritas tan fácilmente como agregar un elemento **InkCanvas** al árbol.</span><span class="sxs-lookup"><span data-stu-id="ffdef-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="ffdef-117">En el ejemplo siguiente se agrega una <xref:System.Windows.Controls.InkCanvas> a un proyecto de WPF predeterminado creado en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="ffdef-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="ffdef-118">El elemento **InkCanvas** también puede contener elementos secundarios, lo que permite agregar capacidades de anotación manuscrita a casi cualquier tipo de elemento XAML.</span><span class="sxs-lookup"><span data-stu-id="ffdef-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="ffdef-119">Por ejemplo, para agregar capacidades de entrada de lápiz a un elemento de texto, simplemente conviértalo en un elemento secundario de un <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="ffdef-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="ffdef-120">Agregar compatibilidad para marcar una imagen con tinta es igual de fácil:</span><span class="sxs-lookup"><span data-stu-id="ffdef-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="ffdef-121">Modos de InkCollection</span><span class="sxs-lookup"><span data-stu-id="ffdef-121">InkCollection Modes</span></span>

<span data-ttu-id="ffdef-122">El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con varios modos de entrada a través de su propiedad <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffdef-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="ffdef-123">Manipular la entrada manuscrita</span><span class="sxs-lookup"><span data-stu-id="ffdef-123">Manipulate Ink</span></span>

<span data-ttu-id="ffdef-124">El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con muchas operaciones de edición de tinta.</span><span class="sxs-lookup"><span data-stu-id="ffdef-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="ffdef-125">Por ejemplo, <xref:System.Windows.Controls.InkCanvas> admite el borrado de la parte trasera del lápiz y no se necesita ningún código adicional para agregar la funcionalidad al elemento.</span><span class="sxs-lookup"><span data-stu-id="ffdef-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="ffdef-126">Selección</span><span class="sxs-lookup"><span data-stu-id="ffdef-126">Selection</span></span>

<span data-ttu-id="ffdef-127">Establecer el modo de selección es tan sencillo como establecer la propiedad <xref:System.Windows.Controls.InkCanvasEditingMode> en **Select**.</span><span class="sxs-lookup"><span data-stu-id="ffdef-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="ffdef-128">El código siguiente establece el modo de edición basándose en el valor de un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="ffdef-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="ffdef-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="ffdef-129">DrawingAttributes</span></span>

<span data-ttu-id="ffdef-130">Use la propiedad <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> para cambiar la apariencia de los trazos de tinta.</span><span class="sxs-lookup"><span data-stu-id="ffdef-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="ffdef-131">Por ejemplo, el miembro <xref:System.Windows.Ink.DrawingAttributes.Color%2A> de <xref:System.Windows.Ink.DrawingAttributes> establece el color de la <xref:System.Windows.Ink.Stroke>representada.</span><span class="sxs-lookup"><span data-stu-id="ffdef-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="ffdef-132">En el ejemplo siguiente se cambia el color de los trazos seleccionados a rojo:</span><span class="sxs-lookup"><span data-stu-id="ffdef-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="ffdef-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="ffdef-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="ffdef-134">La propiedad <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proporciona acceso a propiedades como el alto, el ancho y el color de los trazos que se van a crear en un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="ffdef-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ffdef-135">Una vez que se cambia el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros especificados en el <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ffdef-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="ffdef-136">Además de modificar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede usar la sintaxis XAML para especificar <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="ffdef-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="ffdef-137">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Ink.DrawingAttributes.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffdef-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="ffdef-138">Para usar este código, cree un nuevo proyecto de WPF denominado "HelloInkCanvas" en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffdef-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="ffdef-139">Reemplace el código del archivo *MainWindow. Xaml* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffdef-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="ffdef-140">A continuación, agregue los siguientes controladores de eventos de botón al archivo de código subyacente, dentro de la clase MainWindow:</span><span class="sxs-lookup"><span data-stu-id="ffdef-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="ffdef-141">Después de copiar este código, presione **F5** en Visual Studio para ejecutar el programa en el depurador.</span><span class="sxs-lookup"><span data-stu-id="ffdef-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="ffdef-142">Observe cómo el <xref:System.Windows.Controls.StackPanel> coloca los botones encima de la <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="ffdef-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ffdef-143">Si intenta realizar una entrada manuscrita sobre la parte superior de los botones, el <xref:System.Windows.Controls.InkCanvas> recopila y representa la tinta detrás de los botones.</span><span class="sxs-lookup"><span data-stu-id="ffdef-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="ffdef-144">Esto se debe a que los botones son del mismo nivel que el <xref:System.Windows.Controls.InkCanvas> en lugar de secundarios.</span><span class="sxs-lookup"><span data-stu-id="ffdef-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="ffdef-145">Además, los botones son superiores en el orden de z, por lo que la entrada de lápiz se representa detrás de ellos.</span><span class="sxs-lookup"><span data-stu-id="ffdef-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffdef-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffdef-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
