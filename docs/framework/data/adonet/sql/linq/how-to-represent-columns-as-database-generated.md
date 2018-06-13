---
title: 'Cómo: Representar columnas como columnas generadas por la base de datos'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: f6b127208ae359b43f273f54d7b5c72933c2eba6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353746"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="2df08-102">Cómo: Representar columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="2df08-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="2df08-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar un campo o propiedad representa una columna generada por base de datos.</span><span class="sxs-lookup"><span data-stu-id="2df08-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="2df08-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="2df08-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="2df08-105">Para designar que un campo o propiedad representa una columna generada por base de datos</span><span class="sxs-lookup"><span data-stu-id="2df08-105">To designate a field or property as representing a database-generated column</span></span>  
  
1.  <span data-ttu-id="2df08-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2df08-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="2df08-107">Establezca el valor de propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="2df08-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df08-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df08-108">See Also</span></span>  
 [<span data-ttu-id="2df08-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2df08-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="2df08-110">Personalización de clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="2df08-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
