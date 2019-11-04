---
title: 'Cómo: Cargar y mostrar metarchivos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424815"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="cf419-102">Cómo: Cargar y mostrar metarchivos</span><span class="sxs-lookup"><span data-stu-id="cf419-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="cf419-103">La clase <xref:System.Drawing.Imaging.Metafile>, que hereda de la clase <xref:System.Drawing.Image>, proporciona métodos para grabar, mostrar y examinar imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="cf419-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf419-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf419-104">Example</span></span>  
 <span data-ttu-id="cf419-105">Para mostrar una imagen vectorial (metarchivo) en la pantalla, necesita un objeto <xref:System.Drawing.Imaging.Metafile> y un objeto <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="cf419-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="cf419-106">Pase el nombre de un archivo (o una secuencia) a un constructor de <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="cf419-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="cf419-107">Después de crear un objeto de <xref:System.Drawing.Imaging.Metafile>, pase ese <xref:System.Drawing.Imaging.Metafile> objeto al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="cf419-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="cf419-108">En el ejemplo se crea un objeto <xref:System.Drawing.Imaging.Metafile> a partir de un archivo EMF (metarchivo mejorado) y, a continuación, se dibuja la imagen con la esquina superior izquierda en (60, 10).</span><span class="sxs-lookup"><span data-stu-id="cf419-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="cf419-109">En la ilustración siguiente se muestra el metarchivo dibujado en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="cf419-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="cf419-110">![Captura de pantalla que muestra la posición de la imagen.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="cf419-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf419-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cf419-111">Compiling the Code</span></span>  
 <span data-ttu-id="cf419-112">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="cf419-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf419-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf419-113">See also</span></span>

- [<span data-ttu-id="cf419-114">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="cf419-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
