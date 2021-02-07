---
description: 'Más información acerca de cómo: representar claves principales'
title: Procedimiento para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 1fbac2d60bd730718b5330bfd48910a61deae15c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723613"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="efa9d-103">Procedimiento para representar claves principales</span><span class="sxs-lookup"><span data-stu-id="efa9d-103">How to: Represent Primary Keys</span></span>

<span data-ttu-id="efa9d-104">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o un campo que represente la clave principal de una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="efa9d-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="efa9d-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="efa9d-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="efa9d-106">no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="efa9d-106">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="efa9d-107">Para designar una propiedad o un campo como clave principal</span><span class="sxs-lookup"><span data-stu-id="efa9d-107">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="efa9d-108">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="efa9d-108">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="efa9d-109">Especifique el valor como `true`.</span><span class="sxs-lookup"><span data-stu-id="efa9d-109">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa9d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa9d-110">See also</span></span>

- [<span data-ttu-id="efa9d-111">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="efa9d-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="efa9d-112">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="efa9d-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
