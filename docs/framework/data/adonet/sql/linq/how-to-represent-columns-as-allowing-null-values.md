---
title: Procedimiento para representar columnas como columnas que permiten valores null
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ef8fa87963b91ef7140fbaefb657fc7904604b5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902920"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="39585-102">Procedimiento para representar columnas como columnas que permiten valores null</span><span class="sxs-lookup"><span data-stu-id="39585-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="39585-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que la columna de base de datos asociada puede contener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="39585-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="39585-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="39585-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="39585-105">Para designar que una columna permite valores nulos</span><span class="sxs-lookup"><span data-stu-id="39585-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="39585-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="39585-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="39585-107">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="39585-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39585-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="39585-108">See also</span></span>

- [<span data-ttu-id="39585-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="39585-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="39585-110">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="39585-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
