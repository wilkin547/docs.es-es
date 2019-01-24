---
title: Procedimiento Usar con una región de la prueba de posicionamiento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564310"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="876d2-102">Procedimiento Usar con una región de la prueba de posicionamiento</span><span class="sxs-lookup"><span data-stu-id="876d2-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="876d2-103">Es el propósito de la prueba de posicionamiento determinar si el cursor está sobre un objeto determinado, como un icono o un botón.</span><span class="sxs-lookup"><span data-stu-id="876d2-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="876d2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="876d2-104">Example</span></span>  
 <span data-ttu-id="876d2-105">El ejemplo siguiente crea una región en forma más mediante la unión de dos regiones rectangulares.</span><span class="sxs-lookup"><span data-stu-id="876d2-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="876d2-106">Supongamos que la variable `point` contiene la ubicación del clic más reciente.</span><span class="sxs-lookup"><span data-stu-id="876d2-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="876d2-107">El código comprueba si `point` está en la región en forma de signo más.</span><span class="sxs-lookup"><span data-stu-id="876d2-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="876d2-108">Si el punto está en la región (una visita), la región se rellena con un pincel rojo opaco.</span><span class="sxs-lookup"><span data-stu-id="876d2-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="876d2-109">En caso contrario, la región se rellena con un pincel rojo semitransparente.</span><span class="sxs-lookup"><span data-stu-id="876d2-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="876d2-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="876d2-110">Compiling the Code</span></span>  
 <span data-ttu-id="876d2-111">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="876d2-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876d2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="876d2-112">See also</span></span>
- <xref:System.Drawing.Region>
- [<span data-ttu-id="876d2-113">Regiones de GDI+</span><span class="sxs-lookup"><span data-stu-id="876d2-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [<span data-ttu-id="876d2-114">Cómo: Utilizar el recorte en una región</span><span class="sxs-lookup"><span data-stu-id="876d2-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
