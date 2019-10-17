---
title: Parámetros (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 8fbca4f10a7c2c3dbaffff978a536b87d31a8df4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319431"
---
# <a name="parameters-entity-sql"></a>Parámetros (Entity SQL)
Los parámetros son variables que se definen fuera de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], normalmente a través de una API de enlace que se usa en un lenguaje host. Cada parámetro tiene un nombre y un tipo. Los nombres de los parámetros se definen en expresiones de consulta con el símbolo (@) como prefijo. De esta forma se elimina su ambigüedad en los nombres de las propiedades o en otros nombres que se definen en la consulta.  
  
 La API de enlace de lenguaje host proporciona otras API para los parámetros de enlace.  
  
## <a name="example"></a>Ejemplo  
  
```sql  
SELECT c   
      FROM LOB.Customers AS c   
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
