---
title: Procedimiento para filtrar datos relacionados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218230"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="e9ac3-102">Procedimiento para filtrar datos relacionados</span><span class="sxs-lookup"><span data-stu-id="e9ac3-102">How to: Filter Related Data</span></span>
<span data-ttu-id="e9ac3-103">Utilice el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> para especificar subconsultas para limitar la cantidad de los datos recuperados.</span><span class="sxs-lookup"><span data-stu-id="e9ac3-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ac3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9ac3-104">Example</span></span>  
 <span data-ttu-id="e9ac3-105">En el ejemplo siguiente, el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita los `Orders` recuperados a los que no se han enviado hoy.</span><span class="sxs-lookup"><span data-stu-id="e9ac3-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="e9ac3-106">Sin este enfoque, se habrían recuperado todos los `Orders` aunque sólo se requiere un subconjunto.</span><span class="sxs-lookup"><span data-stu-id="e9ac3-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e9ac3-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9ac3-107">See also</span></span>

- [<span data-ttu-id="e9ac3-108">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e9ac3-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
