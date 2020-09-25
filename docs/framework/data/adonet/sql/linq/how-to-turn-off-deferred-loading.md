---
title: Procedimiento para desactivar la carga diferida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: b2193e7e8bda396451274d2da96e7cb86774fd03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196967"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="4475d-102">Procedimiento para desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="4475d-102">How to: Turn Off Deferred Loading</span></span>

<span data-ttu-id="4475d-103">Puede desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="4475d-103">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="4475d-104">Para obtener más información, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="4475d-104">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4475d-105">La carga aplazada se desactiva al desactivar el seguimiento de los objetos.</span><span class="sxs-lookup"><span data-stu-id="4475d-105">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="4475d-106">Para obtener más información, vea [Cómo: recuperar información como de solo lectura](how-to-retrieve-information-as-read-only.md).</span><span class="sxs-lookup"><span data-stu-id="4475d-106">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4475d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4475d-107">Example</span></span>  

 <span data-ttu-id="4475d-108">En el ejemplo siguiente se muestra cómo desactivar la carga aplazada al establecer <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="4475d-108">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4475d-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4475d-109">See also</span></span>

- [<span data-ttu-id="4475d-110">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="4475d-110">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="4475d-111">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="4475d-111">Querying the Database</span></span>](querying-the-database.md)
