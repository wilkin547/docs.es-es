---
title: Procedimiento para recuperar información con formato de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: b98c5e6ea49695015eb566ca2176b23c5260017a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928711"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="9e6ad-102">Procedimiento para recuperar información con formato de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9e6ad-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="9e6ad-103">Cuando no se tiene pensado cambiar los datos, puede aumentar el rendimiento de las consultas buscando resultados de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="9e6ad-104">El procesamiento de solo lectura se implementa estableciendo <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e6ad-105">Cuando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> se establece en `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> se establece implícitamente en `false`.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e6ad-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e6ad-106">Example</span></span>  
 <span data-ttu-id="9e6ad-107">El código siguiente recupera una colección de solo lectura de fechas de contratación de empleados.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e6ad-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e6ad-108">See also</span></span>

- [<span data-ttu-id="9e6ad-109">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="9e6ad-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="9e6ad-110">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="9e6ad-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="9e6ad-111">Carga inmediata y carga diferida</span><span class="sxs-lookup"><span data-stu-id="9e6ad-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
