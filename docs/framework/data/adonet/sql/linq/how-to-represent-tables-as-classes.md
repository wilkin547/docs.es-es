---
title: Filtrar para representar tablas como clases
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 49e7d6768d8739bba94c9e8d38bcc582c8bd6e4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073140"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="e631c-102">Filtrar para representar tablas como clases</span><span class="sxs-lookup"><span data-stu-id="e631c-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="e631c-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e631c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="e631c-104">Para asignar una clase a una tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="e631c-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="e631c-105">Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.</span><span class="sxs-lookup"><span data-stu-id="e631c-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e631c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e631c-106">Example</span></span>  
 <span data-ttu-id="e631c-107">El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="e631c-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="e631c-108">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="e631c-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="e631c-109">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="e631c-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e631c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e631c-110">See also</span></span>

- [<span data-ttu-id="e631c-111">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e631c-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e631c-112">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="e631c-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
