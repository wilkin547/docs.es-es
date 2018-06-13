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
ms.openlocfilehash: c2b0a89966100077d5a72edc11822c356d2de1b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522775"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="4e211-102">Cómo: Cargar y mostrar metarchivos</span><span class="sxs-lookup"><span data-stu-id="4e211-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="4e211-103">El <xref:System.Drawing.Imaging.Metafile> (clase), que se hereda de la <xref:System.Drawing.Image> clase, proporciona métodos para registrar, mostrar y examinar imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="4e211-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e211-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e211-104">Example</span></span>  
 <span data-ttu-id="4e211-105">Para mostrar una imagen vectorial (metarchivo) en la pantalla, necesita un <xref:System.Drawing.Imaging.Metafile> objeto y un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="4e211-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4e211-106">Pasar el nombre de un archivo (o una secuencia) a un <xref:System.Drawing.Imaging.Metafile> constructor.</span><span class="sxs-lookup"><span data-stu-id="4e211-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="4e211-107">Después de haber creado un <xref:System.Drawing.Imaging.Metafile> de objetos, pasar ese <xref:System.Drawing.Imaging.Metafile> el objeto a la <xref:System.Drawing.Graphics.DrawImage%2A> método de una <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="4e211-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="4e211-108">El ejemplo se crea un <xref:System.Drawing.Imaging.Metafile> objeto desde un archivo EMF (metarchivo mejorado) y, a continuación, se dibuja la imagen con la esquina superior izquierda en (60, 10).</span><span class="sxs-lookup"><span data-stu-id="4e211-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="4e211-109">En la siguiente ilustración se muestra el metarchivo dibujado en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="4e211-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="4e211-110">![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="4e211-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e211-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e211-111">Compiling the Code</span></span>  
 <span data-ttu-id="4e211-112">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="4e211-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e211-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e211-113">See Also</span></span>  
 [<span data-ttu-id="4e211-114">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="4e211-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
