---
title: "Cómo: Crear texto con contorno"
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
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41254d8f93174c896923b1c070e6bf9b5b7c863c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="f18eb-102">Cómo: Crear texto con contorno</span><span class="sxs-lookup"><span data-stu-id="f18eb-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="f18eb-103">En la mayoría de los casos, al agregar ornamentación a las cadenas de texto en su [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación, se utiliza el texto considerándolo una colección de caracteres discretos, o glifos.</span><span class="sxs-lookup"><span data-stu-id="f18eb-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="f18eb-104">Por ejemplo, podría crear un pincel de degradado lineal y aplicarlo a la <xref:System.Windows.Controls.Control.Foreground%2A> propiedad de un <xref:System.Windows.Controls.TextBox> objeto.</span><span class="sxs-lookup"><span data-stu-id="f18eb-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="f18eb-105">Al mostrar o editar el cuadro de texto, el pincel de degradado lineal se aplica automáticamente al conjunto actual de caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="f18eb-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 <span data-ttu-id="f18eb-106">![Texto mostrado con un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span><span class="sxs-lookup"><span data-stu-id="f18eb-106">![Text displayed with a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span></span>  
<span data-ttu-id="f18eb-107">Ejemplo de un pincel de degradado lineal que se aplica a un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="f18eb-107">Example of a linear gradient brush applied to a text box</span></span>  
  
 <span data-ttu-id="f18eb-108">Sin embargo, también puede convertir texto en <xref:System.Windows.Media.Geometry> objetos, lo que le permite crear otros tipos de texto visualmente enriquecido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-108">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="f18eb-109">Por ejemplo, podría crear un <xref:System.Windows.Media.Geometry> objeto basado en el esquema de una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="f18eb-109">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 <span data-ttu-id="f18eb-110">![Contorno al texto mediante un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span><span class="sxs-lookup"><span data-stu-id="f18eb-110">![Text outline using a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span></span>  
<span data-ttu-id="f18eb-111">Ejemplo de un pincel de degradado lineal que se aplica a la geometría del contorno del texto</span><span class="sxs-lookup"><span data-stu-id="f18eb-111">Example of a linear gradient brush applied to the outline geometry of text</span></span>  
  
 <span data-ttu-id="f18eb-112">Cuando el texto se convierte en un <xref:System.Windows.Media.Geometry> de objeto, ya no es una colección de caracteres, no se puede modificar los caracteres de la cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="f18eb-112">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="f18eb-113">Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno.</span><span class="sxs-lookup"><span data-stu-id="f18eb-113">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="f18eb-114">El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-114">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="f18eb-115">Los ejemplos siguientes ilustran varias maneras de crear efectos visuales modificando el trazo y el relleno del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-115">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 <span data-ttu-id="f18eb-116">![Texto con colores diferentes para relleno y trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span><span class="sxs-lookup"><span data-stu-id="f18eb-116">![Text with different colors for fill and stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span></span>  
<span data-ttu-id="f18eb-117">Ejemplo de configuración de relleno y trazo en diferentes colores</span><span class="sxs-lookup"><span data-stu-id="f18eb-117">Example of setting stroke and fill to different colors</span></span>  
  
 <span data-ttu-id="f18eb-118">![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span><span class="sxs-lookup"><span data-stu-id="f18eb-118">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span></span>  
<span data-ttu-id="f18eb-119">Ejemplo de pincel de imagen aplicado al trazo</span><span class="sxs-lookup"><span data-stu-id="f18eb-119">Example of an image brush applied to the stroke</span></span>  
  
 <span data-ttu-id="f18eb-120">También es posible modificar el rectángulo delimitador o el resaltado del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-120">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="f18eb-121">En el ejemplo siguiente se muestra una manera de crear efectos visuales modificando el trazo y el resaltado del texto convertido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-121">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 <span data-ttu-id="f18eb-122">![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span><span class="sxs-lookup"><span data-stu-id="f18eb-122">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span></span>  
<span data-ttu-id="f18eb-123">Ejemplo de pincel de imagen aplicado al trazo y el resaltado</span><span class="sxs-lookup"><span data-stu-id="f18eb-123">Example of an image brush applied to the stroke and highlight</span></span>  
  
## <a name="example"></a><span data-ttu-id="f18eb-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f18eb-124">Example</span></span>  
 <span data-ttu-id="f18eb-125">La clave para convertir texto en una <xref:System.Windows.Media.Geometry> objeto consiste en usar la <xref:System.Windows.Media.FormattedText> objeto.</span><span class="sxs-lookup"><span data-stu-id="f18eb-125">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="f18eb-126">Una vez que ha creado este objeto, puede usar el <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> y <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> métodos para convertir el texto en <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="f18eb-126">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="f18eb-127">El primer método devuelve la geometría del texto con formato; el segundo método devuelve que la geometría del texto con formato del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="f18eb-127">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="f18eb-128">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Media.FormattedText> objeto y recuperar las geometrías del texto con formato y su cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="f18eb-128">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="f18eb-129">Para mostrar el objeto recuperado el <xref:System.Windows.Media.Geometry> objetos, necesita tener acceso a la <xref:System.Windows.Media.DrawingContext> del objeto que se muestra el texto convertido.</span><span class="sxs-lookup"><span data-stu-id="f18eb-129">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="f18eb-130">En estos ejemplos de código, esto se realiza mediante la creación de un objeto de control personalizado que se deriva de una clase que admite el procesamiento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f18eb-130">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="f18eb-131">Para mostrar <xref:System.Windows.Media.Geometry> objetos en el control personalizado, proporcione un nombre para invalidar el <xref:System.Windows.UIElement.OnRender%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f18eb-131">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="f18eb-132">Debe usar el método invalidado la <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> método para dibujar el <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="f18eb-132">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a><span data-ttu-id="f18eb-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f18eb-133">See Also</span></span>  
 [<span data-ttu-id="f18eb-134">Dibujar texto con formato</span><span class="sxs-lookup"><span data-stu-id="f18eb-134">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
