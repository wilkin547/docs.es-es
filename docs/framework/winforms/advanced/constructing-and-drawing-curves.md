---
title: Crear y dibujar curvas
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 92e7b1e8b4ce37db633b5dafe212a252b854d1af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935452"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="ee4a5-102">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="ee4a5-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ee4a5-103">admite varios tipos de curvas: elipses, arcos, curvas spline cardinales y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-103">supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="ee4a5-104">Una elipse se define por su rectángulo delimitador; un arco es una parte de una elipse definida por un ángulo inicial y un ángulo de barrido.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="ee4a5-105">Una curva spline cardinal se define mediante una matriz de puntos y un parámetro de tensión, la curva suavemente pasa por cada punto de la matriz y el parámetro de tensión influye en la manera en que la curva.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="ee4a5-106">Una curva spline de Bézier se define mediante dos puntos de conexión y dos puntos de control de que la curva no pasa por los puntos de control, pero los puntos de control influyen en la dirección y doblar la curva de tránsito de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee4a5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ee4a5-107">In This Section</span></span>  
 [<span data-ttu-id="ee4a5-108">Cómo: Dibujar curvas spline cardinales</span><span class="sxs-lookup"><span data-stu-id="ee4a5-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="ee4a5-109">Describe las curvas spline cardinales y cómo dibujarlas.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="ee4a5-110">Cómo: Dibujar una curva Spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="ee4a5-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="ee4a5-111">Describe una curva spline de Bézier y cómo se dibujan uno.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="ee4a5-112">Cómo: Dibujar una secuencia de curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="ee4a5-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="ee4a5-113">Explica cómo dibujar varias curvas spline de Bézier en secuencia.</span><span class="sxs-lookup"><span data-stu-id="ee4a5-113">Explains how to draw several Bézier splines in sequence.</span></span>
