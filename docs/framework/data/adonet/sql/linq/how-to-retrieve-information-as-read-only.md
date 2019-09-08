---
title: Procedimiento para recuperar información con formato de solo lectura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 399bf44ef5536a9adebf1cad590439741df998f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793317"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="37271-102">Procedimiento para recuperar información con formato de solo lectura</span><span class="sxs-lookup"><span data-stu-id="37271-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="37271-103">Cuando no se tiene pensado cambiar los datos, puede aumentar el rendimiento de las consultas buscando resultados de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="37271-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="37271-104">El procesamiento de solo lectura se implementa estableciendo <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="37271-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37271-105">Cuando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> se establece en `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> se establece implícitamente en `false`.</span><span class="sxs-lookup"><span data-stu-id="37271-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37271-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37271-106">Example</span></span>  
 <span data-ttu-id="37271-107">El código siguiente recupera una colección de solo lectura de fechas de contratación de empleados.</span><span class="sxs-lookup"><span data-stu-id="37271-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="37271-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="37271-108">See also</span></span>

- [<span data-ttu-id="37271-109">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="37271-109">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="37271-110">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="37271-110">Querying the Database</span></span>](querying-the-database.md)
- [<span data-ttu-id="37271-111">Carga inmediata y carga diferida</span><span class="sxs-lookup"><span data-stu-id="37271-111">Deferred versus Immediate Loading</span></span>](deferred-versus-immediate-loading.md)
