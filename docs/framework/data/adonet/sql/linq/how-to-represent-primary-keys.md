---
title: Filtrar para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 714211046afcafab4c2b67bf9318cfbede314476
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173217"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="e2e25-102">Filtrar para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="e2e25-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="e2e25-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o campo para representar la clave principal para una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2e25-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="e2e25-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2e25-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e2e25-105">no admite columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="e2e25-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="e2e25-106">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="e2e25-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="e2e25-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2e25-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="e2e25-108">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="e2e25-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e25-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2e25-109">See also</span></span>

- [<span data-ttu-id="e2e25-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e2e25-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e2e25-111">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="e2e25-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
