---
title: "Cómo: Dibujar un mapa de bits existente en la pantalla"
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
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b3c8aef4aee74fbcdcc80301f5d5c1020883341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="83c73-102">Cómo: Dibujar un mapa de bits existente en la pantalla</span><span class="sxs-lookup"><span data-stu-id="83c73-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="83c73-103">Puede dibujar fácilmente una imagen existente en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="83c73-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="83c73-104">En primer lugar debe crear un <xref:System.Drawing.Bitmap> objeto utilizando el constructor de mapa de bits que toma un nombre de archivo, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="83c73-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="83c73-105">Este constructor acepta imágenes con distintos formatos de archivo, incluidos los BMP, GIF, JPEG, PNG y TIFF.</span><span class="sxs-lookup"><span data-stu-id="83c73-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="83c73-106">Después de haber creado el <xref:System.Drawing.Bitmap> de objetos, pasar ese <xref:System.Drawing.Bitmap> el objeto a la <xref:System.Drawing.Graphics.DrawImage%2A> método de una <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="83c73-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c73-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83c73-107">Example</span></span>  
 <span data-ttu-id="83c73-108">Este ejemplo se crea un <xref:System.Drawing.Bitmap> objeto desde un archivo JPEG y, a continuación, se dibuja el mapa de bits con la esquina superior izquierda en (60, 10).</span><span class="sxs-lookup"><span data-stu-id="83c73-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="83c73-109">La siguiente ilustración muestra el mapa de bits dibujado en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="83c73-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="83c73-110">![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="83c73-110">![Image Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83c73-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="83c73-111">Compiling the Code</span></span>  
 <span data-ttu-id="83c73-112">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="83c73-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c73-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c73-113">See Also</span></span>  
 [<span data-ttu-id="83c73-114">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83c73-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="83c73-115">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="83c73-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
