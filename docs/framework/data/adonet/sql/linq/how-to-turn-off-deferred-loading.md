---
description: 'Más información acerca de cómo: desactivar la carga aplazada'
title: Procedimiento para desactivar la carga diferida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 739c9b0b65eda73d6c504409395eb805b0c02873
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785840"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="7359a-103">Procedimiento para desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="7359a-103">How to: Turn Off Deferred Loading</span></span>

<span data-ttu-id="7359a-104">Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="7359a-104">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="7359a-105">Para obtener más información, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="7359a-105">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7359a-106">La carga aplazada se desactiva al desactivar el seguimiento de los objetos.</span><span class="sxs-lookup"><span data-stu-id="7359a-106">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="7359a-107">Para obtener más información, vea [Cómo: recuperar información como de solo lectura](how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="7359a-107">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7359a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7359a-108">Example</span></span>  

 <span data-ttu-id="7359a-109">En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="7359a-109">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7359a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7359a-110">See also</span></span>

- [<span data-ttu-id="7359a-111">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="7359a-111">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="7359a-112">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="7359a-112">Querying the Database</span></span>](querying-the-database.md)
