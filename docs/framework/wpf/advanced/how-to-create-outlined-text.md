---
title: Filtrar Crear texto con contorno
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 5de1068401dac61c5de5b86604da9417e18a94ae
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125946"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="6ea10-102">Filtrar Crear texto con contorno</span><span class="sxs-lookup"><span data-stu-id="6ea10-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="6ea10-103">En la mayoría de los casos, cuando se agregan adorno a cadenas de texto en su [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación, que usa texto en términos de una colección de caracteres discretos, o glifos.</span><span class="sxs-lookup"><span data-stu-id="6ea10-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="6ea10-104">Por ejemplo, podría crear un pincel de degradado lineal y se aplicará la <xref:System.Windows.Controls.Control.Foreground%2A> propiedad de un <xref:System.Windows.Controls.TextBox> objeto.</span><span class="sxs-lookup"><span data-stu-id="6ea10-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="6ea10-105">Al mostrar o editar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="6ea10-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Texto que se muestra con un pincel de degradado lineal](./media/how-to-create-outlined-text/text-linear-gradient.jpg)    
  
 <span data-ttu-id="6ea10-107">Sin embargo, también puede convertir texto en <xref:System.Windows.Media.Geometry> objetos, lo que permite crear otros tipos de texto enriquecido visualmente.</span><span class="sxs-lookup"><span data-stu-id="6ea10-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="6ea10-108">Por ejemplo, podría crear un <xref:System.Windows.Media.Geometry> objeto basado en el esquema de una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="6ea10-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="6ea10-110">Cuando el texto se convierte en un <xref:System.Windows.Media.Geometry> de objeto, ya no es una colección de caracteres, no se puede modificar los caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="6ea10-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="6ea10-111">Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno.</span><span class="sxs-lookup"><span data-stu-id="6ea10-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="6ea10-112">El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="6ea10-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="6ea10-113">Los ejemplos siguientes ilustran varias maneras de crear efectos visuales modificando el trazo y el relleno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="6ea10-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Texto con colores diferentes para relleno y trazo](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="6ea10-116">También es posible modificar el rectángulo delimitador, o el resaltado del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="6ea10-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="6ea10-117">El ejemplo siguiente muestra una manera de crear efectos visuales modificando el trazo y el resaltado del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="6ea10-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Texto con pincel de imagen aplicado para trazar y resaltar](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="6ea10-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ea10-119">Example</span></span>  
 <span data-ttu-id="6ea10-120">La clave para convertir texto a un <xref:System.Windows.Media.Geometry> objeto consiste en usar el <xref:System.Windows.Media.FormattedText> objeto.</span><span class="sxs-lookup"><span data-stu-id="6ea10-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="6ea10-121">Una vez que ha creado este objeto, puede usar el <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> y <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> métodos para convertir el texto en <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="6ea10-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="6ea10-122">El primer método devuelve la geometría del texto con formato; el segundo método devuelve que el cuadro de límite de la geometría del texto con formato.</span><span class="sxs-lookup"><span data-stu-id="6ea10-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="6ea10-123">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Media.FormattedText> objeto y recuperar las geometrías de texto con formato y su rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="6ea10-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="6ea10-124">Para mostrar el objeto recuperado el <xref:System.Windows.Media.Geometry> objetos, debe tener acceso a la <xref:System.Windows.Media.DrawingContext> del objeto que se muestra el texto convertido.</span><span class="sxs-lookup"><span data-stu-id="6ea10-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="6ea10-125">En estos ejemplos de código, esto se hace mediante la creación de un objeto de control personalizado que se deriva de una clase que admite el procesamiento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6ea10-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="6ea10-126">Para mostrar <xref:System.Windows.Media.Geometry> objetos en el control personalizado, proporcione una invalidación para el <xref:System.Windows.UIElement.OnRender%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6ea10-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="6ea10-127">Debe usar el método invalidado la <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> método para dibujar el <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="6ea10-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="6ea10-128">Para el origen del objeto de control de usuario personalizado de ejemplo, vea [OutlineTextControl.cs para C# ](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) y [OutlineTextControl.vb para Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span><span class="sxs-lookup"><span data-stu-id="6ea10-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6ea10-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ea10-129">See also</span></span>
- [<span data-ttu-id="6ea10-130">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="6ea10-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
