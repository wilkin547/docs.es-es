---
title: "Cómo: Recuperar información con formato de solo lectura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a9765d8d8330c7ad2a6e8cb25166427cdd9414a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="c0926-102">Cómo: Recuperar información con formato de solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0926-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="c0926-103">Cuando no se tiene pensado cambiar los datos, puede aumentar el rendimiento de las consultas buscando resultados de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c0926-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="c0926-104">El procesamiento de solo lectura se implementa estableciendo <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c0926-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0926-105">Cuando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> se establece en `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> se establece implícitamente en `false`.</span><span class="sxs-lookup"><span data-stu-id="c0926-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0926-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0926-106">Example</span></span>  
 <span data-ttu-id="c0926-107">El código siguiente recupera una colección de solo lectura de fechas de contratación de empleados.</span><span class="sxs-lookup"><span data-stu-id="c0926-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c0926-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0926-108">See Also</span></span>  
 [<span data-ttu-id="c0926-109">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="c0926-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="c0926-110">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="c0926-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [<span data-ttu-id="c0926-111">Ejecución diferida frente a la carga inmediata</span><span class="sxs-lookup"><span data-stu-id="c0926-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
