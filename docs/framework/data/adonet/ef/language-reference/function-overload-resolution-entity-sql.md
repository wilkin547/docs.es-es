---
title: Resolución de la sobrecarga de funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: d37cd9342d1fb3b60d5a2c05d373fb7e71f54b1f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189401"
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="58461-102">Resolución de la sobrecarga de funciones (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="58461-102">Function Overload Resolution (Entity SQL)</span></span>

<span data-ttu-id="58461-103">En este tema se describe cómo se resuelven las funciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58461-103">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="58461-104">Se puede definir más de una función con el mismo nombre, siempre que las funciones tengan firmas únicas.</span><span class="sxs-lookup"><span data-stu-id="58461-104">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="58461-105">Cuando ocurre esto, se deben aplicar los criterios siguientes para determinar qué expresión dada hace referencia a qué funciones.</span><span class="sxs-lookup"><span data-stu-id="58461-105">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="58461-106">Estos criterios se aplican en secuencia.</span><span class="sxs-lookup"><span data-stu-id="58461-106">These criteria are applied in sequence.</span></span> <span data-ttu-id="58461-107">El primer criterio que se aplique únicamente a una sola función indica la función que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="58461-107">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1. <span data-ttu-id="58461-108">**Número de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="58461-108">**Parameter number**.</span></span> <span data-ttu-id="58461-109">La función tiene el mismo número de parámetros que se especifica en la expresión.</span><span class="sxs-lookup"><span data-stu-id="58461-109">The function has the same number of parameters specified in the expression.</span></span>  
  
2. <span data-ttu-id="58461-110">**Coincidencia exacta en el tipo**.</span><span class="sxs-lookup"><span data-stu-id="58461-110">**Exact match on type**.</span></span> <span data-ttu-id="58461-111">Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="58461-111">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3. <span data-ttu-id="58461-112">**Coincidencia en el subtipo**.</span><span class="sxs-lookup"><span data-stu-id="58461-112">**Match on subtype**.</span></span> <span data-ttu-id="58461-113">Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es un subtipo del mismo, o bien el argumento es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="58461-113">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="58461-114">En caso de que varias funciones solo difieran en el número de conversiones de subtipo requeridas, la que tenga el menor número de conversiones de subtipo es la que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="58461-114">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4. <span data-ttu-id="58461-115">**Coincide con el subtipo o la promoción de tipos**.</span><span class="sxs-lookup"><span data-stu-id="58461-115">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="58461-116">Cada tipo de argumento de la función coincide exactamente, es un subtipo o se puede promover al tipo de parámetro, o bien el argumento es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="58461-116">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="58461-117">De nuevo, en caso de que varias funciones solo difieran en el número de conversiones de subtipo y en las promociones, la que tenga el menor número de conversiones de subtipo y promociones es la que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="58461-117">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="58461-118">Si ninguno de estos criterios hace que se seleccione una función única, la expresión de invocación de función es ambigua.</span><span class="sxs-lookup"><span data-stu-id="58461-118">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="58461-119">Incluso si se puede extraer una única función utilizando estas reglas, los argumentos podrían no coincidir aún con los parámetros.</span><span class="sxs-lookup"><span data-stu-id="58461-119">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="58461-120">En ese caso, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="58461-120">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="58461-121">Para las funciones definidas por el usuario, la definición de una función inline de consulta tiene prioridad incluso cuando existe una función definida por el modelo con una firma que es una coincidencia mejor para la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="58461-121">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58461-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58461-122">See also</span></span>

- [<span data-ttu-id="58461-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="58461-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="58461-124">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="58461-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="58461-125">Funciones</span><span class="sxs-lookup"><span data-stu-id="58461-125">Functions</span></span>](functions-entity-sql.md)
