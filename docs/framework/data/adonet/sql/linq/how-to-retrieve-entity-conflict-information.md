---
title: Procedimiento para recuperar información de conflictos de entidades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: e8c548ac632454d9c488ebd5f7b471f6759418fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155879"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="7e3a8-102">Procedimiento para recuperar información de conflictos de entidades</span><span class="sxs-lookup"><span data-stu-id="7e3a8-102">How to: Retrieve Entity Conflict Information</span></span>

<span data-ttu-id="7e3a8-103">Puede utilizar objetos de la clase <xref:System.Data.Linq.ObjectChangeConflict> para proporcionar información sobre los conflictos que revelan las excepciones <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="7e3a8-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="7e3a8-104">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7e3a8-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e3a8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e3a8-105">Example</span></span>  

 <span data-ttu-id="7e3a8-106">En el ejemplo siguiente se recorre en iteración una lista de conflictos acumulados.</span><span class="sxs-lookup"><span data-stu-id="7e3a8-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7e3a8-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e3a8-107">See also</span></span>

- [<span data-ttu-id="7e3a8-108">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="7e3a8-108">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
