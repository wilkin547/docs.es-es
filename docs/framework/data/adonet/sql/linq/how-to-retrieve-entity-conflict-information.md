---
title: Filtrar para recuperar información de conflictos de entidades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 825ba2a32e7c75e922ca08386b9f6efede7b2693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154757"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="a9713-102">Filtrar para recuperar información de conflictos de entidades</span><span class="sxs-lookup"><span data-stu-id="a9713-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="a9713-103">Puede utilizar objetos de la clase <xref:System.Data.Linq.ObjectChangeConflict> para proporcionar información sobre los conflictos que revelan las excepciones <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="a9713-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="a9713-104">Para obtener más información, consulte [simultaneidad optimista: Información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9713-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9713-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9713-105">Example</span></span>  
 <span data-ttu-id="a9713-106">En el ejemplo siguiente se recorre en iteración una lista de conflictos acumulados.</span><span class="sxs-lookup"><span data-stu-id="a9713-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a9713-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9713-107">See also</span></span>

- [<span data-ttu-id="a9713-108">Filtrar para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="a9713-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
