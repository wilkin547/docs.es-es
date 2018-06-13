---
title: 'Cómo: Especificar cuándo se inician las excepciones de simultaneidad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 6890cc130f4f4101c02bb88c5f5666bcd5cf9b98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360825"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="38c1a-102">Cómo: Especificar cuándo se inician las excepciones de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="38c1a-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="38c1a-103">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando los objetos no se actualizan debido a conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="38c1a-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="38c1a-104">Para obtener más información, consulte [simultaneidad optimista: información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="38c1a-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="38c1a-105">Antes de enviar cambios a la base de datos, puede especificar cuándo se deberían iniciar excepciones de simultaneidad:</span><span class="sxs-lookup"><span data-stu-id="38c1a-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
-   <span data-ttu-id="38c1a-106">Iniciar la excepción en el primer error (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="38c1a-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
-   <span data-ttu-id="38c1a-107">Finalizar todos los intentos de actualización, acumular todos los errores e informar de todos ellos en la excepción (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="38c1a-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="38c1a-108">Cuando se inicia, la excepción <xref:System.Data.Linq.ChangeConflictException> proporciona acceso a una colección <xref:System.Data.Linq.ChangeConflictCollection>.</span><span class="sxs-lookup"><span data-stu-id="38c1a-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="38c1a-109">Esta colección proporciona detalles sobre cada conflicto (asignado a un único intento de actualización con error), incluido el acceso a la colección <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.</span><span class="sxs-lookup"><span data-stu-id="38c1a-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="38c1a-110">Cada conflicto de miembro se asigna a un único miembro en la actualización que no pasó la comprobación de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="38c1a-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38c1a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38c1a-111">Example</span></span>  
 <span data-ttu-id="38c1a-112">El código siguiente muestra ejemplos de ambos valores.</span><span class="sxs-lookup"><span data-stu-id="38c1a-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="38c1a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38c1a-113">See Also</span></span>  
 [<span data-ttu-id="38c1a-114">Administración de conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="38c1a-114">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="38c1a-115">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="38c1a-115">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
