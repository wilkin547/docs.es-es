---
description: 'Más información acerca de cómo: representar columnas como Database-Generated'
title: Procedimiento para representar columnas como columnas generadas por la base de datos
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 01828ef3f73257d20023168f0ea471ee7e3863c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695637"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="bc327-103">Procedimiento para representar columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="bc327-103">How to: Represent Columns as Database-Generated</span></span>

<span data-ttu-id="bc327-104">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna generada por la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc327-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="bc327-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc327-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="bc327-106">Para designar que un campo o propiedad representa una columna generada por base de datos</span><span class="sxs-lookup"><span data-stu-id="bc327-106">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="bc327-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bc327-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="bc327-108">Establezca el valor de propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="bc327-108">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc327-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc327-109">See also</span></span>

- [<span data-ttu-id="bc327-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bc327-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="bc327-111">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="bc327-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
