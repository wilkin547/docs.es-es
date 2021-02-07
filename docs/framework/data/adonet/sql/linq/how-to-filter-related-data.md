---
description: 'Más información acerca de cómo: filtrar datos relacionados'
title: Procedimiento para filtrar datos relacionados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: d44e0805b82c0c58f9ee19808e078f9f9b337050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738954"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="04d62-103">Procedimiento para filtrar datos relacionados</span><span class="sxs-lookup"><span data-stu-id="04d62-103">How to: Filter Related Data</span></span>

<span data-ttu-id="04d62-104">Utilice el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> para especificar subconsultas para limitar la cantidad de los datos recuperados.</span><span class="sxs-lookup"><span data-stu-id="04d62-104">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04d62-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04d62-105">Example</span></span>  

 <span data-ttu-id="04d62-106">En el ejemplo siguiente, el método <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita los `Orders` recuperados a los que no se han enviado hoy.</span><span class="sxs-lookup"><span data-stu-id="04d62-106">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="04d62-107">Sin este enfoque, se habrían recuperado todos los `Orders` aunque sólo se requiere un subconjunto.</span><span class="sxs-lookup"><span data-stu-id="04d62-107">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="04d62-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="04d62-108">See also</span></span>

- [<span data-ttu-id="04d62-109">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="04d62-109">Querying the Database</span></span>](querying-the-database.md)
