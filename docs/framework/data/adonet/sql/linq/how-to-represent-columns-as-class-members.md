---
title: Filtrar para representar columnas como miembros de clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 74966dd1661faa43df334987b2e3b0e84eff3446
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074006"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="f5751-102">Filtrar para representar columnas como miembros de clase</span><span class="sxs-lookup"><span data-stu-id="f5751-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="f5751-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para asociar una columna de base de datos en un campo o propiedad.</span><span class="sxs-lookup"><span data-stu-id="f5751-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="f5751-104">Para asignar un campo o una propiedad a una columna de base de datos</span><span class="sxs-lookup"><span data-stu-id="f5751-104">To map a field or property to a database column</span></span>  
  
-   <span data-ttu-id="f5751-105">Agregue el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> a la propiedad o declaración de campo.</span><span class="sxs-lookup"><span data-stu-id="f5751-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5751-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5751-106">Example</span></span>  
 <span data-ttu-id="f5751-107">El código siguiente asigna el campo `CustomerID` de la clase `Customer` a la columna `CustomerID` de la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="f5751-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="f5751-108">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="f5751-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="f5751-109">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="f5751-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5751-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5751-110">See also</span></span>

- [<span data-ttu-id="f5751-111">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f5751-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f5751-112">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="f5751-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
