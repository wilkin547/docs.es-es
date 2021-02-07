---
description: 'Más información sobre: Cómo: representar columnas como permitir valores NULL'
title: Procedimiento para representar columnas como columnas que permiten valores null
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 019affd13fa9c2629c6a0ec66c42f19842a4d824
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695910"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="93e01-103">Procedimiento para representar columnas como columnas que permiten valores null</span><span class="sxs-lookup"><span data-stu-id="93e01-103">How to: Represent Columns as Allowing Null Values</span></span>

<span data-ttu-id="93e01-104">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que la columna de base de datos asociada puede contener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="93e01-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="93e01-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="93e01-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="93e01-106">Para designar que una columna permite valores nulos</span><span class="sxs-lookup"><span data-stu-id="93e01-106">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="93e01-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="93e01-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="93e01-108">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="93e01-108">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e01-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="93e01-109">See also</span></span>

- [<span data-ttu-id="93e01-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="93e01-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="93e01-111">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="93e01-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
