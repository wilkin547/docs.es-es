---
description: 'Más información acerca de cómo: representar tablas como clases'
title: Procedimiento para representar tablas como clases
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 9ec5b7309d7d10eaa6e4da6cd6fe4b1d03df1dd9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723587"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="c86f2-103">Procedimiento para representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="c86f2-103">How to: Represent Tables as Classes</span></span>

<span data-ttu-id="c86f2-104">Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c86f2-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="c86f2-105">Para asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="c86f2-105">To map a class to a database table</span></span>  
  
- <span data-ttu-id="c86f2-106">Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.</span><span class="sxs-lookup"><span data-stu-id="c86f2-106">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c86f2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86f2-107">Example</span></span>  

 <span data-ttu-id="c86f2-108">El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="c86f2-108">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c86f2-109">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="c86f2-109">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="c86f2-110">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="c86f2-110">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86f2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c86f2-111">See also</span></span>

- [<span data-ttu-id="c86f2-112">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c86f2-112">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c86f2-113">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="c86f2-113">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
