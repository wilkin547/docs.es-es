---
title: "Cómo: Detectar y resolver envíos con conflictos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28dba94262002f863a750a83493ba98b3714fabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="13c64-102">Cómo: Detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="13c64-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="13c64-103"> proporciona muchos recursos para detectar y resolver los conflictos que ocasionan los cambios que realizan varios usuarios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="13c64-103"> provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="13c64-104">Para obtener más información, consulte [Cómo: administrar conflictos de cambio](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="13c64-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c64-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13c64-105">Example</span></span>  
 <span data-ttu-id="13c64-106">El ejemplo siguiente muestra un `try` / `catch` bloque que detecta un <xref:System.Data.Linq.ChangeConflictException> excepción.</span><span class="sxs-lookup"><span data-stu-id="13c64-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="13c64-107">La información de entidad y miembro de cada conflicto se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="13c64-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c64-108">Debe incluir la directiva `using System.Reflection` (`Imports System.Reflection` en Visual Basic) para habilitar la recuperación de la información.</span><span class="sxs-lookup"><span data-stu-id="13c64-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="13c64-109">Para obtener más información, consulta <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="13c64-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="13c64-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="13c64-110">See Also</span></span>  
 [<span data-ttu-id="13c64-111">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="13c64-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="13c64-112">Administración de conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="13c64-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
