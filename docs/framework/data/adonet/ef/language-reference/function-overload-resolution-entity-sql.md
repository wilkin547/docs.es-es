---
description: 'Más información sobre: resolución de sobrecargas de función (Entity SQL)'
title: Resolución de la sobrecarga de funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: 8fbe0b54ed559d1f962c3e916d25554e0de65737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786334"
---
# <a name="function-overload-resolution-entity-sql"></a>Resolución de la sobrecarga de funciones (Entity SQL)

En este tema se describe cómo se resuelven las funciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 Se puede definir más de una función con el mismo nombre, siempre que las funciones tengan firmas únicas.  
  
 Cuando ocurre esto, se deben aplicar los criterios siguientes para determinar qué expresión dada hace referencia a qué funciones. Estos criterios se aplican en secuencia. El primer criterio que se aplique únicamente a una sola función indica la función que se resuelve.  
  
1. **Número de parámetro**. La función tiene el mismo número de parámetros que se especifica en la expresión.  
  
2. **Coincidencia exacta en el tipo**. Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es el literal NULL.  
  
3. **Coincidencia en el subtipo**. Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es un subtipo del mismo, o bien el argumento es el literal NULL. En caso de que varias funciones solo difieran en el número de conversiones de subtipo requeridas, la que tenga el menor número de conversiones de subtipo es la que se resuelve.  
  
4. **Coincide con el subtipo o la promoción de tipos**. Cada tipo de argumento de la función coincide exactamente, es un subtipo o se puede promover al tipo de parámetro, o bien el argumento es el literal NULL. De nuevo, en caso de que varias funciones solo difieran en el número de conversiones de subtipo y en las promociones, la que tenga el menor número de conversiones de subtipo y promociones es la que se resuelve.  
  
 Si ninguno de estos criterios hace que se seleccione una función única, la expresión de invocación de función es ambigua.  
  
 Incluso si se puede extraer una única función utilizando estas reglas, los argumentos podrían no coincidir aún con los parámetros. En ese caso, se genera un error.  
  
 Para las funciones definidas por el usuario, la definición de una función inline de consulta tiene prioridad incluso cuando existe una función definida por el modelo con una firma que es una coincidencia mejor para la función definida por el usuario.  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Funciones](functions-entity-sql.md)
