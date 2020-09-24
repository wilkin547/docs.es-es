---
title: Procedimiento para recuperar información de conflictos de miembros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 4848ef69914f0520d2365538faea7fa064c1a15c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155814"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="11aff-102">Procedimiento para recuperar información de conflictos de miembros</span><span class="sxs-lookup"><span data-stu-id="11aff-102">How to: Retrieve Member Conflict Information</span></span>

<span data-ttu-id="11aff-103">Puede utilizar la clase <xref:System.Data.Linq.MemberChangeConflict> para recuperar información sobre cada uno de los miembros en conflicto.</span><span class="sxs-lookup"><span data-stu-id="11aff-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="11aff-104">En este mismo contexto, puede proporcionar el control personalizado del conflicto para cualquier miembro.</span><span class="sxs-lookup"><span data-stu-id="11aff-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="11aff-105">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11aff-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11aff-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11aff-106">Example</span></span>  

 <span data-ttu-id="11aff-107">El código siguiente procesa una iteración en los objetos <xref:System.Data.Linq.ObjectChangeConflict>.</span><span class="sxs-lookup"><span data-stu-id="11aff-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="11aff-108">Para cada objeto, procesa una iteración en los objetos <xref:System.Data.Linq.MemberChangeConflict>.</span><span class="sxs-lookup"><span data-stu-id="11aff-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11aff-109">Incluya <xref:System.Reflection> para proporcionar información de <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.</span><span class="sxs-lookup"><span data-stu-id="11aff-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="11aff-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="11aff-110">See also</span></span>

- [<span data-ttu-id="11aff-111">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="11aff-111">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
