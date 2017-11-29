---
title: "Cómo: Convertir colores de imágenes"
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
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c21d20b631d8e0cf68e370dd43b3f5e92144b09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="34098-102">Cómo: Convertir colores de imágenes</span><span class="sxs-lookup"><span data-stu-id="34098-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="34098-103">Una traducción, agrega un valor para uno o varios de los cuatro componentes de color.</span><span class="sxs-lookup"><span data-stu-id="34098-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="34098-104">En la tabla siguiente se indican las entradas de la matriz de color que representan las traducciones.</span><span class="sxs-lookup"><span data-stu-id="34098-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="34098-105">Componente que se deben traducir</span><span class="sxs-lookup"><span data-stu-id="34098-105">Component to be translated</span></span>|<span data-ttu-id="34098-106">Entrada de matriz</span><span class="sxs-lookup"><span data-stu-id="34098-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="34098-107">Rojo</span><span class="sxs-lookup"><span data-stu-id="34098-107">Red</span></span>|<span data-ttu-id="34098-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="34098-108">[4][0]</span></span>|  
|<span data-ttu-id="34098-109">Verde</span><span class="sxs-lookup"><span data-stu-id="34098-109">Green</span></span>|<span data-ttu-id="34098-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="34098-110">[4][1]</span></span>|  
|<span data-ttu-id="34098-111">Azul</span><span class="sxs-lookup"><span data-stu-id="34098-111">Blue</span></span>|<span data-ttu-id="34098-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="34098-112">[4][2]</span></span>|  
|<span data-ttu-id="34098-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="34098-113">Alpha</span></span>|<span data-ttu-id="34098-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="34098-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34098-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34098-115">Example</span></span>  
 <span data-ttu-id="34098-116">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="34098-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="34098-117">A continuación, el código agrega 0,75 al componente rojo de cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="34098-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="34098-118">Se dibuja la imagen original junto con la imagen transformada.</span><span class="sxs-lookup"><span data-stu-id="34098-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="34098-119">En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen transformada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="34098-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="34098-120">![Conversión de colores](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="34098-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="34098-121">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la conversión del rojo.</span><span class="sxs-lookup"><span data-stu-id="34098-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="34098-122">Tenga en cuenta que dado que el valor máximo de un componente de color es 1, el componente rojo de la segunda fila no cambia.</span><span class="sxs-lookup"><span data-stu-id="34098-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="34098-123">(De forma similar, el valor mínimo de un componente de color es 0).</span><span class="sxs-lookup"><span data-stu-id="34098-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="34098-124">Original</span><span class="sxs-lookup"><span data-stu-id="34098-124">Original</span></span>|<span data-ttu-id="34098-125">Texto traducido al</span><span class="sxs-lookup"><span data-stu-id="34098-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="34098-126">Negro (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="34098-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="34098-128">Rojo (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="34098-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="34098-130">Verde (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="34098-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="34098-132">Azul (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="34098-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="34098-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34098-134">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="34098-134">Compiling the Code</span></span>  
 <span data-ttu-id="34098-135">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="34098-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="34098-136">Reemplace `ColorBars.bmp` con un nombre de archivo de imagen y la ruta de acceso que son válidos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="34098-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34098-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="34098-137">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="34098-138">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34098-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="34098-139">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="34098-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
