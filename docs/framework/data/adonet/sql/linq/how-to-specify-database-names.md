---
title: "Cómo: Especificar nombres de base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d0dffe22205b2d59dbd77bcd8f86efe4fa56be3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="e706d-102">Cómo: Especificar nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="e706d-102">How to: Specify Database Names</span></span>
<span data-ttu-id="e706d-103">Utilice la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en un atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> para especificar el nombre de una base de datos cuando la conexión no proporciona ninguno.</span><span class="sxs-lookup"><span data-stu-id="e706d-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="e706d-104">Para consultar muestras de código, vea <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="e706d-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="e706d-105">Para especificar el nombre de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e706d-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="e706d-106">Agregue el atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> a la declaración de clase para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e706d-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="e706d-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> al atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e706d-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="e706d-108">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en el nombre que desea especificar.</span><span class="sxs-lookup"><span data-stu-id="e706d-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e706d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e706d-109">See Also</span></span>  
 [<span data-ttu-id="e706d-110">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e706d-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="e706d-111">Personalización de clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="e706d-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
