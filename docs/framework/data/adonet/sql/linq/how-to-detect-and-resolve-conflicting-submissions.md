---
title: 'Cómo: Detectar y resolver envíos con conflictos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: dfe1fac4285b915c316fb70d1e3bd1e7b99f145a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354399"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="ec1c1-102">Cómo: Detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="ec1c1-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ec1c1-103"> proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-103"> provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="ec1c1-104">Para obtener más información, consulte [Cómo: administrar conflictos de cambio](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="ec1c1-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec1c1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec1c1-105">Example</span></span>  
 <span data-ttu-id="ec1c1-106">El ejemplo siguiente muestra un `try` / `catch` bloque que detecta un <xref:System.Data.Linq.ChangeConflictException> excepción.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="ec1c1-107">La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec1c1-108">Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="ec1c1-109">Para obtener más información, consulta <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ec1c1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec1c1-110">See Also</span></span>  
 [<span data-ttu-id="ec1c1-111">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="ec1c1-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="ec1c1-112">Administración de conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="ec1c1-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
