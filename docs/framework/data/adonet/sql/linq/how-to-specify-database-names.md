---
title: Filtrar para especificar nombres de base de datos
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 1c694678dc3a60cf91dea62f2a17973b396e2b19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184527"
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="e9d8f-102">Filtrar para especificar nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="e9d8f-102">How to: Specify Database Names</span></span>
<span data-ttu-id="e9d8f-103">Utilice la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en un atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> para especificar el nombre de una base de datos cuando la conexión no proporciona ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="e9d8f-104">Para consultar muestras de código, vea <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="e9d8f-105">Para especificar el nombre de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e9d8f-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="e9d8f-106">Agregue el atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> a la declaración de clase para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="e9d8f-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> al atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="e9d8f-108">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en el nombre que desea especificar.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d8f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9d8f-109">See also</span></span>

- [<span data-ttu-id="e9d8f-110">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e9d8f-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e9d8f-111">Filtrar para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="e9d8f-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
