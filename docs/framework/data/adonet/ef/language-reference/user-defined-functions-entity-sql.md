---
title: Funciones definidas por el usuario (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 03146d895c6ca780692228937fafcf25b24902aa
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507250"
---
# <a name="user-defined-functions-entity-sql"></a>Funciones definidas por el usuario (Entity SQL)
Entity SQL admite llamadas a funciones definidas por el usuario en una consulta. Puede definir estas funciones inline con la consulta (vea [Cómo: llamar a una función definida por el usuario](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) o como parte del modelo conceptual (vea [Cómo: definir funciones personalizadas en el modelo Conceptual](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Las funciones del modelo conceptual se definen como un comando de Entity SQL en el [DefiningExpression](https://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) elemento de un [función](https://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) elemento en el modelo conceptual.  
  
 Entity SQL le permite definir las funciones en el propio comando de consulta. El [función](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operador define las funciones inline. Puede definir varias funciones con el mismo nombre en un único comando, siempre que sus firmas sean únicas. Para obtener más información, consulta [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vea también  
 [Funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
