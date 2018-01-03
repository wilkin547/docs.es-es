---
title: "Parámetros (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4cbc13433b742cea1063cbd284690ce8cabbbfc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="41fd5-102">Parámetros (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="41fd5-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="41fd5-103">Los parámetros son variables que se definen fuera de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], normalmente a través de una API de enlace que se usa en un lenguaje host.</span><span class="sxs-lookup"><span data-stu-id="41fd5-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="41fd5-104">Cada parámetro tiene un nombre y un tipo.</span><span class="sxs-lookup"><span data-stu-id="41fd5-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="41fd5-105">Los nombres de los parámetros se definen en expresiones de consulta con el símbolo (@) como prefijo.</span><span class="sxs-lookup"><span data-stu-id="41fd5-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="41fd5-106">De esta forma se elimina su ambigüedad en los nombres de las propiedades o en otros nombres que se definen en la consulta.</span><span class="sxs-lookup"><span data-stu-id="41fd5-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="41fd5-107">La API de enlace de lenguaje host proporciona otras API para los parámetros de enlace.</span><span class="sxs-lookup"><span data-stu-id="41fd5-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41fd5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41fd5-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="41fd5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="41fd5-109">See Also</span></span>  
 [<span data-ttu-id="41fd5-110">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="41fd5-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="41fd5-111">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="41fd5-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
