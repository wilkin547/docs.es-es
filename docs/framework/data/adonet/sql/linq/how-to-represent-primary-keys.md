---
title: Procedimiento para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 28c62798f965edfcffe1a156213c2481a8193b49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943529"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="213fa-102">Procedimiento para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="213fa-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="213fa-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o un campo que represente la clave principal de una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="213fa-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="213fa-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="213fa-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="213fa-105">no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="213fa-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="213fa-106">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="213fa-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="213fa-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="213fa-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="213fa-108">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="213fa-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="213fa-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="213fa-109">See also</span></span>

- [<span data-ttu-id="213fa-110">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="213fa-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="213fa-111">Procedimientos: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="213fa-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
