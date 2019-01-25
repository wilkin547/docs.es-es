---
title: Procedimiento Utilizar el recorte en una región
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: 5482218a8d6310ce49a1f9f5f02b3b8e36c1fd90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590661"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="353a0-102">Procedimiento Utilizar el recorte en una región</span><span class="sxs-lookup"><span data-stu-id="353a0-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="353a0-103">Una de las propiedades de la <xref:System.Drawing.Graphics> clase es la región de recorte.</span><span class="sxs-lookup"><span data-stu-id="353a0-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="353a0-104">Todos los dibujos realizados por un determinado <xref:System.Drawing.Graphics> está restringido a la región de recorte de dicho objeto <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="353a0-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="353a0-105">Puede establecer la región de recorte mediante una llamada a la <xref:System.Drawing.Graphics.SetClip%2A> método.</span><span class="sxs-lookup"><span data-stu-id="353a0-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="353a0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="353a0-106">Example</span></span>  
 <span data-ttu-id="353a0-107">El ejemplo siguiente crea una ruta de acceso que consta de un polígono.</span><span class="sxs-lookup"><span data-stu-id="353a0-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="353a0-108">A continuación, el código construye una región, en función de esa ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="353a0-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="353a0-109">La región se pasa a la <xref:System.Drawing.Graphics.SetClip%2A> método de un <xref:System.Drawing.Graphics> se dibujan los objetos y, a continuación, dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="353a0-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="353a0-110">La siguiente ilustración muestra las cadenas recortadas.</span><span class="sxs-lookup"><span data-stu-id="353a0-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="353a0-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="353a0-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="353a0-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="353a0-112">Compiling the Code</span></span>  
 <span data-ttu-id="353a0-113">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="353a0-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="353a0-114">See also</span></span>
- [<span data-ttu-id="353a0-115">Regiones de GDI+</span><span class="sxs-lookup"><span data-stu-id="353a0-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="353a0-116">Utilizar regiones</span><span class="sxs-lookup"><span data-stu-id="353a0-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
