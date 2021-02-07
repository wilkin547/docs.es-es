---
description: 'Más información acerca de cómo: representar columnas como miembros de clase'
title: Procedimiento para representar columnas como miembros de clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 81c35060298cde0081d040f1f874728c23d9c8ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695780"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="84a51-103">Procedimiento para representar columnas como miembros de clase</span><span class="sxs-lookup"><span data-stu-id="84a51-103">How to: Represent Columns as Class Members</span></span>

<span data-ttu-id="84a51-104">Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para asociar un campo o una propiedad a una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="84a51-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="84a51-105">Para asignar un campo o una propiedad a una columna de base de datos</span><span class="sxs-lookup"><span data-stu-id="84a51-105">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="84a51-106">Agregue el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> a la propiedad o declaración de campo.</span><span class="sxs-lookup"><span data-stu-id="84a51-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84a51-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84a51-107">Example</span></span>  

 <span data-ttu-id="84a51-108">El código siguiente asigna el campo `CustomerID` de la clase `Customer` a la columna `CustomerID` de la tabla de base de datos `Customers`.</span><span class="sxs-lookup"><span data-stu-id="84a51-108">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="84a51-109">No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> si se puede deducir el nombre.</span><span class="sxs-lookup"><span data-stu-id="84a51-109">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="84a51-110">Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.</span><span class="sxs-lookup"><span data-stu-id="84a51-110">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a51-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="84a51-111">See also</span></span>

- [<span data-ttu-id="84a51-112">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="84a51-112">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="84a51-113">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="84a51-113">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
