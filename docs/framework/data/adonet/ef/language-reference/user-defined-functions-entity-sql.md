---
description: 'Más información acerca de: funciones de User-Defined (Entity SQL)'
title: Funciones definidas por el usuario (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: b5ebff087da08530e13f301e58509ba2d90c3605
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673211"
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="06931-103">Funciones definidas por el usuario (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="06931-103">User-Defined Functions (Entity SQL)</span></span>

<span data-ttu-id="06931-104">Entity SQL admite llamadas a funciones definidas por el usuario en una consulta.</span><span class="sxs-lookup"><span data-stu-id="06931-104">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="06931-105">Puede definir estas funciones alineadas con la consulta (vea [Cómo: llamar a una función User-Defined](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) o como parte del modelo conceptual (vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="06931-105">You can define these functions inline with the query (see [How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span></span> <span data-ttu-id="06931-106">Las funciones del modelo conceptual se definen como un comando Entity SQL en el elemento [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) de un elemento [function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="06931-106">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) element of a [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="06931-107">Entity SQL le permite definir las funciones en el propio comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="06931-107">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="06931-108">El operador de [función](function-entity-sql.md) define las funciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="06931-108">The [FUNCTION](function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="06931-109">Puede definir varias funciones con el mismo nombre en un único comando, siempre que sus firmas sean únicas.</span><span class="sxs-lookup"><span data-stu-id="06931-109">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="06931-110">Para obtener más información, consulta [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="06931-110">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06931-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="06931-111">See also</span></span>

- [<span data-ttu-id="06931-112">Funciones</span><span class="sxs-lookup"><span data-stu-id="06931-112">Functions</span></span>](functions-entity-sql.md)
