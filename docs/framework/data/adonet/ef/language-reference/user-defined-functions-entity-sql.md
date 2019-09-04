---
title: Funciones definidas por el usuario (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9ddafb18a10ff2313fd27eab453907054a35218a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248768"
---
# <a name="user-defined-functions-entity-sql"></a>Funciones definidas por el usuario (Entity SQL)
Entity SQL admite llamadas a funciones definidas por el usuario en una consulta. Puede definir estas funciones alineadas con la consulta (vea [cómo: Llamar a una función](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))definida por el usuario) o como parte del modelo conceptual (vea [cómo: Definir funciones personalizadas en el modelo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))conceptual). Las funciones del modelo conceptual se definen como un comando Entity SQL en el elemento [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) de un elemento [function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) en el modelo conceptual.  
  
 Entity SQL le permite definir las funciones en el propio comando de consulta. El operador de [función](function-entity-sql.md) define las funciones insertadas. Puede definir varias funciones con el mismo nombre en un único comando, siempre que sus firmas sean únicas. Para obtener más información, consulta [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones](functions-entity-sql.md)
