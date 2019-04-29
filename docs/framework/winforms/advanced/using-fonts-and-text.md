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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769426"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="11d59-102">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="11d59-102">Using Fonts and Text</span></span>
<span data-ttu-id="11d59-103">Hay varias clases proporcionadas por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="11d59-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="11d59-104">El [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> clase tiene varias <xref:System.Drawing.Graphics.DrawString%2A> métodos que le permiten especificar diversas características de texto, como la ubicación, el rectángulo delimitador, fuentes y formato.</span><span class="sxs-lookup"><span data-stu-id="11d59-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="11d59-105">Además, puede dibujar y medir el texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mediante estático <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> métodos que ofrece el `TextRenderer` clase.</span><span class="sxs-lookup"><span data-stu-id="11d59-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="11d59-106">El [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] métodos también permiten especificar la ubicación, la fuente y el formato.</span><span class="sxs-lookup"><span data-stu-id="11d59-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="11d59-107">Puede elegir [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar texto; sin embargo, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generalmente ofrece un mejor rendimiento y la medición de texto más precisa.</span><span class="sxs-lookup"><span data-stu-id="11d59-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="11d59-108">Otras clases que contribuyen a la representación de texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, y `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="11d59-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11d59-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11d59-109">In This Section</span></span>  
 [<span data-ttu-id="11d59-110">Cómo: Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="11d59-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="11d59-111">Muestra cómo crear `Font` y `FontFamily` objetos.</span><span class="sxs-lookup"><span data-stu-id="11d59-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="11d59-112">Cómo: Dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="11d59-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="11d59-113">Describe cómo dibujar texto en un determinado almacén utiliza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d59-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="11d59-114">Cómo: Dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="11d59-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="11d59-115">Explica cómo dibujar texto en un rectángulo mediante [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d59-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="11d59-116">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="11d59-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="11d59-117">Muestra cómo usar [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto.</span><span class="sxs-lookup"><span data-stu-id="11d59-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="11d59-118">Cómo: Alinear texto dibujado</span><span class="sxs-lookup"><span data-stu-id="11d59-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="11d59-119">Muestra cómo dar formato a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] texto.</span><span class="sxs-lookup"><span data-stu-id="11d59-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="11d59-120">Cómo: Crear texto Vertical</span><span class="sxs-lookup"><span data-stu-id="11d59-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="11d59-121">Describe cómo dibujar texto alineado verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d59-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="11d59-122">Cómo: Establecer posiciones de tabulación en texto dibujado</span><span class="sxs-lookup"><span data-stu-id="11d59-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="11d59-123">Muestra cómo dibujar texto con tabulaciones con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11d59-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="11d59-124">Cómo: Enumerar las fuentes instaladas</span><span class="sxs-lookup"><span data-stu-id="11d59-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="11d59-125">Explica cómo enumerar los nombres de las fuentes instaladas.</span><span class="sxs-lookup"><span data-stu-id="11d59-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="11d59-126">Cómo: Crear una colección de fuentes privada</span><span class="sxs-lookup"><span data-stu-id="11d59-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="11d59-127">Describe cómo crear un <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="11d59-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="11d59-128">Cómo: Obtener medidas de fuentes</span><span class="sxs-lookup"><span data-stu-id="11d59-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="11d59-129">Se muestra cómo obtener medidas de fuentes, como el ascenso de celda y el descenso.</span><span class="sxs-lookup"><span data-stu-id="11d59-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="11d59-130">Cómo: Usa suavizado de contorno con texto</span><span class="sxs-lookup"><span data-stu-id="11d59-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="11d59-131">Explica cómo utilizar el suavizado de contorno al dibujar el texto.</span><span class="sxs-lookup"><span data-stu-id="11d59-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="11d59-132">Referencia</span><span class="sxs-lookup"><span data-stu-id="11d59-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="11d59-133">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="11d59-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="11d59-134">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="11d59-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="11d59-135">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="11d59-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="11d59-136">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="11d59-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="11d59-137">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="11d59-137">Describes this class and contains links to all of its members.</span></span>
