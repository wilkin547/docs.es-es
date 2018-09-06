---
title: Recopilar entradas de lápiz en aplicaciones WPF
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
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787449"
---
# <a name="collect-ink"></a><span data-ttu-id="ec49d-102">Recopilar entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="ec49d-102">Collect Ink</span></span>

<span data-ttu-id="ec49d-103">La plataforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) recopila entradas de lápiz digitales como parte esencial de su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ec49d-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="ec49d-104">En este tema se describe métodos para la recopilación de tinta en Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ec49d-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec49d-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec49d-105">Prerequisites</span></span>

<span data-ttu-id="ec49d-106">Para usar los ejemplos siguientes, debe instalar primero Visual Studio y el [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec49d-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="ec49d-107">También debe entender cómo escribir aplicaciones para WPF.</span><span class="sxs-lookup"><span data-stu-id="ec49d-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="ec49d-108">Para obtener más información acerca de la introducción a WPF, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="ec49d-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="ec49d-109">Utilice el elemento InkCanvas</span><span class="sxs-lookup"><span data-stu-id="ec49d-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="ec49d-110">El <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento proporciona la manera más fácil de recopilar entradas de lápiz en WPF.</span><span class="sxs-lookup"><span data-stu-id="ec49d-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="ec49d-111">Use un <xref:System.Windows.Controls.InkCanvas> elemento para recibir y mostrar entradas de lápiz.</span><span class="sxs-lookup"><span data-stu-id="ec49d-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="ec49d-112">Normalmente, la entrada de lápiz se realiza con un lápiz, que interactúa con un digitalizador para generar trazos de lápiz.</span><span class="sxs-lookup"><span data-stu-id="ec49d-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="ec49d-113">También se puede usar un mouse en lugar de un lápiz.</span><span class="sxs-lookup"><span data-stu-id="ec49d-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="ec49d-114">Los trazos creados se representan como <xref:System.Windows.Ink.Stroke> objetos y se pueden manipular mediante programación y por el usuario de entrada.</span><span class="sxs-lookup"><span data-stu-id="ec49d-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="ec49d-115">El <xref:System.Windows.Controls.InkCanvas> permite a los usuarios seleccionar, modificar o eliminar una existente <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="ec49d-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="ec49d-116">Mediante el uso de XAML, puede configurar la recopilación de tinta tan fácilmente como agregar un **InkCanvas** elemento al árbol.</span><span class="sxs-lookup"><span data-stu-id="ec49d-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="ec49d-117">En el ejemplo siguiente se agrega un <xref:System.Windows.Controls.InkCanvas> a un proyecto WPF predeterminado creado en Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="ec49d-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="ec49d-118">El **InkCanvas** elemento también puede contener elementos secundarios, lo que permite agregar funcionalidades de anotación de tinta a casi cualquier tipo de elemento XAML.</span><span class="sxs-lookup"><span data-stu-id="ec49d-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="ec49d-119">Por ejemplo, para agregar capacidades de tinta a un elemento de texto, simplemente convertirlo en un elemento secundario de un <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="ec49d-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="ec49d-120">Agregar compatibilidad para marcar una imagen con tinta es igual de fácil:</span><span class="sxs-lookup"><span data-stu-id="ec49d-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="ec49d-121">Modos de InkCollection</span><span class="sxs-lookup"><span data-stu-id="ec49d-121">InkCollection Modes</span></span>

<span data-ttu-id="ec49d-122">El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con varios modos a través de la entrada su <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec49d-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="ec49d-123">Manipular entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="ec49d-123">Manipulate Ink</span></span>

<span data-ttu-id="ec49d-124">El <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con muchas operaciones de edición de tinta.</span><span class="sxs-lookup"><span data-stu-id="ec49d-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="ec49d-125">Por ejemplo, <xref:System.Windows.Controls.InkCanvas> borrar admite back del lápiz, y no es necesario ningún código adicional para agregar la funcionalidad para el elemento.</span><span class="sxs-lookup"><span data-stu-id="ec49d-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="ec49d-126">Selección</span><span class="sxs-lookup"><span data-stu-id="ec49d-126">Selection</span></span>

<span data-ttu-id="ec49d-127">Establecer el modo de selección es tan sencillo como la configuración de la <xref:System.Windows.Controls.InkCanvasEditingMode> propiedad **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="ec49d-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="ec49d-128">El código siguiente establece el modo de edición en función del valor de un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="ec49d-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="ec49d-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="ec49d-129">DrawingAttributes</span></span>

<span data-ttu-id="ec49d-130">Use el <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propiedad para cambiar la apariencia de los trazos de tinta.</span><span class="sxs-lookup"><span data-stu-id="ec49d-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="ec49d-131">Por ejemplo, el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> miembro de <xref:System.Windows.Ink.DrawingAttributes> establece el color de la representado <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="ec49d-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="ec49d-132">El ejemplo siguiente cambia el color de los trazos seleccionados a rojo:</span><span class="sxs-lookup"><span data-stu-id="ec49d-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="ec49d-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="ec49d-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="ec49d-134">El <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedad proporciona acceso a propiedades como el alto, ancho y color de los trazos que se creará en un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="ec49d-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ec49d-135">Una vez que cambie el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros que se celebra el <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec49d-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="ec49d-136">Además de modificar el <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede usar sintaxis XAML para especificar <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="ec49d-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="ec49d-137">En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Ink.DrawingAttributes.Color%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec49d-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="ec49d-138">Para usar este código, cree un nuevo proyecto WPF denominado "HelloInkCanvas" en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec49d-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="ec49d-139">Reemplace el código en el *MainWindow.xaml* archivo con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec49d-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="ec49d-140">A continuación, agregue los siguientes controladores de eventos de botón en el archivo de código subyacente, dentro de la clase MainWindow:</span><span class="sxs-lookup"><span data-stu-id="ec49d-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="ec49d-141">Después de copiar este código, presione **F5** en Visual Studio para ejecutar el programa en el depurador.</span><span class="sxs-lookup"><span data-stu-id="ec49d-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="ec49d-142">Observe cómo el <xref:System.Windows.Controls.StackPanel> coloca los botones en la parte superior de la <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="ec49d-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ec49d-143">Si trata de entrada de lápiz encima de los botones, el <xref:System.Windows.Controls.InkCanvas> recopila y procesa la entrada de lápiz detrás de los botones.</span><span class="sxs-lookup"><span data-stu-id="ec49d-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="ec49d-144">Esto es porque los botones están relacionados con el <xref:System.Windows.Controls.InkCanvas> en lugar de los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ec49d-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="ec49d-145">Además, los botones son superiores en el orden de z, por lo que la entrada de lápiz se representa detrás de ellos.</span><span class="sxs-lookup"><span data-stu-id="ec49d-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec49d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec49d-146">See Also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>