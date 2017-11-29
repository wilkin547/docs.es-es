---
title: "Cómo: Utilizar una tabla de reasignación de colores"
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
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c4399e98504a675cfbf63462b8dc964c677488e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="8a7e8-102">Cómo: Utilizar una tabla de reasignación de colores</span><span class="sxs-lookup"><span data-stu-id="8a7e8-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="8a7e8-103">Cómo volver a asignar es el proceso de convertir los colores de una imagen según una tabla de reasignación de colores.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="8a7e8-104">La tabla de reasignación de colores es una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="8a7e8-105">Cada <xref:System.Drawing.Imaging.ColorMap> los objetos de la matriz tienen un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad y un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="8a7e8-106">Cuando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja una imagen, cada píxel de la imagen se compara con la matriz de colores antiguos.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="8a7e8-107">Si el color de un píxel coincide con un color antiguo, su color cambia al color nuevo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="8a7e8-108">Los colores se cambian para la representación, los valores de color de la imagen en Sí (almacenado en una <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> objeto) no se cambian.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="8a7e8-109">Para dibujar una imagen reasignada, inicialice una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="8a7e8-110">Pasar esa matriz a la <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> método de una <xref:System.Drawing.Imaging.ImageAttributes> objeto y, a continuación, pasar la <xref:System.Drawing.Imaging.ImageAttributes> el objeto a la <xref:System.Drawing.Graphics.DrawImage%2A> método de una <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a7e8-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a7e8-111">Example</span></span>  
 <span data-ttu-id="8a7e8-112">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="8a7e8-113">El código crea una tabla de reasignación de colores que consta de una sola <xref:System.Drawing.Imaging.ColorMap> objeto.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="8a7e8-114">El <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad de la `ColorRemap` objeto está en rojo y la <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad es azul.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="8a7e8-115">La imagen es dibuja una vez sin reasignación y otra vez con reasignación.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="8a7e8-116">El proceso de reasignación cambia todos los píxeles rojos a azul.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="8a7e8-117">En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen reasignada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="8a7e8-118">![Reasignación de colores](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="8a7e8-118">![Color ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8a7e8-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8a7e8-119">Compiling the Code</span></span>  
 <span data-ttu-id="8a7e8-120">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="8a7e8-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7e8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a7e8-121">See Also</span></span>  
 [<span data-ttu-id="8a7e8-122">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="8a7e8-122">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="8a7e8-123">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="8a7e8-123">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
