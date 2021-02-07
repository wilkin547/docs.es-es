---
description: 'Más información acerca de cómo: recuperar información de conflictos de entidades'
title: Procedimiento para recuperar información de conflictos de entidades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: dde11a431ae977595b9845444e48705a4552fb23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767757"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="aec06-103">Procedimiento para recuperar información de conflictos de entidades</span><span class="sxs-lookup"><span data-stu-id="aec06-103">How to: Retrieve Entity Conflict Information</span></span>

<span data-ttu-id="aec06-104">Puede utilizar objetos de la clase <xref:System.Data.Linq.ObjectChangeConflict> para proporcionar información sobre los conflictos que revelan las excepciones <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="aec06-104">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="aec06-105">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aec06-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec06-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aec06-106">Example</span></span>  

 <span data-ttu-id="aec06-107">En el ejemplo siguiente se recorre en iteración una lista de conflictos acumulados.</span><span class="sxs-lookup"><span data-stu-id="aec06-107">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="aec06-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec06-108">See also</span></span>

- [<span data-ttu-id="aec06-109">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="aec06-109">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
