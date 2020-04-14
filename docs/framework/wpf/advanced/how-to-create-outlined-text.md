---
title: 'Cómo: Crear texto con contorno'
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
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278930"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="ea00d-102">Cómo: Crear texto esbozado</span><span class="sxs-lookup"><span data-stu-id="ea00d-102">How to: Create outlined text</span></span>

<span data-ttu-id="ea00d-103">En la mayoría de los casos, cuando se [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] agrega ornamentación a cadenas de texto en la aplicación, se utiliza texto en términos de una colección de caracteres discretos o pictogramas.</span><span class="sxs-lookup"><span data-stu-id="ea00d-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="ea00d-104">Por ejemplo, podría crear un pincel de <xref:System.Windows.Controls.Control.Foreground%2A> degradado lineal <xref:System.Windows.Controls.TextBox> y aplicarlo a la propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="ea00d-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="ea00d-105">Al mostrar o editar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="ea00d-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Texto que se muestra con un pincel de degradado lineal](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="ea00d-107">Sin embargo, también <xref:System.Windows.Media.Geometry> puede convertir texto en objetos, lo que le permite crear otros tipos de texto visualmente enriquecido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="ea00d-108">Por ejemplo, podría <xref:System.Windows.Media.Geometry> crear un objeto basado en el contorno de una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="ea00d-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="ea00d-110">Cuando el texto <xref:System.Windows.Media.Geometry> se convierte en un objeto, ya no es una colección de caracteres: no se pueden modificar los caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="ea00d-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="ea00d-111">Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno.</span><span class="sxs-lookup"><span data-stu-id="ea00d-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="ea00d-112">El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="ea00d-113">Los siguientes ejemplos ilustran varias formas de crear efectos visuales modificando el trazo y el relleno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Texto con colores diferentes para relleno y trazo](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="ea00d-116">También es posible modificar el rectángulo del cuadro delimitador, o resaltar, del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="ea00d-117">En el ejemplo siguiente se muestra una forma de crear efectos visuales modificando el trazo y el resaltado del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Texto con pincel de imagen aplicado al trazo y resaltado](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="ea00d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea00d-119">Example</span></span>  
 <span data-ttu-id="ea00d-120">La clave para convertir <xref:System.Windows.Media.Geometry> texto en un <xref:System.Windows.Media.FormattedText> objeto es utilizar el objeto.</span><span class="sxs-lookup"><span data-stu-id="ea00d-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="ea00d-121">Una vez creado este objeto, <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> puede <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> utilizar los métodos y para convertir el texto en <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="ea00d-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="ea00d-122">El primer método devuelve la geometría del texto con formato; el segundo método devuelve la geometría del cuadro delimitador del texto con formato.</span><span class="sxs-lookup"><span data-stu-id="ea00d-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="ea00d-123">En el ejemplo de código <xref:System.Windows.Media.FormattedText> siguiente se muestra cómo crear un objeto y recuperar las geometrías del texto con formato y su cuadro delimitador.</span><span class="sxs-lookup"><span data-stu-id="ea00d-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="ea00d-124">Para mostrar los <xref:System.Windows.Media.Geometry> objetos recuperados, debe <xref:System.Windows.Media.DrawingContext> tener acceso al objeto que muestra el texto convertido.</span><span class="sxs-lookup"><span data-stu-id="ea00d-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="ea00d-125">En estos ejemplos de código, este acceso se logra mediante la creación de un objeto de control personalizado que se deriva de una clase que admite la representación definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea00d-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="ea00d-126">Para <xref:System.Windows.Media.Geometry> mostrar objetos en el control <xref:System.Windows.UIElement.OnRender%2A> personalizado, proporcione una invalidación para el método.</span><span class="sxs-lookup"><span data-stu-id="ea00d-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="ea00d-127">El método invalidado <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> debe usar <xref:System.Windows.Media.Geometry> el método para dibujar los objetos.</span><span class="sxs-lookup"><span data-stu-id="ea00d-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="ea00d-128">Para obtener el origen del objeto de control de usuario personalizado de ejemplo, vea [OutlineTextControl.cs para C-](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) y [OutlineTextControl.vb para Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span><span class="sxs-lookup"><span data-stu-id="ea00d-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea00d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea00d-129">See also</span></span>

- [<span data-ttu-id="ea00d-130">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="ea00d-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
