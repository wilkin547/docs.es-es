---
title: 'Cómo: Desactivar la carga diferida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 279317f10211271fad812068215b08a93e30fbdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358650"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="23a51-102">Cómo: Desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="23a51-102">How to: Turn Off Deferred Loading</span></span>
<span data-ttu-id="23a51-103">Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="23a51-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="23a51-104">Para obtener más información, consulte [ejecución diferida frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="23a51-104">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23a51-105">La carga aplazada se desactiva al desactivar el seguimiento de los objetos.</span><span class="sxs-lookup"><span data-stu-id="23a51-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="23a51-106">Para obtener más información, consulte [Cómo: recuperar información como sólo lectura](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="23a51-106">For more information, see [How to: Retrieve Information As Read-Only](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23a51-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23a51-107">Example</span></span>  
 <span data-ttu-id="23a51-108">En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="23a51-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="23a51-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="23a51-109">See Also</span></span>  
 [<span data-ttu-id="23a51-110">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="23a51-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="23a51-111">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="23a51-111">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
