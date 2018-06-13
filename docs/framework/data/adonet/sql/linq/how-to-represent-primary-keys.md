---
title: 'Cómo: Representar claves principales'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: dae8603a18318f45182c7148b10b8194e67fd017
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352595"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="45095-102">Cómo: Representar claves principales</span><span class="sxs-lookup"><span data-stu-id="45095-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="45095-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o campo para representar la clave principal para una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="45095-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="45095-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="45095-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="45095-105"> no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="45095-105"> does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="45095-106">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="45095-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="45095-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="45095-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="45095-108">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="45095-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45095-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="45095-109">See Also</span></span>  
 [<span data-ttu-id="45095-110">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="45095-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="45095-111">Personalización de clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="45095-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
