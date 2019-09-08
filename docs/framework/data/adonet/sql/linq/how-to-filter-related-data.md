---
title: Procedimiento para filtrar datos relacionados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e8e63c139f38d6de46390925428e18682a65818d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793608"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="63b99-102">Procedimiento para filtrar datos relacionados</span><span class="sxs-lookup"><span data-stu-id="63b99-102">How to: Filter Related Data</span></span>
<span data-ttu-id="63b99-103">Utilice el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> para especificar subconsultas para limitar la cantidad de los datos recuperados.</span><span class="sxs-lookup"><span data-stu-id="63b99-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63b99-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63b99-104">Example</span></span>  
 <span data-ttu-id="63b99-105">En el ejemplo siguiente, el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita los `Orders` recuperados a los que no se han enviado hoy.</span><span class="sxs-lookup"><span data-stu-id="63b99-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="63b99-106">Sin este enfoque, se habrían recuperado todos los `Orders` aunque sólo se requiere un subconjunto.</span><span class="sxs-lookup"><span data-stu-id="63b99-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="63b99-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="63b99-107">See also</span></span>

- [<span data-ttu-id="63b99-108">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="63b99-108">Querying the Database</span></span>](querying-the-database.md)
