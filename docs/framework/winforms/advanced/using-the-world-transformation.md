---
title: Utilizar la transformación de coordenadas universales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139963"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="88225-102">Utilizar la transformación de coordenadas universales</span><span class="sxs-lookup"><span data-stu-id="88225-102">Using the World Transformation</span></span>
<span data-ttu-id="88225-103">La transformación universal es una propiedad de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="88225-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="88225-104">Los números que especifican la transformación universal se almacenan en un <xref:System.Drawing.Drawing2D.Matrix> objeto, que representa una matriz de 3 x 3.</span><span class="sxs-lookup"><span data-stu-id="88225-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="88225-105">El <xref:System.Drawing.Drawing2D.Matrix> y <xref:System.Drawing.Graphics> clases tienen varios métodos para establecer los números en la matriz de transformación del mundo.</span><span class="sxs-lookup"><span data-stu-id="88225-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="88225-106">Distintos tipos de transformaciones</span><span class="sxs-lookup"><span data-stu-id="88225-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="88225-107">En el ejemplo siguiente, el código primero crea un rectángulo de 50 x 50 y sitúa en el origen (0, 0).</span><span class="sxs-lookup"><span data-stu-id="88225-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="88225-108">El origen está en la esquina superior izquierda del área cliente.</span><span class="sxs-lookup"><span data-stu-id="88225-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="88225-109">El código siguiente aplica una transformación de escala que se expande el rectángulo por un factor de 1,75 en la dirección del eje x y reduce el rectángulo por un factor de 0,5 en la dirección y:</span><span class="sxs-lookup"><span data-stu-id="88225-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="88225-110">El resultado es un rectángulo que es más largo en la dirección del eje x y la dirección del eje y menor que el original.</span><span class="sxs-lookup"><span data-stu-id="88225-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="88225-111">Para girar el rectángulo en lugar de el escalado, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="88225-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="88225-112">Para traducir el rectángulo, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="88225-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="88225-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="88225-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="88225-114">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="88225-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="88225-115">Usar transformaciones en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="88225-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
