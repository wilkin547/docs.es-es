---
title: Procedimiento para usar la comprobación de visitas en una región
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150506"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="61f5f-102">Procedimiento para usar la comprobación de visitas en una región</span><span class="sxs-lookup"><span data-stu-id="61f5f-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="61f5f-103">Es el propósito de la prueba de posicionamiento determinar si el cursor está sobre un objeto determinado, como un icono o un botón.</span><span class="sxs-lookup"><span data-stu-id="61f5f-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f5f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61f5f-104">Example</span></span>  
 <span data-ttu-id="61f5f-105">El ejemplo siguiente crea una región en forma más mediante la unión de dos regiones rectangulares.</span><span class="sxs-lookup"><span data-stu-id="61f5f-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="61f5f-106">Supongamos que la variable `point` contiene la ubicación del clic más reciente.</span><span class="sxs-lookup"><span data-stu-id="61f5f-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="61f5f-107">El código comprueba si `point` está en la región en forma de signo más.</span><span class="sxs-lookup"><span data-stu-id="61f5f-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="61f5f-108">Si el punto está en la región (una visita), la región se rellena con un pincel rojo opaco.</span><span class="sxs-lookup"><span data-stu-id="61f5f-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="61f5f-109">En caso contrario, la región se rellena con un pincel rojo semitransparente.</span><span class="sxs-lookup"><span data-stu-id="61f5f-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61f5f-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="61f5f-110">Compiling the Code</span></span>  
 <span data-ttu-id="61f5f-111">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="61f5f-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f5f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="61f5f-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="61f5f-113">Regiones de GDI+</span><span class="sxs-lookup"><span data-stu-id="61f5f-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="61f5f-114">Cómo: Utilizar el recorte en una región</span><span class="sxs-lookup"><span data-stu-id="61f5f-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
