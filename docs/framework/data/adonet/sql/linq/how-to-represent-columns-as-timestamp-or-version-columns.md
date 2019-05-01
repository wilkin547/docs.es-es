---
title: Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: db73bf4880d8f5556247f7b037fca24b0ddc56d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037744"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="2aa04-102">Procedimiento para representar columnas como columnas de marcas de tiempo o de versión</span><span class="sxs-lookup"><span data-stu-id="2aa04-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="2aa04-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> propiedad de la <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar un campo o propiedad representa una columna de base de datos que contiene los números de marcas de tiempo o una versión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2aa04-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="2aa04-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="2aa04-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="2aa04-105">Para designar que un campo o propiedad representa una columna de marca de tiempo o versión</span><span class="sxs-lookup"><span data-stu-id="2aa04-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="2aa04-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2aa04-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="2aa04-107">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="2aa04-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa04-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aa04-108">See also</span></span>

- [<span data-ttu-id="2aa04-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2aa04-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="2aa04-110">Cómo: Especificar que los miembros se comprueban los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="2aa04-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="2aa04-111">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="2aa04-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
