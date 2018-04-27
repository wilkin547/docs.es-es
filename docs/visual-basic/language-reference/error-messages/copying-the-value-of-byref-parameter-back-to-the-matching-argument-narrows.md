---
title: Copiar el valor de &#39;ByRef&#39; parámetro &#39; &lt;parametername&gt; &#39; en el argumento correspondiente se reduce de tipo &#39; &lt;typename1&gt; &#39; al tipo &#39; &lt;nombredetipo2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18c72e56e4b2cc9c2251de2417a9f12a6688323f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="7d141-102">Copiar el valor de &#39;ByRef&#39; parámetro &#39; &lt;parametername&gt; &#39; en el argumento correspondiente se reduce de tipo &#39; &lt;typename1&gt; &#39; al tipo &#39; &lt;nombredetipo2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="7d141-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="7d141-103">Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.</span><span class="sxs-lookup"><span data-stu-id="7d141-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="7d141-104">Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos.</span><span class="sxs-lookup"><span data-stu-id="7d141-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="7d141-105">También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="7d141-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="7d141-106">Cuando utilice su tipo de clase o estructura en una llamada a procedimiento, Visual Basic puede utilizar estos operadores de conversión para convertir al tipo de un argumento al tipo del parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7d141-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="7d141-107">Si se pasa el argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia.</span><span class="sxs-lookup"><span data-stu-id="7d141-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="7d141-108">En este caso, cuando el procedimiento vuelve, Visual Basic debe copiar de nuevo el valor de la variable local en el argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="7d141-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="7d141-109">Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="7d141-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="7d141-110">Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="7d141-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="7d141-111">Si uno de los tipos es su tipo de clase o estructura, Visual Basic debe convertir a y desde el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="7d141-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="7d141-112">Si es una de estas conversiones de ampliación, la conversión inversa podría ser de restricción.</span><span class="sxs-lookup"><span data-stu-id="7d141-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="7d141-113">**Id. de error:** BC32053</span><span class="sxs-lookup"><span data-stu-id="7d141-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d141-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7d141-114">To correct this error</span></span>  
  
-   <span data-ttu-id="7d141-115">Si es posible, utilice un argumento de llamada del mismo tipo como el parámetro de procedimiento, por lo que no es necesario realizar ninguna conversión de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d141-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="7d141-116">Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="7d141-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="7d141-117">Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si es posible.</span><span class="sxs-lookup"><span data-stu-id="7d141-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d141-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d141-118">See Also</span></span>  
 [<span data-ttu-id="7d141-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="7d141-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="7d141-120">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="7d141-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7d141-121">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="7d141-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="7d141-122">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="7d141-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="7d141-123">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7d141-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="7d141-124">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="7d141-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="7d141-125">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="7d141-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="7d141-126">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d141-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="7d141-127">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="7d141-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
