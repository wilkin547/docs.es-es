---
title: Crear y dibujar trazados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6cec2356159b59e58ac6785a2988df7b2fac0e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="10c36-102">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="10c36-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="10c36-103">Una ruta de acceso es una secuencia de primitivos de gráficos (líneas, rectángulos, curvas, texto etc.) que se pueden manipular y dibujar como una sola unidad.</span><span class="sxs-lookup"><span data-stu-id="10c36-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="10c36-104">Una ruta de acceso puede dividirse en *cifras* que están abiertos o cerrados.</span><span class="sxs-lookup"><span data-stu-id="10c36-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="10c36-105">Una figura puede contener a varios tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="10c36-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="10c36-106">Puede dibujar un trazado mediante una llamada a la <xref:System.Drawing.Graphics.DrawPath%2A> método de la <xref:System.Drawing.Graphics> clase y se puede escribir una ruta de acceso mediante una llamada a la <xref:System.Drawing.Graphics.FillPath%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="10c36-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10c36-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="10c36-107">In This Section</span></span>  
 [<span data-ttu-id="10c36-108">Crear figuras a partir de líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="10c36-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="10c36-109">Muestra cómo utilizar un <xref:System.Drawing.Drawing2D.GraphicsPath> para crear figuras.</span><span class="sxs-lookup"><span data-stu-id="10c36-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="10c36-110">Rellenar figuras abiertas</span><span class="sxs-lookup"><span data-stu-id="10c36-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="10c36-111">Explica cómo rellenar un <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="10c36-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="10c36-112">Aplanar un trazado curvo en una línea</span><span class="sxs-lookup"><span data-stu-id="10c36-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="10c36-113">Muestra cómo aplanar un <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="10c36-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="10c36-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="10c36-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="10c36-115">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="10c36-115">Describes this class and contains links to all of its members.</span></span>
