---
title: Utilizar lápiz para dibujar líneas y formas
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: 3846c59712cec6003c35f336714041544dec94b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777252"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="baaf2-102">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="baaf2-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="baaf2-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objetos que se va a dibujar los contornos de formas, curvas y segmentos de línea.</span><span class="sxs-lookup"><span data-stu-id="baaf2-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="baaf2-104">En esta sección, *línea* hace referencia a cualquiera de estos, a menos que indique que se trata únicamente de un segmento de línea.</span><span class="sxs-lookup"><span data-stu-id="baaf2-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="baaf2-105">Establecer las propiedades de un lápiz para controlar el color, ancho, alineación y el estilo de las líneas dibujadas con ese lápiz.</span><span class="sxs-lookup"><span data-stu-id="baaf2-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="baaf2-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="baaf2-106">In This Section</span></span>  
 [<span data-ttu-id="baaf2-107">Cómo: Utilizar lápiz para dibujar líneas</span><span class="sxs-lookup"><span data-stu-id="baaf2-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="baaf2-108">Explica cómo dibujar líneas.</span><span class="sxs-lookup"><span data-stu-id="baaf2-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="baaf2-109">Cómo: Utilizar lápiz para dibujar rectángulos</span><span class="sxs-lookup"><span data-stu-id="baaf2-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="baaf2-110">Describe cómo se dibujan rectángulos.</span><span class="sxs-lookup"><span data-stu-id="baaf2-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="baaf2-111">Cómo: Establecer el ancho de lápiz y la alineación</span><span class="sxs-lookup"><span data-stu-id="baaf2-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="baaf2-112">Explica cómo cambiar el ancho y la alineación de un `Pen` objeto.</span><span class="sxs-lookup"><span data-stu-id="baaf2-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="baaf2-113">Cómo: Dibujar una línea con extremos de línea</span><span class="sxs-lookup"><span data-stu-id="baaf2-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="baaf2-114">Describe cómo agregar extremos al dibujar una línea.</span><span class="sxs-lookup"><span data-stu-id="baaf2-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="baaf2-115">Cómo: Unir líneas</span><span class="sxs-lookup"><span data-stu-id="baaf2-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="baaf2-116">Muestra cómo combinar dos líneas.</span><span class="sxs-lookup"><span data-stu-id="baaf2-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="baaf2-117">Cómo: Dibujar una línea discontinua personalizada</span><span class="sxs-lookup"><span data-stu-id="baaf2-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="baaf2-118">Describe cómo dibujar una línea discontinua.</span><span class="sxs-lookup"><span data-stu-id="baaf2-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="baaf2-119">Cómo: Dibujar una línea rellenada con una textura</span><span class="sxs-lookup"><span data-stu-id="baaf2-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="baaf2-120">Explica cómo dibujar una línea de relleno de textura.</span><span class="sxs-lookup"><span data-stu-id="baaf2-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="baaf2-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="baaf2-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="baaf2-122">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="baaf2-122">Describes this class and has links to all its members.</span></span>
