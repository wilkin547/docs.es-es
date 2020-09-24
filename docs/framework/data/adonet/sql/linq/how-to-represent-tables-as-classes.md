---
title: Procedimiento para representar tablas como clases
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166227"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="c28e7-102">Procedimiento para representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="c28e7-102">How to: Represent Tables as Classes</span></span>

<span data-ttu-id="c28e7-103">Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c28e7-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="c28e7-104">Para asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="c28e7-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="c28e7-105">Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.</span><span class="sxs-lookup"><span data-stu-id="c28e7-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c28e7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c28e7-106">Example</span></span>  

 <span data-ttu-id="c28e7-107">El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="c28e7-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c28e7-108">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="c28e7-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="c28e7-109">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="c28e7-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c28e7-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c28e7-110">See also</span></span>

- [<span data-ttu-id="c28e7-111">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c28e7-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c28e7-112">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="c28e7-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
