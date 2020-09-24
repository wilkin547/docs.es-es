---
title: Procedimiento para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 02570176c8aef5cfdc7ba09fd6976f430900e8df
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166240"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="32f59-102">Procedimiento para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="32f59-102">How to: Represent Primary Keys</span></span>

<span data-ttu-id="32f59-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o un campo que represente la clave principal de una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f59-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="32f59-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="32f59-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="32f59-105">no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="32f59-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="32f59-106">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="32f59-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="32f59-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32f59-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="32f59-108">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="32f59-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f59-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32f59-109">See also</span></span>

- [<span data-ttu-id="32f59-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="32f59-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="32f59-111">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="32f59-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
