---
description: 'Más información acerca de cómo: representar columnas calculadas'
title: Procedimiento para representar columnas calculadas
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 5f3b4898cd29c148665c6696b0b3abab42bd071c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695624"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="04b6f-103">Procedimiento para representar columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="04b6f-103">How to: Represent Computed Columns</span></span>

<span data-ttu-id="04b6f-104">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para representar una columna cuyo contenido es el resultado del cálculo.</span><span class="sxs-lookup"><span data-stu-id="04b6f-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="04b6f-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="04b6f-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="04b6f-106">no admite las columnas calculadas como claves principales.</span><span class="sxs-lookup"><span data-stu-id="04b6f-106">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="04b6f-107">Para representar una columna calculada</span><span class="sxs-lookup"><span data-stu-id="04b6f-107">To represent a computed column</span></span>  
  
1. <span data-ttu-id="04b6f-108">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="04b6f-108">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="04b6f-109">Asigne una representación de cadena de la fórmula a la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="04b6f-109">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b6f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="04b6f-110">See also</span></span>

- [<span data-ttu-id="04b6f-111">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="04b6f-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="04b6f-112">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="04b6f-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
