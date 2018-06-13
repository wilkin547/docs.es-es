---
title: Parámetros (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: c8bdb54e52b4c0d189f3bff72bdb24785c1a9c27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765079"
---
# <a name="parameters-entity-sql"></a>Parámetros (Entity SQL)
Los parámetros son variables que se definen fuera de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], normalmente a través de una API de enlace que se usa en un lenguaje host. Cada parámetro tiene un nombre y un tipo. Los nombres de los parámetros se definen en expresiones de consulta con el símbolo (@) como prefijo. De esta forma se elimina su ambigüedad en los nombres de las propiedades o en otros nombres que se definen en la consulta.  
  
 La API de enlace de lenguaje host proporciona otras API para los parámetros de enlace.  
  
## <a name="example"></a>Ejemplo  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
