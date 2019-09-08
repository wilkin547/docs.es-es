---
title: Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793501"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="c6739-102">Procedimiento para representar columnas como columnas de marcas de tiempo o de versión</span><span class="sxs-lookup"><span data-stu-id="c6739-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="c6739-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> propiedad del <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna de base de datos que contiene marcas de tiempo de base de datos o números de versión.</span><span class="sxs-lookup"><span data-stu-id="c6739-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="c6739-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6739-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="c6739-105">Para designar que un campo o propiedad representa una columna de marca de tiempo o versión</span><span class="sxs-lookup"><span data-stu-id="c6739-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="c6739-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c6739-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="c6739-107">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="c6739-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6739-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6739-108">See also</span></span>

- [<span data-ttu-id="c6739-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c6739-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c6739-110">Procedimientos: Especificar los miembros para los que se van a probar los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="c6739-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="c6739-111">Cómo: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="c6739-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
