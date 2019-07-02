---
title: Utilizar fuentes y texto
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505109"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="6034f-102">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="6034f-102">Using Fonts and Text</span></span>
<span data-ttu-id="6034f-103">Hay varias clases proporcionadas por GDI + y GDI para dibujar texto en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6034f-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="6034f-104">GDI + <xref:System.Drawing.Graphics> clase tiene varias <xref:System.Drawing.Graphics.DrawString%2A> métodos que le permiten especificar diversas características de texto, como la ubicación, el rectángulo delimitador, fuentes y formato.</span><span class="sxs-lookup"><span data-stu-id="6034f-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="6034f-105">Además, puede dibujar y medir el texto con GDI mediante estático <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> métodos que ofrece el `TextRenderer` clase.</span><span class="sxs-lookup"><span data-stu-id="6034f-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="6034f-106">Los métodos GDI también permiten especificar la ubicación, la fuente y el formato.</span><span class="sxs-lookup"><span data-stu-id="6034f-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="6034f-107">Puede elegir GDI o GDI + para la representación de texto; Sin embargo, GDI generalmente ofrece un mejor rendimiento y la medición de texto más precisa.</span><span class="sxs-lookup"><span data-stu-id="6034f-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="6034f-108">Otras clases que contribuyen a la representación de texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, y `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="6034f-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6034f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6034f-109">In This Section</span></span>  
 [<span data-ttu-id="6034f-110">Cómo: Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="6034f-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="6034f-111">Muestra cómo crear `Font` y `FontFamily` objetos.</span><span class="sxs-lookup"><span data-stu-id="6034f-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="6034f-112">Cómo: Dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="6034f-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="6034f-113">Describe cómo dibujar texto en una ubicación determinada con GDI + y GDI.</span><span class="sxs-lookup"><span data-stu-id="6034f-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="6034f-114">Cómo: Dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="6034f-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="6034f-115">Explica cómo dibujar texto en un rectángulo con GDI + y GDI.</span><span class="sxs-lookup"><span data-stu-id="6034f-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="6034f-116">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="6034f-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="6034f-117">Muestra cómo usar GDI para dibujar texto.</span><span class="sxs-lookup"><span data-stu-id="6034f-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="6034f-118">Cómo: Alinear texto dibujado</span><span class="sxs-lookup"><span data-stu-id="6034f-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="6034f-119">Muestra cómo dar formato al texto GDI + y GDI.</span><span class="sxs-lookup"><span data-stu-id="6034f-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="6034f-120">Cómo: Crear texto Vertical</span><span class="sxs-lookup"><span data-stu-id="6034f-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="6034f-121">Describe cómo se va a dibujar el texto alineado verticalmente con GDI +.</span><span class="sxs-lookup"><span data-stu-id="6034f-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="6034f-122">Cómo: Establecer posiciones de tabulación en texto dibujado</span><span class="sxs-lookup"><span data-stu-id="6034f-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="6034f-123">Muestra cómo dibujar texto con tabulaciones con GDI +.</span><span class="sxs-lookup"><span data-stu-id="6034f-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="6034f-124">Cómo: Enumerar las fuentes instaladas</span><span class="sxs-lookup"><span data-stu-id="6034f-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="6034f-125">Explica cómo enumerar los nombres de las fuentes instaladas.</span><span class="sxs-lookup"><span data-stu-id="6034f-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="6034f-126">Cómo: Crear una colección de fuentes privada</span><span class="sxs-lookup"><span data-stu-id="6034f-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="6034f-127">Describe cómo crear un <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="6034f-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="6034f-128">Cómo: Obtener medidas de fuentes</span><span class="sxs-lookup"><span data-stu-id="6034f-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="6034f-129">Se muestra cómo obtener medidas de fuentes, como el ascenso de celda y el descenso.</span><span class="sxs-lookup"><span data-stu-id="6034f-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="6034f-130">Cómo: Usa suavizado de contorno con texto</span><span class="sxs-lookup"><span data-stu-id="6034f-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="6034f-131">Explica cómo utilizar el suavizado de contorno al dibujar el texto.</span><span class="sxs-lookup"><span data-stu-id="6034f-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6034f-132">Referencia</span><span class="sxs-lookup"><span data-stu-id="6034f-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="6034f-133">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6034f-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="6034f-134">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6034f-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="6034f-135">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6034f-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="6034f-136">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6034f-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="6034f-137">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6034f-137">Describes this class and contains links to all of its members.</span></span>
