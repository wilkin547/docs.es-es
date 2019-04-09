---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 6a5b374bc253cb2deb7a9e1de942c32d8e8bbfcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168030"
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Especifica espacios de nombres que se usan en una expresión de consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argumentos  
 `alias`  
 Especifica un alias más breve con el que calificar un espacio de nombres.  
  
 `namespace`  
 Cualquier espacio de nombres válido.  
  
## <a name="example"></a>Ejemplo  
 En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Vea también

- [Espacios de nombres](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
