---
title: Información general sobre adornos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111184"
---
# <a name="adorners-overview"></a><span data-ttu-id="a5de5-102">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="a5de5-102">Adorners Overview</span></span>

<span data-ttu-id="a5de5-103">Los adornos son <xref:System.Windows.FrameworkElement>un tipo especial de , que se utiliza para proporcionar señales visuales a un usuario.</span><span class="sxs-lookup"><span data-stu-id="a5de5-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="a5de5-104">Entre otros usos, los Adorners se pueden utilizar para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.</span><span class="sxs-lookup"><span data-stu-id="a5de5-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="a5de5-105">Acerca de Adorners</span><span class="sxs-lookup"><span data-stu-id="a5de5-105">About Adorners</span></span>

<span data-ttu-id="a5de5-106">Un <xref:System.Windows.Documents.Adorner> es <xref:System.Windows.FrameworkElement> una costumbre que <xref:System.Windows.UIElement>está enlazada a un archivo .</span><span class="sxs-lookup"><span data-stu-id="a5de5-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="a5de5-107">Los adornos se <xref:System.Windows.Documents.AdornerLayer>representan en un , que es una superficie de representación que siempre está encima del elemento adornado o una colección de elementos adornados.</span><span class="sxs-lookup"><span data-stu-id="a5de5-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="a5de5-108">La representación de un adorno <xref:System.Windows.UIElement> es independiente de la representación de la que está enlazado el adorno.</span><span class="sxs-lookup"><span data-stu-id="a5de5-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="a5de5-109">Normalmente, un adorno se coloca en relación con el elemento al que está enlazado, utilizando el origen de coordenadas 2D estándar situado en la parte superior izquierda del elemento adornado.</span><span class="sxs-lookup"><span data-stu-id="a5de5-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="a5de5-110">Algunas aplicaciones comunes de adornos son:</span><span class="sxs-lookup"><span data-stu-id="a5de5-110">Common applications for adorners include:</span></span>

- <span data-ttu-id="a5de5-111">Agregar identificadores <xref:System.Windows.UIElement> funcionales a un que permiten a un usuario manipular el elemento de alguna manera (cambiar el tamaño, rotar, cambiar la posición, etc.).</span><span class="sxs-lookup"><span data-stu-id="a5de5-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="a5de5-112">Proporcionar comentarios visuales para indicar diversos estados, o en respuesta a distintos eventos.</span><span class="sxs-lookup"><span data-stu-id="a5de5-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="a5de5-113">Superponer decoraciones <xref:System.Windows.UIElement>visuales en un archivo .</span><span class="sxs-lookup"><span data-stu-id="a5de5-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="a5de5-114">Enmascarar visualmente o reemplazar parte <xref:System.Windows.UIElement>o la totalidad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="a5de5-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="a5de5-115">proporciona un marco básico para adornar elementos visuales.</span><span class="sxs-lookup"><span data-stu-id="a5de5-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="a5de5-116">En la tabla siguiente se muestra una lista de los tipos principales utilizados al adornar objetos y su finalidad.</span><span class="sxs-lookup"><span data-stu-id="a5de5-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="a5de5-117">A continuación se muestran varios ejemplos de uso:</span><span class="sxs-lookup"><span data-stu-id="a5de5-117">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="a5de5-118">Una clase base abstracta de la que heredan todas las implementaciones de adornos contextuales concretas.</span><span class="sxs-lookup"><span data-stu-id="a5de5-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="a5de5-119">Una clase que representa una capa de representación para los adornos de uno o más elementos adornados.</span><span class="sxs-lookup"><span data-stu-id="a5de5-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="a5de5-120">Una clase que permite asociar una capa de adornos a una colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="a5de5-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="a5de5-121">Implementación de un adorno personalizado</span><span class="sxs-lookup"><span data-stu-id="a5de5-121">Implementing a Custom Adorner</span></span>

<span data-ttu-id="a5de5-122">El marco de adornos que proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado principalmente para admitir la creación de adornos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a5de5-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="a5de5-123">Un adorno personalizado se crea mediante la implementación de una clase que hereda de la clase abstracta. <xref:System.Windows.Documents.Adorner></span><span class="sxs-lookup"><span data-stu-id="a5de5-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="a5de5-124">El elemento <xref:System.Windows.Documents.Adorner> primario <xref:System.Windows.Documents.AdornerLayer> de un <xref:System.Windows.Documents.Adorner>es el que representa el , no el elemento que se está adornando.</span><span class="sxs-lookup"><span data-stu-id="a5de5-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="a5de5-125">En el ejemplo siguiente se muestra una clase que implementa un adorno simple.</span><span class="sxs-lookup"><span data-stu-id="a5de5-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="a5de5-126">El adorno de ejemplo simplemente <xref:System.Windows.UIElement> adorna las esquinas de un con círculos.</span><span class="sxs-lookup"><span data-stu-id="a5de5-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="a5de5-127">La siguiente imagen muestra el SimpleCircleAdorner aplicado a un <xref:System.Windows.Controls.TextBox>:</span><span class="sxs-lookup"><span data-stu-id="a5de5-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![Captura de pantalla que muestra un cuadro de texto adornado.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="a5de5-129">Comportamiento de representación de los adornos</span><span class="sxs-lookup"><span data-stu-id="a5de5-129">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="a5de5-130">Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.</span><span class="sxs-lookup"><span data-stu-id="a5de5-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="a5de5-131">Una forma común de implementar el <xref:System.Windows.UIElement.OnRender%2A> comportamiento de representación es invalidar el método y usar uno o varios <xref:System.Windows.Media.DrawingContext> objetos para representar los objetos visuales del adorno según sea necesario (como se muestra en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="a5de5-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="a5de5-132">Todo aquello que se coloca en la capa de los adornos se representa encima del resto de estilos que se han establecido.</span><span class="sxs-lookup"><span data-stu-id="a5de5-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="a5de5-133">En otras palabras, los adornos siempre están visualmente encima y no pueden invalidar utilizando el orden z.</span><span class="sxs-lookup"><span data-stu-id="a5de5-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="a5de5-134">Eventos y pruebas de posicionamiento</span><span class="sxs-lookup"><span data-stu-id="a5de5-134">Events and Hit Testing</span></span>

<span data-ttu-id="a5de5-135">Los adornos reciben eventos <xref:System.Windows.FrameworkElement>de entrada como cualquier otro .</span><span class="sxs-lookup"><span data-stu-id="a5de5-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="a5de5-136">Dado que un adorno siempre tiene un orden z más alto que el elemento <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>que adorna, el adorno recibe eventos de entrada (como o ) que pueden estar pensados para el elemento adornado subyacente.</span><span class="sxs-lookup"><span data-stu-id="a5de5-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="a5de5-137">Un adorno puede realizar escuchas para ciertos eventos de entrada y pasárselos al elemento adornado subyacente volviendo a provocar el evento.</span><span class="sxs-lookup"><span data-stu-id="a5de5-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="a5de5-138">Para habilitar la prueba de posicionación de paso a <xref:System.Windows.UIElement.IsHitTestVisible%2A> través de elementos debajo de un adorno, establezca la propiedad de prueba de posicionación en **false** en el adorno.</span><span class="sxs-lookup"><span data-stu-id="a5de5-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="a5de5-139">Para obtener más información acerca de las pruebas de posicionamiento, consulte Pruebas de [posicionamiento en la capa visual](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="a5de5-139">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="a5de5-140">Adorno de un solo elemento de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a5de5-140">Adorning a Single UIElement</span></span>

<span data-ttu-id="a5de5-141">Para enlazar un adorno <xref:System.Windows.UIElement>a un adorno determinado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5de5-141">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="a5de5-142">Llame al <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método estático <xref:System.Windows.Documents.AdornerLayer> para <xref:System.Windows.UIElement> obtener un objeto para que se va a adornar.</span><span class="sxs-lookup"><span data-stu-id="a5de5-142">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="a5de5-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>camina por el árbol visual, comenzando en el <xref:System.Windows.UIElement>, y devuelve la primera capa de adorno que encuentra.</span><span class="sxs-lookup"><span data-stu-id="a5de5-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="a5de5-144">(Si no se encuentra ninguna capa de adornos, el método devuelve null).</span><span class="sxs-lookup"><span data-stu-id="a5de5-144">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="a5de5-145">Llame <xref:System.Windows.Documents.AdornerLayer.Add%2A> al método para enlazar el <xref:System.Windows.UIElement>adorno al destino .</span><span class="sxs-lookup"><span data-stu-id="a5de5-145">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="a5de5-146">En el ejemplo siguiente se enlaza un SimpleCircleAdorner (mostrado arriba) a un <xref:System.Windows.Controls.TextBox> *myTextBox*con nombre:</span><span class="sxs-lookup"><span data-stu-id="a5de5-146">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="a5de5-147">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="a5de5-147">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="a5de5-148">Adornamiento de elementos secundarios de un panel</span><span class="sxs-lookup"><span data-stu-id="a5de5-148">Adorning the Children of a Panel</span></span>

<span data-ttu-id="a5de5-149">Para enlazar un adorno a <xref:System.Windows.Controls.Panel>los hijos de un , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5de5-149">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="a5de5-150">Llame `static` al <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método para buscar una capa de adorno para el elemento cuyos elementos secundarios se van a adornar.</span><span class="sxs-lookup"><span data-stu-id="a5de5-150">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="a5de5-151">Enumerar a través de los elementos secundarios del elemento primario y llamar al <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="a5de5-151">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="a5de5-152">En el ejemplo siguiente se enlaza un SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> (mostrado arriba) a los elementos secundarios de un *myStackPanel*con nombre:</span><span class="sxs-lookup"><span data-stu-id="a5de5-152">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="a5de5-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5de5-153">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="a5de5-154">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="a5de5-154">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="a5de5-155">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="a5de5-155">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="a5de5-156">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="a5de5-156">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="a5de5-157">Temas de información</span><span class="sxs-lookup"><span data-stu-id="a5de5-157">How-to Topics</span></span>](adorners-how-to-topics.md)
