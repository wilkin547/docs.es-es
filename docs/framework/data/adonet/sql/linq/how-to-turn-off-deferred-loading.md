---
title: Procedimiento para desactivar la carga diferida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f82e347ecdb3c69cee3749855d1e4cb457a460f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033623"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="c4802-102">Procedimiento para desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="c4802-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="c4802-103">Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c4802-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="c4802-104">Para obtener más información, consulte [carga inmediata y carga diferida](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="c4802-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4802-105">La carga aplazada se desactiva al desactivar el seguimiento de los objetos.</span><span class="sxs-lookup"><span data-stu-id="c4802-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="c4802-106">Para obtener más información, vea [Cómo: Recuperar información como de solo lectura](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="c4802-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4802-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4802-107">Example</span></span>  
 <span data-ttu-id="c4802-108">En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c4802-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c4802-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4802-109">See also</span></span>

- [<span data-ttu-id="c4802-110">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="c4802-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="c4802-111">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c4802-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
