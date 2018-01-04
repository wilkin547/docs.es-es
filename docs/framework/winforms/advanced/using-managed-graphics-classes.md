---
title: "Utilizar clases gráficas administradas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, managed classes
- graphics [Windows Forms], using in Windows Forms
- graphics [Windows Forms], managed classes
ms.assetid: e6d1a42d-2100-46aa-97e6-a5ddc0baaae5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a34e2726182c194882d94fe4b8d1164993d8284
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-managed-graphics-classes"></a><span data-ttu-id="75698-102">Utilizar clases gráficas administradas</span><span class="sxs-lookup"><span data-stu-id="75698-102">Using Managed Graphics Classes</span></span>
<span data-ttu-id="75698-103">Los temas siguientes describen cómo utilizar el [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API en el marco de trabajo de la clase administrada.</span><span class="sxs-lookup"><span data-stu-id="75698-103">The following topics describe how to use the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API in the managed class framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75698-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="75698-104">In This Section</span></span>  
 [<span data-ttu-id="75698-105">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="75698-105">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 <span data-ttu-id="75698-106">Describe cómo realizar tareas básicas con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75698-106">Describes how to accomplish basic tasks with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="75698-107">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="75698-107">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 <span data-ttu-id="75698-108">Muestra cómo construir un lápiz y utilizarlo para dibujar una serie de líneas y formas.</span><span class="sxs-lookup"><span data-stu-id="75698-108">Demonstrates how to construct a pen and use it to draw a variety of lines and shapes.</span></span>  
  
 [<span data-ttu-id="75698-109">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="75698-109">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)  
 <span data-ttu-id="75698-110">Muestra cómo construir un pincel y rellenar formas con una variedad de efectos.</span><span class="sxs-lookup"><span data-stu-id="75698-110">Demonstrates how to construct a brush and fill shapes with a variety of effects.</span></span>  
  
 [<span data-ttu-id="75698-111">Utilizar un pincel degradado para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="75698-111">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 <span data-ttu-id="75698-112">Muestra cómo crear y utilizar diferentes tipos de pinceles degradados.</span><span class="sxs-lookup"><span data-stu-id="75698-112">Shows how to create and use different types of gradient brushes.</span></span>  
  
 [<span data-ttu-id="75698-113">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="75698-113">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="75698-114">Muestra cómo crear y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="75698-114">Demonstrates how to construct and manipulate images.</span></span>  
  
 [<span data-ttu-id="75698-115">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="75698-115">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 <span data-ttu-id="75698-116">Muestra cómo lograr la transparencia para formas y líneas.</span><span class="sxs-lookup"><span data-stu-id="75698-116">Demonstrates how to achieve transparency for shapes and lines.</span></span>  
  
 [<span data-ttu-id="75698-117">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="75698-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 <span data-ttu-id="75698-118">Muestra cómo dibujar texto y utilizar fuentes y familias de fuentes.</span><span class="sxs-lookup"><span data-stu-id="75698-118">Shows how to draw text and use fonts and font families.</span></span>  
  
 [<span data-ttu-id="75698-119">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="75698-119">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 <span data-ttu-id="75698-120">Muestra cómo dibujar curvas spline cardinales y Bézier.</span><span class="sxs-lookup"><span data-stu-id="75698-120">Shows how to draw Cardinal and Bezier splines.</span></span>  
  
 [<span data-ttu-id="75698-121">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="75698-121">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 <span data-ttu-id="75698-122">Muestra cómo crear ilustraciones con rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="75698-122">Shows how to create figures using paths.</span></span>  
  
 [<span data-ttu-id="75698-123">Usar transformaciones en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="75698-123">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)  
 <span data-ttu-id="75698-124">Muestra las transformaciones de matrices.</span><span class="sxs-lookup"><span data-stu-id="75698-124">Demonstrates matrix transformations.</span></span>  
  
 [<span data-ttu-id="75698-125">Utilizar contenedores de gráficos</span><span class="sxs-lookup"><span data-stu-id="75698-125">Using Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-graphics-containers.md)  
 <span data-ttu-id="75698-126">Muestra cómo administrar contenedores de gráficos anidados y estado de objeto de gráficos.</span><span class="sxs-lookup"><span data-stu-id="75698-126">Shows how to manage graphics object state and nested graphics containers.</span></span>  
  
 [<span data-ttu-id="75698-127">Utilizar regiones</span><span class="sxs-lookup"><span data-stu-id="75698-127">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)  
 <span data-ttu-id="75698-128">Muestra la comprobación de visitas y recorte con regiones.</span><span class="sxs-lookup"><span data-stu-id="75698-128">Demonstrates hit testing and clipping with regions.</span></span>  
  
 [<span data-ttu-id="75698-129">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="75698-129">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 <span data-ttu-id="75698-130">Muestra varios aspectos de manipular los colores.</span><span class="sxs-lookup"><span data-stu-id="75698-130">Demonstrates various aspects of manipulating colors.</span></span>  
  
 [<span data-ttu-id="75698-131">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="75698-131">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 <span data-ttu-id="75698-132">Se muestra cómo utilizar descodificadores y codificadores de imágenes para manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="75698-132">Show how to use image encoders and decoders to manipulate images.</span></span>  
  
 [<span data-ttu-id="75698-133">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="75698-133">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="75698-134">Muestra cómo reducir el parpadeo con doble búfer.</span><span class="sxs-lookup"><span data-stu-id="75698-134">Demonstrates how to reduce flicker with double buffering.</span></span>
