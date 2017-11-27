---
title: Regiones de GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="d1e6c-102">Regiones de GDI+</span><span class="sxs-lookup"><span data-stu-id="d1e6c-102">Regions in GDI+</span></span>
<span data-ttu-id="d1e6c-103">Una región es una parte del área de presentación de un dispositivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="d1e6c-104">Las regiones pueden ser simples (un único rectángulo) o complejas (una combinación de polígonos y curvas cerradas).</span><span class="sxs-lookup"><span data-stu-id="d1e6c-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="d1e6c-105">En la siguiente ilustración se muestra dos regiones: una construida a partir de un rectángulo y la otra construida a partir de una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="d1e6c-106">![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="d1e6c-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="d1e6c-107">Utilizar regiones</span><span class="sxs-lookup"><span data-stu-id="d1e6c-107">Using Regions</span></span>  
 <span data-ttu-id="d1e6c-108">Las regiones se utilizan a menudo para recortar y la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="d1e6c-109">Recortar implica la restricción del dibujo a una región determinada del área de presentación, normalmente la parte que debe actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="d1e6c-110">La prueba de posicionamiento implica la comprobación para determinar si el cursor está en una región determinada de la pantalla cuando se presiona un botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="d1e6c-111">Puede construir una región de un rectángulo o una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="d1e6c-112">También puede crear regiones complejas mediante la combinación de regiones existentes.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="d1e6c-113">El <xref:System.Drawing.Region> clase proporciona los siguientes métodos para combinar regiones: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, y <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="d1e6c-114">La intersección de dos regiones es el conjunto de todos los puntos que pertenecen a ambas regiones.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="d1e6c-115">La unión es el conjunto de todos los puntos que pertenecen a una u otra materia o ambas regiones.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="d1e6c-116">El complemento de una región es el conjunto de todos los puntos que no están en la región.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="d1e6c-117">En la siguiente ilustración muestra la intersección y la unión de las dos regiones que se muestra en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="d1e6c-118">![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="d1e6c-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="d1e6c-119">El <xref:System.Drawing.Region.Xor%2A> método, que se aplique a un par de regiones, genera una región que contiene todos los puntos que pertenecen a una región o la otra, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="d1e6c-120">El <xref:System.Drawing.Region.Exclude%2A> método, que se aplique a un par de regiones, genera una región que contiene todos los puntos de la primera región que no están en la segunda región.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="d1e6c-121">En la siguiente ilustración se muestra las regiones que son el resultado de aplicar el <xref:System.Drawing.Region.Xor%2A> y <xref:System.Drawing.Region.Exclude%2A> métodos a las dos regiones mostradas al principio de este tema.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="d1e6c-122">![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="d1e6c-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="d1e6c-123">Para rellenar una región, son necesarios un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Brush> objeto y un <xref:System.Drawing.Region> objeto.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="d1e6c-124">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.FillRegion%2A> método y el <xref:System.Drawing.Brush> objeto almacena atributos del relleno, como el color o una trama.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="d1e6c-125">En el ejemplo siguiente se rellena una región con un color sólido.</span><span class="sxs-lookup"><span data-stu-id="d1e6c-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="d1e6c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1e6c-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="d1e6c-127">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="d1e6c-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="d1e6c-128">Utilizar regiones</span><span class="sxs-lookup"><span data-stu-id="d1e6c-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
