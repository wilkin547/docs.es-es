---
title: "Utilizar lápiz para dibujar líneas y formas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f43316e2535aae6622ccf7952f649cdb92fc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="2ae67-102">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="2ae67-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="2ae67-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objetos que se va a dibujar segmentos de línea, curvas y los contornos de formas.</span><span class="sxs-lookup"><span data-stu-id="2ae67-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="2ae67-104">En esta sección, *línea* hace referencia a cualquiera de estos, a menos que indique que se trata únicamente de un segmento de línea.</span><span class="sxs-lookup"><span data-stu-id="2ae67-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="2ae67-105">Establecer las propiedades de un lápiz para controlar el color, el ancho, la alineación y el estilo de las líneas dibujadas con ese lápiz.</span><span class="sxs-lookup"><span data-stu-id="2ae67-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ae67-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ae67-106">In This Section</span></span>  
 [<span data-ttu-id="2ae67-107">Utilizar lápiz para dibujar líneas</span><span class="sxs-lookup"><span data-stu-id="2ae67-107">How to: Use a Pen to Draw Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="2ae67-108">Explica cómo dibujar líneas.</span><span class="sxs-lookup"><span data-stu-id="2ae67-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="2ae67-109">Utilizar lápiz para dibujar rectángulos</span><span class="sxs-lookup"><span data-stu-id="2ae67-109">How to: Use a Pen to Draw Rectangles</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="2ae67-110">Describe cómo dibujar rectángulos.</span><span class="sxs-lookup"><span data-stu-id="2ae67-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="2ae67-111">Establecer el ancho y la alineación del lápiz</span><span class="sxs-lookup"><span data-stu-id="2ae67-111">How to: Set Pen Width and Alignment</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="2ae67-112">Explica cómo cambiar el ancho y la alineación de un `Pen` objeto.</span><span class="sxs-lookup"><span data-stu-id="2ae67-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="2ae67-113">Dibujar una línea con extremos de línea</span><span class="sxs-lookup"><span data-stu-id="2ae67-113">How to: Draw a Line with Line Caps</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="2ae67-114">Describe cómo agregar extremos al dibujar una línea.</span><span class="sxs-lookup"><span data-stu-id="2ae67-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="2ae67-115">Unir líneas</span><span class="sxs-lookup"><span data-stu-id="2ae67-115">How to: Join Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-join-lines.md)  
 <span data-ttu-id="2ae67-116">Muestra cómo combinar las dos líneas.</span><span class="sxs-lookup"><span data-stu-id="2ae67-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="2ae67-117">Dibujar una línea discontinua personalizada</span><span class="sxs-lookup"><span data-stu-id="2ae67-117">How to: Draw a Custom Dashed Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="2ae67-118">Describe cómo dibujar una línea discontinua.</span><span class="sxs-lookup"><span data-stu-id="2ae67-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="2ae67-119">Dibujar una línea rellena con una textura</span><span class="sxs-lookup"><span data-stu-id="2ae67-119">How to: Draw a Line Filled with a Texture</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="2ae67-120">Explica cómo dibujar una línea de relleno de textura.</span><span class="sxs-lookup"><span data-stu-id="2ae67-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ae67-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="2ae67-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="2ae67-122">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="2ae67-122">Describes this class and has links to all its members.</span></span>
