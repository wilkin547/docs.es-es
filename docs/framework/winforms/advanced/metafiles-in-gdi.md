---
title: Metarchivos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504584"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="db653-102">Metarchivos en GDI+</span><span class="sxs-lookup"><span data-stu-id="db653-102">Metafiles in GDI+</span></span>
<span data-ttu-id="db653-103">GDI + proporciona la <xref:System.Drawing.Imaging.Metafile> clase por lo que puede grabar y mostrar metarchivos.</span><span class="sxs-lookup"><span data-stu-id="db653-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="db653-104">Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y valores de dibujo.</span><span class="sxs-lookup"><span data-stu-id="db653-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="db653-105">Los comandos y valores que se registran en un <xref:System.Drawing.Imaging.Metafile> objeto se pueda almacenar en memoria o guardado en un archivo o secuencia.</span><span class="sxs-lookup"><span data-stu-id="db653-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="db653-106">Formatos de metarchivo</span><span class="sxs-lookup"><span data-stu-id="db653-106">Metafile Formats</span></span>  
 <span data-ttu-id="db653-107">GDI + puede mostrar metarchivos que se han almacenado en los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="db653-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="db653-108">Metarchivo de Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="db653-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="db653-109">Metarchivo mejorado (EMF)</span><span class="sxs-lookup"><span data-stu-id="db653-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="db653-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="db653-110">EMF+</span></span>  
  
 <span data-ttu-id="db653-111">GDI + puede registrar metarchivos en los formatos EMF y EMF +, pero no en el formato WMF.</span><span class="sxs-lookup"><span data-stu-id="db653-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="db653-112">EMF + es una extensión EMF que permite que se almacenen registros GDI +.</span><span class="sxs-lookup"><span data-stu-id="db653-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="db653-113">Hay dos variaciones en formato EMF +: EMF + solo y EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="db653-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="db653-114">Metarchivos EMF + sólo contienen únicamente registros GDI +.</span><span class="sxs-lookup"><span data-stu-id="db653-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="db653-115">Metarchivos de este tipo pueden mostrarse en GDI + pero no en GDI.</span><span class="sxs-lookup"><span data-stu-id="db653-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="db653-116">Los metarchivos EMF + Dual contienen registros GDI + y GDI.</span><span class="sxs-lookup"><span data-stu-id="db653-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="db653-117">Cada registro GDI + de un metarchivo EMF + Dual está emparejado con un registro GDI alternativo.</span><span class="sxs-lookup"><span data-stu-id="db653-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="db653-118">Metarchivos de este tipo pueden mostrarse mediante GDI + o GDI.</span><span class="sxs-lookup"><span data-stu-id="db653-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="db653-119">El ejemplo siguiente muestra un metarchivo que se guardó previamente como un archivo.</span><span class="sxs-lookup"><span data-stu-id="db653-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="db653-120">Metarchivo que se muestra con la esquina superior izquierda en (100, 100).</span><span class="sxs-lookup"><span data-stu-id="db653-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="db653-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="db653-121">See also</span></span>

- [<span data-ttu-id="db653-122">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="db653-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
