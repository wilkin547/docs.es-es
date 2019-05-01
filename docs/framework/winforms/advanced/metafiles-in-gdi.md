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
ms.openlocfilehash: bb972f158496192aa38f10564209bb2781837414
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010041"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="93e93-102">Metarchivos en GDI+</span><span class="sxs-lookup"><span data-stu-id="93e93-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="93e93-103">proporciona el <xref:System.Drawing.Imaging.Metafile> clase por lo que puede grabar y mostrar metarchivos.</span><span class="sxs-lookup"><span data-stu-id="93e93-103">provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="93e93-104">Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y valores de dibujo.</span><span class="sxs-lookup"><span data-stu-id="93e93-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="93e93-105">Los comandos y valores que se registran en un <xref:System.Drawing.Imaging.Metafile> objeto se pueda almacenar en memoria o guardado en un archivo o secuencia.</span><span class="sxs-lookup"><span data-stu-id="93e93-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="93e93-106">Formatos de metarchivo</span><span class="sxs-lookup"><span data-stu-id="93e93-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="93e93-107">puede mostrar metarchivos que se han almacenado en los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="93e93-107">can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="93e93-108">Metarchivo de Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="93e93-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="93e93-109">Metarchivo mejorado (EMF)</span><span class="sxs-lookup"><span data-stu-id="93e93-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="93e93-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="93e93-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="93e93-111">puede registrar metarchivos en los formatos EMF y EMF +, pero no en el formato WMF.</span><span class="sxs-lookup"><span data-stu-id="93e93-111">can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="93e93-112">EMF + es una extensión EMF que permite [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="93e93-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="93e93-113">Hay dos variaciones en formato EMF +: EMF + solo y EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="93e93-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="93e93-114">Los metarchivos EMF + Only sólo contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros.</span><span class="sxs-lookup"><span data-stu-id="93e93-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="93e93-115">Metarchivos de este tipo se pueden mostrar por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pero no en [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93e93-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="93e93-116">Los metarchivos EMF + Dual contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registros.</span><span class="sxs-lookup"><span data-stu-id="93e93-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="93e93-117">Cada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros en un archivo EMF + Dual metarchivo se empareja con alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registro.</span><span class="sxs-lookup"><span data-stu-id="93e93-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="93e93-118">Metarchivos de este tipo se pueden mostrar por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93e93-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="93e93-119">El ejemplo siguiente muestra un metarchivo que se guardó previamente como un archivo.</span><span class="sxs-lookup"><span data-stu-id="93e93-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="93e93-120">Metarchivo que se muestra con la esquina superior izquierda en (100, 100).</span><span class="sxs-lookup"><span data-stu-id="93e93-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="93e93-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="93e93-121">See also</span></span>

- [<span data-ttu-id="93e93-122">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="93e93-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
