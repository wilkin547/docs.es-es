---
description: 'Más información acerca de cómo: representar columnas como marcas de tiempo o columnas de versión'
title: Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: 042e6a62c66b3f1ef522453157560e5e4c0f7de6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712511"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="b4876-103">Procedimiento para representar columnas como columnas de marcas de tiempo o de versión</span><span class="sxs-lookup"><span data-stu-id="b4876-103">How to: Represent Columns as Timestamp or Version Columns</span></span>

<span data-ttu-id="b4876-104">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> propiedad del <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna de base de datos que contiene marcas de tiempo de base de datos o números de versión.</span><span class="sxs-lookup"><span data-stu-id="b4876-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="b4876-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b4876-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="b4876-106">Para designar que un campo o propiedad representa una columna de marca de tiempo o versión</span><span class="sxs-lookup"><span data-stu-id="b4876-106">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="b4876-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b4876-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="b4876-108">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="b4876-108">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4876-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4876-109">See also</span></span>

- [<span data-ttu-id="b4876-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b4876-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="b4876-111">Procedimiento para especificar en qué miembros se comprueban los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="b4876-111">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="b4876-112">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="b4876-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
