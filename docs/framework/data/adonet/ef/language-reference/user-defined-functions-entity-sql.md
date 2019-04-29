---
title: Funciones definidas por el usuario (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 4922e7fada676a6c26042236ccdb6315d6d455ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879754"
---
# <a name="user-defined-functions-entity-sql"></a>Funciones definidas por el usuario (Entity SQL)
Entity SQL admite llamadas a funciones definidas por el usuario en una consulta. Puede definir estas funciones inline con la consulta (vea [Cómo: Llamar a una función definida por el usuario](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) o como parte del modelo conceptual (vea [Cómo: Definir funciones personalizadas en el modelo Conceptual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Las funciones del modelo conceptual se definen como un comando de Entity SQL en el [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) elemento de un [función](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) elemento en el modelo conceptual.  
  
 Entity SQL le permite definir las funciones en el propio comando de consulta. El [función](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operador define las funciones inline. Puede definir varias funciones con el mismo nombre en un único comando, siempre que sus firmas sean únicas. Para obtener más información, consulta [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vea también

- [Funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
