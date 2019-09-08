---
title: Procedimiento para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 5df82292f000d7f5e61cab699237b86de30bda70
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793431"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="1d0f4-102">Procedimiento para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="1d0f4-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="1d0f4-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o un campo que represente la clave principal de una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d0f4-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="1d0f4-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d0f4-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="1d0f4-105">no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="1d0f4-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="1d0f4-106">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="1d0f4-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="1d0f4-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1d0f4-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="1d0f4-108">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="1d0f4-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0f4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d0f4-109">See also</span></span>

- [<span data-ttu-id="1d0f4-110">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1d0f4-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="1d0f4-111">Procedimientos: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="1d0f4-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
