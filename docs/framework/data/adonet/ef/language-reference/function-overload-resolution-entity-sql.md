---
title: "Resolución de la sobrecarga de funciones (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3a303ca917a9f6cfee42d11456a1f80b52ffd2ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="function-overload-resolution-entity-sql"></a>Resolución de la sobrecarga de funciones (Entity SQL)
En este tema se describe cómo se resuelven las funciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 Se puede definir más de una función con el mismo nombre, siempre que las funciones tengan firmas únicas.  
  
 Cuando ocurre esto, se deben aplicar los criterios siguientes para determinar qué expresión dada hace referencia a qué funciones. Estos criterios se aplican en secuencia. El primer criterio que se aplique únicamente a una sola función indica la función que se resuelve.  
  
1.  **Número de parámetro**. La función tiene el mismo número de parámetros que se especifica en la expresión.  
  
2.  **Coincidencia exacta de tipo**. Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es el literal NULL.  
  
3.  **Coincidir en el subtipo**. Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es un subtipo del mismo, o bien el argumento es el literal NULL. En caso de que varias funciones solo difieran en el número de conversiones de subtipo requeridas, la que tenga el menor número de conversiones de subtipo es la que se resuelve.  
  
4.  **Búsqueda de coincidencias en la promoción de tipos o subtipos**. Cada tipo de argumento de la función coincide exactamente, es un subtipo o se puede promover al tipo de parámetro, o bien el argumento es el literal NULL. De nuevo, en caso de que varias funciones solo difieran en el número de conversiones de subtipo y en las promociones, la que tenga el menor número de conversiones de subtipo y promociones es la que se resuelve.  
  
 Si ninguno de estos criterios hace que se seleccione una función única, la expresión de invocación de función es ambigua.  
  
 Incluso si se puede extraer una única función utilizando estas reglas, los argumentos podrían no coincidir aún con los parámetros. En ese caso, se genera un error.  
  
 Para las funciones definidas por el usuario, la definición de una función inline de consulta tiene prioridad incluso cuando existe una función definida por el modelo con una firma que es una coincidencia mejor para la función definida por el usuario.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
