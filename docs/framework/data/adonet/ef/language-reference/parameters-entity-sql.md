---
title: Parámetros (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187682"
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

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
