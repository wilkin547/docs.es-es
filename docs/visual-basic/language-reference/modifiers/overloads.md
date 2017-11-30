---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a23a6b91681cbd814ac96464e1c340be99a0ecf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="b2f08-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f08-102">Overloads (Visual Basic)</span></span>
<span data-ttu-id="b2f08-103">Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b2f08-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2f08-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2f08-104">Remarks</span></span>  
 <span data-ttu-id="b2f08-105">*Sobrecarga* es la práctica de proporcionar más de una definición para un nombre de propiedad o un procedimiento determinado en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="b2f08-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="b2f08-106">Volver a declarar una propiedad o procedimiento con otra firma se denomina *ocultar mediante signatura*.</span><span class="sxs-lookup"><span data-stu-id="b2f08-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b2f08-107">Reglas</span><span class="sxs-lookup"><span data-stu-id="b2f08-107">Rules</span></span>  
  
-   <span data-ttu-id="b2f08-108">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-108">**Declaration Context.**</span></span> <span data-ttu-id="b2f08-109">Puede usar `Overloads` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="b2f08-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="b2f08-110">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-110">**Combined Modifiers.**</span></span> <span data-ttu-id="b2f08-111">No se puede especificar `Overloads` junto con [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) en la misma declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f08-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>  
  
-   <span data-ttu-id="b2f08-112">**Diferencias requeridas.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-112">**Required Differences.**</span></span> <span data-ttu-id="b2f08-113">El *firma* en esta declaración debe ser diferente de la firma de cada propiedad o procedimiento que sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="b2f08-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="b2f08-114">La firma incluye el nombre de propiedad o procedimiento más lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2f08-114">The signature comprises the property or procedure name together with the following:</span></span>  
  
    -   <span data-ttu-id="b2f08-115">el número de parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f08-115">the number of parameters</span></span>  
  
    -   <span data-ttu-id="b2f08-116">el orden de los parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f08-116">the order of the parameters</span></span>  
  
    -   <span data-ttu-id="b2f08-117">los tipos de datos de los parámetros</span><span class="sxs-lookup"><span data-stu-id="b2f08-117">the data types of the parameters</span></span>  
  
    -   <span data-ttu-id="b2f08-118">el número de parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="b2f08-118">the number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="b2f08-119">el tipo de valor devuelto (solo para un procedimiento de operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="b2f08-119">the return type (only for a conversion operator procedure)</span></span>  
  
     <span data-ttu-id="b2f08-120">Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores.</span><span class="sxs-lookup"><span data-stu-id="b2f08-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="b2f08-121">Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2f08-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>  
  
-   <span data-ttu-id="b2f08-122">**Diferencias no permitidas.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-122">**Disallowed Differences.**</span></span> <span data-ttu-id="b2f08-123">El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:</span><span class="sxs-lookup"><span data-stu-id="b2f08-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>  
  
    -   <span data-ttu-id="b2f08-124">si devuelve o no un valor (para un procedimiento)</span><span class="sxs-lookup"><span data-stu-id="b2f08-124">whether or not it returns a value (for a procedure)</span></span>  
  
    -   <span data-ttu-id="b2f08-125">el tipo de datos del valor devuelto (excepto para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="b2f08-125">the data type of the return value (except for a conversion operator)</span></span>  
  
    -   <span data-ttu-id="b2f08-126">los nombres de los parámetros o parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b2f08-126">the names of the parameters or type parameters</span></span>  
  
    -   <span data-ttu-id="b2f08-127">las restricciones en los parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="b2f08-127">the constraints on the type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="b2f08-128">palabras clave de modificador de parámetro (como `ByRef` o `Optional`)</span><span class="sxs-lookup"><span data-stu-id="b2f08-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>  
  
    -   <span data-ttu-id="b2f08-129">palabras clave de modificador de propiedad o procedimiento (como `Public` o `Shared`)</span><span class="sxs-lookup"><span data-stu-id="b2f08-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>  
  
-   <span data-ttu-id="b2f08-130">**Modificador opcional.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-130">**Optional Modifier.**</span></span> <span data-ttu-id="b2f08-131">No es necesario usar el modificador `Overloads` al definir varias propiedades o procedimientos sobrecargados en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="b2f08-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="b2f08-132">Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.</span><span class="sxs-lookup"><span data-stu-id="b2f08-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>  
  
-   <span data-ttu-id="b2f08-133">**Sombreado y sobrecarga.**</span><span class="sxs-lookup"><span data-stu-id="b2f08-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="b2f08-134">`Overloads`También puede utilizarse para sombrear un miembro existente o un conjunto de miembros sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="b2f08-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="b2f08-135">Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.</span><span class="sxs-lookup"><span data-stu-id="b2f08-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>  
  
 <span data-ttu-id="b2f08-136">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="b2f08-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="b2f08-137">El modificador `Overloads` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2f08-137">The `Overloads` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b2f08-138">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2f08-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="b2f08-139">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2f08-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="b2f08-140">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2f08-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="b2f08-141">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2f08-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2f08-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2f08-142">See Also</span></span>  
 [<span data-ttu-id="b2f08-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="b2f08-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="b2f08-144">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="b2f08-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="b2f08-145">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2f08-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="b2f08-146">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="b2f08-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="b2f08-147">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="b2f08-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
