---
description: 'Más información acerca de cómo: controlar la cantidad de datos relacionados que se recuperan'
title: Procedimiento para controlar la cantidad de datos relacionados que se recupera
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: becf1282d18d5c630da3e3be27c62ebae404d940
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786048"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="4f0c7-103">Procedimiento para controlar la cantidad de datos relacionados que se recupera</span><span class="sxs-lookup"><span data-stu-id="4f0c7-103">How to: Control How Much Related Data Is Retrieved</span></span>

<span data-ttu-id="4f0c7-104">Utilice el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para especificar qué datos relacionados con el destino principal deben recuperarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-104">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="4f0c7-105">Por ejemplo, si sabe que va a necesitar información sobre los pedidos de los clientes, puede utilizar <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para asegurarse de que la información de los pedidos se va a recuperar al mismo tiempo que la información de los clientes.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-105">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="4f0c7-106">Con este enfoque, sólo se requiere un viaje a la base de datos para ambos conjuntos de información.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-106">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f0c7-107">Puede recuperar datos relacionados con el destino principal de la consulta recuperando un producto cruzado como una gran proyección; por ejemplo, puede recuperar los pedidos cuando el destino de la consulta son los clientes.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-107">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="4f0c7-108">Sin embargo, este enfoque a menudo tiene desventajas.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-108">But this approach often has disadvantages.</span></span> <span data-ttu-id="4f0c7-109">Por ejemplo, los resultados son simples proyecciones, no entidades que se puedan cambiar y conservar mediante [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0c7-109">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4f0c7-110">Además, podría recuperar una gran cantidad de datos que no necesita.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-110">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f0c7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f0c7-111">Example</span></span>  

 <span data-ttu-id="4f0c7-112">En el siguiente ejemplo, se recuperan todos los `Orders` de todos los `Customers` de Londres cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-112">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="4f0c7-113">En consecuencia, el acceso posterior a la propiedad `Orders` de un objeto `Customer` no desencadena una nueva consulta de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4f0c7-113">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4f0c7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f0c7-114">See also</span></span>

- [<span data-ttu-id="4f0c7-115">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="4f0c7-115">Querying the Database</span></span>](querying-the-database.md)
