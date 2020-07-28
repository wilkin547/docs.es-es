---
title: Información general sobre adornos
description: Obtenga información acerca de los adornos de Windows Presentation Foundation, un tipo especial de FrameworkElement que proporciona indicaciones a un usuario, como los identificadores funcionales de los elementos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 43d4af9f86c6ae72a61f86d1ca19405c2dcc6cc8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167739"
---
# <a name="adorners-overview"></a><span data-ttu-id="8ca94-103">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="8ca94-103">Adorners Overview</span></span>

<span data-ttu-id="8ca94-104">Los adornos son un tipo especial de <xref:System.Windows.FrameworkElement> , que se usa para proporcionar indicaciones visuales a un usuario.</span><span class="sxs-lookup"><span data-stu-id="8ca94-104">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="8ca94-105">Entre otros usos, los Adorners se pueden utilizar para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.</span><span class="sxs-lookup"><span data-stu-id="8ca94-105">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="8ca94-106">Acerca de Adorners</span><span class="sxs-lookup"><span data-stu-id="8ca94-106">About Adorners</span></span>

<span data-ttu-id="8ca94-107"><xref:System.Windows.Documents.Adorner>Es un personalizado <xref:System.Windows.FrameworkElement> que está enlazado a un <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="8ca94-107">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="8ca94-108">Los adornos se representan en un <xref:System.Windows.Documents.AdornerLayer> , que es una superficie de representación que siempre está encima del elemento adornado o una colección de elementos adornados.</span><span class="sxs-lookup"><span data-stu-id="8ca94-108">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="8ca94-109">La representación de un adorno es independiente de la representación de a la <xref:System.Windows.UIElement> que está enlazado el adorno.</span><span class="sxs-lookup"><span data-stu-id="8ca94-109">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="8ca94-110">Normalmente, un adorno se coloca en relación con el elemento al que está enlazado, utilizando el origen de la coordenada 2D estándar situado en la parte superior izquierda del elemento adornado.</span><span class="sxs-lookup"><span data-stu-id="8ca94-110">An adorner is typically positioned relative to the element to which it is bound, using the standard 2D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="8ca94-111">Algunas aplicaciones comunes de adornos son:</span><span class="sxs-lookup"><span data-stu-id="8ca94-111">Common applications for adorners include:</span></span>

- <span data-ttu-id="8ca94-112">Agregar manipuladores funcionales a <xref:System.Windows.UIElement> que permiten a un usuario manipular el elemento de alguna manera (cambiar el tamaño, girar, cambiar de posición, etc.).</span><span class="sxs-lookup"><span data-stu-id="8ca94-112">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="8ca94-113">Proporcionar comentarios visuales para indicar diversos estados, o en respuesta a distintos eventos.</span><span class="sxs-lookup"><span data-stu-id="8ca94-113">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="8ca94-114">Superponer decoraciones visuales en un <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="8ca94-114">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="8ca94-115">Enmascara o invalida visualmente una parte o la totalidad de un <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="8ca94-115">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="8ca94-116">proporciona un marco básico para adornar elementos visuales.</span><span class="sxs-lookup"><span data-stu-id="8ca94-116">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="8ca94-117">En la tabla siguiente se muestra una lista de los tipos principales utilizados al adornar objetos y su finalidad.</span><span class="sxs-lookup"><span data-stu-id="8ca94-117">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="8ca94-118">A continuación se muestran varios ejemplos de uso:</span><span class="sxs-lookup"><span data-stu-id="8ca94-118">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="8ca94-119">Una clase base abstracta de la que heredan todas las implementaciones de adornos contextuales concretas.</span><span class="sxs-lookup"><span data-stu-id="8ca94-119">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="8ca94-120">Una clase que representa una capa de representación para los adornos de uno o más elementos adornados.</span><span class="sxs-lookup"><span data-stu-id="8ca94-120">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="8ca94-121">Una clase que permite asociar una capa de adornos a una colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="8ca94-121">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="8ca94-122">Implementación de un adorno personalizado</span><span class="sxs-lookup"><span data-stu-id="8ca94-122">Implementing a Custom Adorner</span></span>

<span data-ttu-id="8ca94-123">El marco de adornos que proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado principalmente para admitir la creación de adornos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8ca94-123">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="8ca94-124">Un adorno personalizado se crea implementando una clase que hereda de la <xref:System.Windows.Documents.Adorner> clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="8ca94-124">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="8ca94-125">El elemento primario de <xref:System.Windows.Documents.Adorner> es el <xref:System.Windows.Documents.AdornerLayer> que representa el <xref:System.Windows.Documents.Adorner> , no el elemento que se va a adornar.</span><span class="sxs-lookup"><span data-stu-id="8ca94-125">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="8ca94-126">En el ejemplo siguiente se muestra una clase que implementa un adorno simple.</span><span class="sxs-lookup"><span data-stu-id="8ca94-126">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="8ca94-127">El adorno de ejemplo simplemente adorna las esquinas de un <xref:System.Windows.UIElement> con círculos.</span><span class="sxs-lookup"><span data-stu-id="8ca94-127">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="8ca94-128">En la imagen siguiente se muestra el adorno simplecircleadorner aplicado a un <xref:System.Windows.Controls.TextBox> :</span><span class="sxs-lookup"><span data-stu-id="8ca94-128">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![Captura de pantalla que muestra un cuadro de texto adornado.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="8ca94-130">Comportamiento de representación de los adornos</span><span class="sxs-lookup"><span data-stu-id="8ca94-130">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="8ca94-131">Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.</span><span class="sxs-lookup"><span data-stu-id="8ca94-131">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="8ca94-132">Una manera común de implementar el comportamiento de representación es invalidar el <xref:System.Windows.UIElement.OnRender%2A> método y usar uno o varios <xref:System.Windows.Media.DrawingContext> objetos para representar los elementos visuales del adorno según sea necesario (como se muestra en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="8ca94-132">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="8ca94-133">Todo aquello que se coloca en la capa de los adornos se representa encima del resto de estilos que se han establecido.</span><span class="sxs-lookup"><span data-stu-id="8ca94-133">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="8ca94-134">En otras palabras, los adornos siempre están visualmente encima y no pueden invalidar utilizando el orden z.</span><span class="sxs-lookup"><span data-stu-id="8ca94-134">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="8ca94-135">Eventos y pruebas de posicionamiento</span><span class="sxs-lookup"><span data-stu-id="8ca94-135">Events and Hit Testing</span></span>

<span data-ttu-id="8ca94-136">Los adornos reciben eventos de entrada como cualquier otro <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="8ca94-136">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="8ca94-137">Dado que un adorno siempre tiene un orden z mayor que el elemento que adorna, el adorno recibe eventos de entrada (como <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove> ) que pueden estar destinados al elemento adornado subyacente.</span><span class="sxs-lookup"><span data-stu-id="8ca94-137">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="8ca94-138">Un adorno puede realizar escuchas para ciertos eventos de entrada y pasárselos al elemento adornado subyacente volviendo a provocar el evento.</span><span class="sxs-lookup"><span data-stu-id="8ca94-138">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="8ca94-139">Para habilitar la prueba de posicionamiento de paso a través de los elementos de un adorno, establezca la propiedad de la prueba de posicionamiento en <xref:System.Windows.UIElement.IsHitTestVisible%2A> **false** en el adorno.</span><span class="sxs-lookup"><span data-stu-id="8ca94-139">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="8ca94-140">Para obtener más información sobre las pruebas de posicionamiento, vea [pruebas de posicionamiento en la capa visual](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="8ca94-140">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="8ca94-141">Adorno de un solo elemento de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8ca94-141">Adorning a Single UIElement</span></span>

<span data-ttu-id="8ca94-142">Para enlazar un adorno a un determinado <xref:System.Windows.UIElement> , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8ca94-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="8ca94-143">Llame al método estático <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un <xref:System.Windows.Documents.AdornerLayer> objeto para el <xref:System.Windows.UIElement> que se va a adornar.</span><span class="sxs-lookup"><span data-stu-id="8ca94-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="8ca94-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>avanza el árbol visual, comenzando en el especificado <xref:System.Windows.UIElement> , y devuelve la primera capa de adornos que encuentra.</span><span class="sxs-lookup"><span data-stu-id="8ca94-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="8ca94-145">(Si no se encuentra ninguna capa de adornos, el método devuelve null).</span><span class="sxs-lookup"><span data-stu-id="8ca94-145">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="8ca94-146">Llame al <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar el adorno al destino <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="8ca94-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="8ca94-147">En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a un <xref:System.Windows.Controls.TextBox> denominado *mytextbox*:</span><span class="sxs-lookup"><span data-stu-id="8ca94-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="8ca94-148">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="8ca94-148">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="8ca94-149">Adornamiento de elementos secundarios de un panel</span><span class="sxs-lookup"><span data-stu-id="8ca94-149">Adorning the Children of a Panel</span></span>

<span data-ttu-id="8ca94-150">Para enlazar un adorno a los elementos secundarios de <xref:System.Windows.Controls.Panel> , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8ca94-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="8ca94-151">Llame al `static` método <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a adornar.</span><span class="sxs-lookup"><span data-stu-id="8ca94-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="8ca94-152">Enumere los elementos secundarios del elemento primario y llame al <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="8ca94-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="8ca94-153">En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a los elementos secundarios de un <xref:System.Windows.Controls.StackPanel> *myStackPanel*con nombre:</span><span class="sxs-lookup"><span data-stu-id="8ca94-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="8ca94-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ca94-154">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="8ca94-155">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="8ca94-155">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="8ca94-156">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="8ca94-156">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="8ca94-157">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="8ca94-157">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="8ca94-158">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="8ca94-158">How-to Topics</span></span>](adorners-how-to-topics.md)
