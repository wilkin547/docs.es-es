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
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="0d2a7-103">Resolución de la sobrecarga de funciones (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0d2a7-103">Function Overload Resolution (Entity SQL)</span></span>

<span data-ttu-id="0d2a7-104">En este tema se describe cómo se resuelven las funciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d2a7-104">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="0d2a7-105">Se puede definir más de una función con el mismo nombre, siempre que las funciones tengan firmas únicas.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-105">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="0d2a7-106">Cuando ocurre esto, se deben aplicar los criterios siguientes para determinar qué expresión dada hace referencia a qué funciones.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-106">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="0d2a7-107">Estos criterios se aplican en secuencia.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-107">These criteria are applied in sequence.</span></span> <span data-ttu-id="0d2a7-108">El primer criterio que se aplique únicamente a una sola función indica la función que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-108">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1. <span data-ttu-id="0d2a7-109">**Número de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-109">**Parameter number**.</span></span> <span data-ttu-id="0d2a7-110">La función tiene el mismo número de parámetros que se especifica en la expresión.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-110">The function has the same number of parameters specified in the expression.</span></span>  
  
2. <span data-ttu-id="0d2a7-111">**Coincidencia exacta en el tipo**.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-111">**Exact match on type**.</span></span> <span data-ttu-id="0d2a7-112">Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-112">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3. <span data-ttu-id="0d2a7-113">**Coincidencia en el subtipo**.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-113">**Match on subtype**.</span></span> <span data-ttu-id="0d2a7-114">Cada tipo de argumento de la función coincide exactamente con el tipo de parámetro o es un subtipo del mismo, o bien el argumento es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-114">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="0d2a7-115">En caso de que varias funciones solo difieran en el número de conversiones de subtipo requeridas, la que tenga el menor número de conversiones de subtipo es la que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-115">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4. <span data-ttu-id="0d2a7-116">**Coincide con el subtipo o la promoción de tipos**.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-116">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="0d2a7-117">Cada tipo de argumento de la función coincide exactamente, es un subtipo o se puede promover al tipo de parámetro, o bien el argumento es el literal NULL.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-117">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="0d2a7-118">De nuevo, en caso de que varias funciones solo difieran en el número de conversiones de subtipo y en las promociones, la que tenga el menor número de conversiones de subtipo y promociones es la que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-118">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="0d2a7-119">Si ninguno de estos criterios hace que se seleccione una función única, la expresión de invocación de función es ambigua.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-119">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="0d2a7-120">Incluso si se puede extraer una única función utilizando estas reglas, los argumentos podrían no coincidir aún con los parámetros.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-120">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="0d2a7-121">En ese caso, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-121">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="0d2a7-122">Para las funciones definidas por el usuario, la definición de una función inline de consulta tiene prioridad incluso cuando existe una función definida por el modelo con una firma que es una coincidencia mejor para la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0d2a7-122">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2a7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d2a7-123">See also</span></span>

- [<span data-ttu-id="0d2a7-124">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0d2a7-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="0d2a7-125">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0d2a7-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="0d2a7-126">Funciones</span><span class="sxs-lookup"><span data-stu-id="0d2a7-126">Functions</span></span>](functions-entity-sql.md)
