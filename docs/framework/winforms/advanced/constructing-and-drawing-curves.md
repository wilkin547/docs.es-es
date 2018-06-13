---
title: Crear y dibujar curvas
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: d9a790060fdf0f0c2a739d99aba1b36cf0323f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520622"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="e2055-102">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="e2055-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e2055-103"> admite varios tipos de curvas: elipses, arcos, curvas spline cardinales y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="e2055-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="e2055-104">Una elipse se define por su rectángulo delimitador; un arco es una parte de una elipse definida por un ángulo inicial y un ángulo de barrido.</span><span class="sxs-lookup"><span data-stu-id="e2055-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="e2055-105">Una curva spline cardinal se define mediante una matriz de puntos y un parámetro de tensión: la curva pasa suavemente por cada punto de la matriz, y el parámetro de tensión influye en la forma de la curva.</span><span class="sxs-lookup"><span data-stu-id="e2055-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="e2055-106">Una curva spline de Bézier se define mediante dos puntos de conexión y dos puntos de control de que la curva no pasa por los puntos de control, pero los puntos de control influyen en la dirección y doblar la curva de tránsito de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="e2055-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2055-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e2055-107">In This Section</span></span>  
 [<span data-ttu-id="e2055-108">Dibujar curvas spline cardinales</span><span class="sxs-lookup"><span data-stu-id="e2055-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="e2055-109">Describe las curvas spline cardinales y cómo obtenerlas.</span><span class="sxs-lookup"><span data-stu-id="e2055-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="e2055-110">Dibujar una curva spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="e2055-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="e2055-111">Describe una curva spline de Bézier y cómo dibujar uno.</span><span class="sxs-lookup"><span data-stu-id="e2055-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="e2055-112">Dibujar una secuencia de curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="e2055-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="e2055-113">Explica cómo dibujar varias curvas spline de Bézier en secuencia.</span><span class="sxs-lookup"><span data-stu-id="e2055-113">Explains how to draw several Bézier splines in sequence.</span></span>
