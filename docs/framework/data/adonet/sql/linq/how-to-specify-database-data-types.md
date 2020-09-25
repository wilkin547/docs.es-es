---
title: Procedimiento para especificar tipos de datos de base de datos
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: f070ff718ac10b9681c5ab3c0f4b46547349101b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197240"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="bd0a8-102">Procedimiento para especificar tipos de datos de base de datos</span><span class="sxs-lookup"><span data-stu-id="bd0a8-102">How to: Specify Database Data Types</span></span>

<span data-ttu-id="bd0a8-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar el texto exacto que define la columna en una declaración de tabla de T-SQL.</span><span class="sxs-lookup"><span data-stu-id="bd0a8-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="bd0a8-104">Debe especificar la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> sólo si piensa utilizar <xref:System.Data.Linq.DataContext.CreateDatabase%2A> para crear una instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bd0a8-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="bd0a8-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd0a8-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="bd0a8-106">Para especificar texto para definir un tipo de datos en una tabla T-SQL</span><span class="sxs-lookup"><span data-stu-id="bd0a8-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="bd0a8-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bd0a8-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="bd0a8-108">Establezca el valor de la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> en el texto exacto que T-SQL utiliza.</span><span class="sxs-lookup"><span data-stu-id="bd0a8-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0a8-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd0a8-109">See also</span></span>

- [<span data-ttu-id="bd0a8-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bd0a8-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="bd0a8-111">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="bd0a8-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
