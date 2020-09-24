---
title: Procedimiento para detectar y resolver envíos con conflictos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147728"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="418a0-102">Procedimiento para detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="418a0-102">How to: Detect and Resolve Conflicting Submissions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="418a0-103">proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="418a0-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="418a0-104">Para obtener más información, vea [Cómo: administrar conflictos de cambios](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="418a0-104">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="418a0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="418a0-105">Example</span></span>  

 <span data-ttu-id="418a0-106">En el ejemplo siguiente se muestra un `try` / `catch` bloque que detecta una <xref:System.Data.Linq.ChangeConflictException> excepción.</span><span class="sxs-lookup"><span data-stu-id="418a0-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="418a0-107">La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="418a0-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="418a0-108">Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información.</span><span class="sxs-lookup"><span data-stu-id="418a0-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="418a0-109">Para obtener más información, vea <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="418a0-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="418a0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="418a0-110">See also</span></span>

- [<span data-ttu-id="418a0-111">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="418a0-111">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="418a0-112">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="418a0-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
