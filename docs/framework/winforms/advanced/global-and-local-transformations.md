---
title: Transformaciones globales y locales
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e8d05bd0c3e76d643d56b652c8849eef1045ea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="38598-102">Transformaciones globales y locales</span><span class="sxs-lookup"><span data-stu-id="38598-102">Global and Local Transformations</span></span>
<span data-ttu-id="38598-103">Una transformación global es una transformación que se aplica a todos los elementos dibujados por un determinado <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="38598-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="38598-104">En cambio, una transformación local es una transformación que se aplica a un elemento específico que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="38598-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="38598-105">Transformaciones globales</span><span class="sxs-lookup"><span data-stu-id="38598-105">Global Transformations</span></span>  
 <span data-ttu-id="38598-106">Para crear una transformación global, construir un <xref:System.Drawing.Graphics> objeto y, a continuación, manipular su <xref:System.Drawing.Graphics.Transform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="38598-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="38598-107">El <xref:System.Drawing.Graphics.Transform%2A> propiedad es una <xref:System.Drawing.Drawing2D.Matrix> de objeto, por lo que puede almacenar cualquier secuencia de transformaciones afines.</span><span class="sxs-lookup"><span data-stu-id="38598-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="38598-108">La transformación se almacena en la <xref:System.Drawing.Graphics.Transform%2A> propiedad se denomina la transformación universal.</span><span class="sxs-lookup"><span data-stu-id="38598-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="38598-109">El <xref:System.Drawing.Graphics> clase proporciona varios métodos para crear una transformación universal compuesta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, y <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="38598-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="38598-110">En el ejemplo siguiente se dibuja una elipse dos veces: una vez antes de crear una transformación de coordenadas universales y otra después.</span><span class="sxs-lookup"><span data-stu-id="38598-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="38598-111">La transformación primero escala por un factor de 0,5 en la dirección del eje y, a continuación, traduce 50 unidades en la dirección del eje x y, a continuación, gira 30 grados.</span><span class="sxs-lookup"><span data-stu-id="38598-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="38598-112">En la siguiente ilustración muestra las matrices implicados en la transformación.</span><span class="sxs-lookup"><span data-stu-id="38598-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="38598-113">![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="38598-113">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38598-114">En el ejemplo anterior, la elipse gira sobre el origen del sistema de coordenadas, que se encuentra en la esquina superior izquierda del área cliente.</span><span class="sxs-lookup"><span data-stu-id="38598-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="38598-115">Esto produce un resultado diferente a la rotación de la elipse alrededor de su propio centro.</span><span class="sxs-lookup"><span data-stu-id="38598-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="38598-116">Transformaciones locales</span><span class="sxs-lookup"><span data-stu-id="38598-116">Local Transformations</span></span>  
 <span data-ttu-id="38598-117">Una transformación local se aplica a un elemento específico que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="38598-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="38598-118">Por ejemplo, un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto tiene una <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> método que permite transformar los puntos de datos de dicha ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="38598-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="38598-119">En el ejemplo siguiente se dibuja un rectángulo sin transformación y un trazado con una transformación de giro.</span><span class="sxs-lookup"><span data-stu-id="38598-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="38598-120">(Se supone que no hay ninguna transformación universal.)</span><span class="sxs-lookup"><span data-stu-id="38598-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="38598-121">Puede combinar la transformación universal con transformaciones locales para conseguir una gran variedad de resultados.</span><span class="sxs-lookup"><span data-stu-id="38598-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="38598-122">Por ejemplo, puede usar la transformación universal para revisar el sistema de coordenadas y usar transformaciones locales para girar y escalar objetos dibujados en el nuevo sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="38598-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="38598-123">Imagine que desea que un sistema de coordenadas que tiene su origen a 200 píxeles desde el borde izquierdo del área cliente y 150 píxeles de la parte superior del área cliente.</span><span class="sxs-lookup"><span data-stu-id="38598-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="38598-124">Además, supongamos que desea que la unidad de medida que sea el píxel, con el eje x apuntando hacia la derecha y el eje y apuntando hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="38598-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="38598-125">El sistema de coordenadas predeterminado tiene el eje y apuntando hacia abajo, por lo que necesita realizar una reflexión en el eje horizontal.</span><span class="sxs-lookup"><span data-stu-id="38598-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="38598-126">En la siguiente ilustración muestra la matriz de dicha reflexión.</span><span class="sxs-lookup"><span data-stu-id="38598-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="38598-127">![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="38598-127">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="38598-128">A continuación, imagine que necesita realizar una conversión de 200 unidades a la derecha y 150 unidades hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="38598-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="38598-129">El ejemplo siguiente establece el sistema de coordenadas descrito mediante el establecimiento de la transformación universal de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="38598-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="38598-130">El código siguiente (que se coloca al final del ejemplo anterior) crea una ruta de acceso que consta de un rectángulo con la esquina inferior izquierda en el origen del nuevo sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="38598-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="38598-131">El rectángulo se rellena una vez sin transformación local y otra vez con una transformación local.</span><span class="sxs-lookup"><span data-stu-id="38598-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="38598-132">La transformación local consta de un ajuste de escala horizontal en un factor de 2 seguido de una rotación de 30 grados.</span><span class="sxs-lookup"><span data-stu-id="38598-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="38598-133">En la siguiente ilustración muestra el nuevo sistema de coordenadas y los dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="38598-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="38598-134">![Transformaciones](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="38598-134">![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38598-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="38598-135">See Also</span></span>  
 [<span data-ttu-id="38598-136">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="38598-136">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="38598-137">Usar transformaciones en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="38598-137">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
