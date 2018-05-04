---
title: Expresiones de consulta (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: d721f54486845847ec86253356e7a605f882722b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="query-expressions-entity-sql"></a>Expresiones de consulta (Entity SQL)
Una expresión de consulta combina muchos operadores de consulta diferentes en una sintaxis única. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona varios tipos de expresiones, incluidos los siguientes: [literales](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parámetros](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variables](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operadores, [funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), operadores de conjuntos y así sucesivamente. Para obtener más información, consulte [Entity SQL Reference](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Cláusulas  
 Una expresión de consulta se compone de una serie de cláusulas que aplican operaciones sucesivas a una colección de objetos. Se basan en las mismas cláusulas que se encuentra en el estándar de una instrucción select de SQL: [seleccione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [donde](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [Tener](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), y [se ORDENA por](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Ámbito  
 Los nombres que se definen en la cláusula FROM se incluyen en el ámbito de FROM en orden de aparición, de izquierda a derecha. En la lista de JOIN, las expresiones pueden hacer referencia a los nombres que se definieron en la lista anteriormente. Las propiedades públicas de los elementos identificados en la cláusula FROM no se agregan al ámbito de FROM. Siempre se debe hacer referencia a ellas mediante el nombre completo del alias. Normalmente, todas las partes de la expresión SELECT se consideran dentro del ámbito de FROM.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
