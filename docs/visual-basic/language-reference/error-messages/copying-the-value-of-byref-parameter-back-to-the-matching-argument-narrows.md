---
title: La acción de volver a copiar el valor del parámetro 'ByRef' '<parametername>' en el argumento coincidente restringe del tipo '<typename1>' al tipo '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: bac5f9a88df719bc64a8b0541f65e5912275866e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409756"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="93233-102">La acción de volver a copiar el valor del parámetro 'ByRef' '\<parametername>' en el argumento coincidente restringe del tipo '\<typename1>' al tipo '\<typename2>'</span><span class="sxs-lookup"><span data-stu-id="93233-102">Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>
<span data-ttu-id="93233-103">Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.</span><span class="sxs-lookup"><span data-stu-id="93233-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="93233-104">Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos.</span><span class="sxs-lookup"><span data-stu-id="93233-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="93233-105">También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="93233-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="93233-106">Cuando se usa el tipo de clase o estructura en una llamada a procedimiento, Visual Basic puede usar estos operadores de conversión para convertir el tipo de un argumento al tipo de su parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="93233-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="93233-107">Si pasa el argumento [ByRef](../modifiers/byref.md), Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia.</span><span class="sxs-lookup"><span data-stu-id="93233-107">If you pass the argument [ByRef](../modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="93233-108">En tal caso, cuando el procedimiento vuelve, Visual Basic debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.</span><span class="sxs-lookup"><span data-stu-id="93233-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="93233-109">Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="93233-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="93233-110">Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="93233-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="93233-111">Si uno de los tipos es su tipo de clase o estructura, Visual Basic debe convertir ambos en y desde el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="93233-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="93233-112">Si una de estas conversiones es la ampliación, la conversión inversa podría estar restringida.</span><span class="sxs-lookup"><span data-stu-id="93233-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="93233-113">**Identificador de error:** BC32053</span><span class="sxs-lookup"><span data-stu-id="93233-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93233-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93233-114">To correct this error</span></span>  
  
- <span data-ttu-id="93233-115">Si es posible, use un argumento de llamada del mismo tipo que el parámetro de procedimiento, por lo que Visual Basic no necesita realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="93233-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="93233-116">Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../modifiers/byval.md) en lugar de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="93233-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>  
  
- <span data-ttu-id="93233-117">Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [ampliación](../modifiers/widening.md), si es posible.</span><span class="sxs-lookup"><span data-stu-id="93233-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93233-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93233-118">See also</span></span>

- [<span data-ttu-id="93233-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="93233-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="93233-120">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="93233-120">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="93233-121">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="93233-121">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="93233-122">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="93233-122">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="93233-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="93233-123">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="93233-124">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="93233-124">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="93233-125">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="93233-125">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="93233-126">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93233-126">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="93233-127">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="93233-127">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
