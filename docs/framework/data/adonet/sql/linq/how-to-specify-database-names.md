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
ms.openlocfilehash: 998a720f4e2cd7c3a63578d1025d0dd7b42a1b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="56818-102">Cómo: Especificar nombres de base de datos</span><span class="sxs-lookup"><span data-stu-id="56818-102">How to: Specify Database Names</span></span>
<span data-ttu-id="56818-103">Utilice la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en un atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> para especificar el nombre de una base de datos cuando la conexión no proporciona ninguno.</span><span class="sxs-lookup"><span data-stu-id="56818-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="56818-104">Para consultar muestras de código, vea <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="56818-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="56818-105">Para especificar el nombre de la base de datos</span><span class="sxs-lookup"><span data-stu-id="56818-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="56818-106">Agregue el atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> a la declaración de clase para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="56818-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="56818-107">Agregue la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> al atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.</span><span class="sxs-lookup"><span data-stu-id="56818-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="56818-108">Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en el nombre que desea especificar.</span><span class="sxs-lookup"><span data-stu-id="56818-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56818-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="56818-109">See Also</span></span>  
 [<span data-ttu-id="56818-110">El modelo de LINQ to SQL objeto</span><span class="sxs-lookup"><span data-stu-id="56818-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="56818-111">Cómo: personalizar clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="56818-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
