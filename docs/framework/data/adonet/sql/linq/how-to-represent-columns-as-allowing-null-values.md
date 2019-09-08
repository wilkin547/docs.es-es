---
title: Procedimiento para representar columnas como columnas que permiten valores null
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781810"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="c2a25-102">Procedimiento para representar columnas como columnas que permiten valores null</span><span class="sxs-lookup"><span data-stu-id="c2a25-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="c2a25-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que la columna de base de datos asociada puede contener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="c2a25-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="c2a25-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2a25-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="c2a25-105">Para designar que una columna permite valores nulos</span><span class="sxs-lookup"><span data-stu-id="c2a25-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="c2a25-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c2a25-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="c2a25-107">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="c2a25-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a25-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a25-108">See also</span></span>

- [<span data-ttu-id="c2a25-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c2a25-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c2a25-110">Cómo: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="c2a25-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
