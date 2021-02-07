---
description: 'Más información acerca de: expresiones de consulta (Entity SQL)'
title: Expresiones de consulta (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 218e7db0e812bd43a92d3145bc4bf96244ef6a3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696040"
---
# <a name="query-expressions-entity-sql"></a>Expresiones de consulta (Entity SQL)

Una expresión de consulta combina muchos operadores de consulta diferentes en una sintaxis única. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona varios tipos de expresiones, entre las que se incluyen los [literales](literals-entity-sql.md), [parámetros](parameters-entity-sql.md), [variables](variables-entity-sql.md), operadores, [funciones](functions-entity-sql.md), operadores de conjuntos, etc. Para obtener más información, vea [referencia de Entity SQL](entity-sql-reference.md).  
  
## <a name="clauses"></a>Cláusulas  

 Una expresión de consulta se compone de una serie de cláusulas que aplican operaciones sucesivas a una colección de objetos. Se basan en las mismas cláusulas que se encuentran en una instrucción SELECT de SQL estándar: [Select](select-entity-sql.md), [from](from-entity-sql.md), [Where](where-entity-sql.md), [Group by](group-by-entity-sql.md), [having](having-entity-sql.md)y [order by](order-by-entity-sql.md).  
  
## <a name="scope"></a>Ámbito  

 Los nombres que se definen en la cláusula FROM se incluyen en el ámbito de FROM en orden de aparición, de izquierda a derecha. En la lista de JOIN, las expresiones pueden hacer referencia a los nombres que se definieron en la lista anteriormente. Las propiedades públicas de los elementos identificados en la cláusula FROM no se agregan al ámbito de FROM. Siempre se debe hacer referencia a ellas mediante el nombre completo del alias. Normalmente, todas las partes de la expresión SELECT se consideran dentro del ámbito de FROM.  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
