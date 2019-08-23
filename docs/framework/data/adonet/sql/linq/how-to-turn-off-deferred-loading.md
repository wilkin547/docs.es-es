---
title: Procedimiento para desactivar la carga diferida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f68db5a5a0092fc4cf37746f2a4dc81e40ee4a9d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938675"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="9c0d4-102">Procedimiento para desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="9c0d4-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="9c0d4-103">Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="9c0d4-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="9c0d4-104">Para obtener más información, vea [carga aplazada frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="9c0d4-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c0d4-105">La carga aplazada se desactiva al desactivar el seguimiento de los objetos.</span><span class="sxs-lookup"><span data-stu-id="9c0d4-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="9c0d4-106">Para obtener más información, consulte [Cómo Recupera información como de solo](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)lectura.</span><span class="sxs-lookup"><span data-stu-id="9c0d4-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c0d4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c0d4-107">Example</span></span>  
 <span data-ttu-id="9c0d4-108">En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="9c0d4-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9c0d4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c0d4-109">See also</span></span>

- [<span data-ttu-id="9c0d4-110">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="9c0d4-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="9c0d4-111">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="9c0d4-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
