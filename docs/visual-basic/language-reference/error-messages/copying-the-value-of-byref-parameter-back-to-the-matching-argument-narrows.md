---
title: "Copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; nuevo en el argumento correspondiente se restringe de tipo &#39;&lt; NombreTipo1&gt;&#39; escriba &#39;&lt; nombredetipo2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords: BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="5af40-102">Copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; nuevo en el argumento correspondiente se restringe de tipo &#39;&lt; NombreTipo1&gt;&#39; escriba &#39;&lt; nombredetipo2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="5af40-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="5af40-103">Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.</span><span class="sxs-lookup"><span data-stu-id="5af40-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="5af40-104">Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos.</span><span class="sxs-lookup"><span data-stu-id="5af40-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="5af40-105">También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="5af40-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="5af40-106">Cuando use su tipo de clase o estructura en una llamada de procedimiento, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] puede usar estos operadores de conversión para convertir el tipo de un argumento al tipo del parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5af40-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="5af40-107">Si se pasa el argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia.</span><span class="sxs-lookup"><span data-stu-id="5af40-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="5af40-108">En tal caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe copiar el valor de la variable local de nuevo en el argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="5af40-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="5af40-109">Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="5af40-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="5af40-110">Pero si los tipos son diferentes, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se debe convertir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="5af40-110">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="5af40-111">Si uno de los tipos es su tipo de clase o estructura, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] lo debe convertir a y desde el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="5af40-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="5af40-112">Si es una de estas conversiones de ampliación, la conversión inversa podría ser de restricción.</span><span class="sxs-lookup"><span data-stu-id="5af40-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="5af40-113">**Id. de error:** BC32053</span><span class="sxs-lookup"><span data-stu-id="5af40-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5af40-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5af40-114">To correct this error</span></span>  
  
-   <span data-ttu-id="5af40-115">Si es posible, use un argumento de llamada del mismo tipo, como el parámetro de procedimiento, por lo que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no necesita hacer ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="5af40-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="5af40-116">Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="5af40-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="5af40-117">Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si es posible.</span><span class="sxs-lookup"><span data-stu-id="5af40-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af40-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5af40-118">See Also</span></span>  
 [<span data-ttu-id="5af40-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="5af40-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="5af40-120">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="5af40-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="5af40-121">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="5af40-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="5af40-122">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="5af40-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="5af40-123">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5af40-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="5af40-124">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="5af40-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="5af40-125">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="5af40-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="5af40-126">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5af40-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="5af40-127">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="5af40-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
