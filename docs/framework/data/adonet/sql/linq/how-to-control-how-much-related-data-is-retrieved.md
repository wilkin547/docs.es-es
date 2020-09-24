---
title: Procedimiento para controlar la cantidad de datos relacionados que se recupera
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: 77ac29eeeaa30ef438b635364dc8e883a0e4c158
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161339"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="d5003-102">Procedimiento para controlar la cantidad de datos relacionados que se recupera</span><span class="sxs-lookup"><span data-stu-id="d5003-102">How to: Control How Much Related Data Is Retrieved</span></span>

<span data-ttu-id="d5003-103">Utilice el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para especificar qué datos relacionados con el destino principal deben recuperarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d5003-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="d5003-104">Por ejemplo, si sabe que va a necesitar información sobre los pedidos de los clientes, puede utilizar <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para asegurarse de que la información de los pedidos se va a recuperar al mismo tiempo que la información de los clientes.</span><span class="sxs-lookup"><span data-stu-id="d5003-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="d5003-105">Con este enfoque, sólo se requiere un viaje a la base de datos para ambos conjuntos de información.</span><span class="sxs-lookup"><span data-stu-id="d5003-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5003-106">Puede recuperar datos relacionados con el destino principal de la consulta recuperando un producto cruzado como una gran proyección; por ejemplo, puede recuperar los pedidos cuando el destino de la consulta son los clientes.</span><span class="sxs-lookup"><span data-stu-id="d5003-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="d5003-107">Sin embargo, este enfoque a menudo tiene desventajas.</span><span class="sxs-lookup"><span data-stu-id="d5003-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="d5003-108">Por ejemplo, los resultados son simples proyecciones, no entidades que se puedan cambiar y conservar mediante [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5003-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="d5003-109">Además, podría recuperar una gran cantidad de datos que no necesita.</span><span class="sxs-lookup"><span data-stu-id="d5003-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5003-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5003-110">Example</span></span>  

 <span data-ttu-id="d5003-111">En el siguiente ejemplo, se recuperan todos los `Orders` de todos los `Customers` de Londres cuando se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="d5003-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="d5003-112">En consecuencia, el acceso posterior a la propiedad `Orders` de un objeto `Customer` no desencadena una nueva consulta de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d5003-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d5003-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5003-113">See also</span></span>

- [<span data-ttu-id="d5003-114">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="d5003-114">Querying the Database</span></span>](querying-the-database.md)
