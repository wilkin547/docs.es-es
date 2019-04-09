---
title: Filtrar para detectar y resolver envíos con conflictos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138130"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="d387d-102">Filtrar para detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="d387d-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d387d-103">proporciona muchos recursos para detectar y resolver los conflictos derivados de los cambios de varios usuarios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d387d-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="d387d-104">Para obtener más información, vea [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="d387d-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d387d-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d387d-105">Example</span></span>  
 <span data-ttu-id="d387d-106">El ejemplo siguiente se muestra un `try` / `catch` bloque que detecta un <xref:System.Data.Linq.ChangeConflictException> excepción.</span><span class="sxs-lookup"><span data-stu-id="d387d-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="d387d-107">La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="d387d-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d387d-108">Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información.</span><span class="sxs-lookup"><span data-stu-id="d387d-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="d387d-109">Para obtener más información, consulta <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="d387d-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d387d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d387d-110">See also</span></span>

- [<span data-ttu-id="d387d-111">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="d387d-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="d387d-112">Filtrar para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="d387d-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
