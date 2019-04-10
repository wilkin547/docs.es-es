---
title: Filtrar para representar columnas como columnas generadas por la base de datos
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2803697c668a8e1dbbeb426ea41b64878f70c145
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307917"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="d10fa-102">Filtrar para representar columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="d10fa-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="d10fa-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar un campo o propiedad representa una columna generada por base de datos.</span><span class="sxs-lookup"><span data-stu-id="d10fa-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="d10fa-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="d10fa-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="d10fa-105">Para designar que un campo o propiedad representa una columna generada por base de datos</span><span class="sxs-lookup"><span data-stu-id="d10fa-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="d10fa-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d10fa-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="d10fa-107">Establezca el valor de propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="d10fa-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10fa-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d10fa-108">See also</span></span>

- [<span data-ttu-id="d10fa-109">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d10fa-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="d10fa-110">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="d10fa-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
