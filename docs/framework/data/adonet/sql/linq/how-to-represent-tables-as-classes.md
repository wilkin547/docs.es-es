---
title: Procedimiento para representar tablas como clases
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 1169def4e0180b1d14103d4a968ff3ed56f63d0c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781762"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="7a9d5-102">Procedimiento para representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="7a9d5-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="7a9d5-103">Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9d5-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="7a9d5-104">Para asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="7a9d5-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="7a9d5-105">Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.</span><span class="sxs-lookup"><span data-stu-id="7a9d5-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a9d5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a9d5-106">Example</span></span>  
 <span data-ttu-id="7a9d5-107">El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="7a9d5-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="7a9d5-108">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="7a9d5-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="7a9d5-109">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="7a9d5-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9d5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a9d5-110">See also</span></span>

- [<span data-ttu-id="7a9d5-111">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7a9d5-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="7a9d5-112">Procedimientos: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="7a9d5-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
