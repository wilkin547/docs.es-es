---
title: Procedimiento para especificar tipos de datos de base de datos
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 67f23ff06aefbcff4ba7e2eaab63d9b8493b9717
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033675"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="d64f5-102">Procedimiento para especificar tipos de datos de base de datos</span><span class="sxs-lookup"><span data-stu-id="d64f5-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="d64f5-103">Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar el texto exacto que define la columna en una declaración de tabla de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d64f5-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="d64f5-104">Debe especificar la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> sólo si piensa utilizar <xref:System.Data.Linq.DataContext.CreateDatabase%2A> para crear una instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d64f5-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="d64f5-105">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d64f5-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="d64f5-106">Para especificar texto para definir un tipo de datos en una tabla T-SQL</span><span class="sxs-lookup"><span data-stu-id="d64f5-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="d64f5-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d64f5-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="d64f5-108">Establezca el valor de la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> en el texto exacto que T-SQL utiliza.</span><span class="sxs-lookup"><span data-stu-id="d64f5-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64f5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d64f5-109">See also</span></span>

- [<span data-ttu-id="d64f5-110">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d64f5-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="d64f5-111">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="d64f5-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
