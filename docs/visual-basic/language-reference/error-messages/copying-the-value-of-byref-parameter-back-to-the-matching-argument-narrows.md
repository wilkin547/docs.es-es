---
description: "Obtener más información acerca de: BC32053: el hecho de volver a copiar el valor del parámetro ' ByRef ' ' <parametername> ' en el argumento coincidente se reduce del tipo ' <typename1> ' al tipo ' <typename2> '"
title: La acción de volver a copiar el valor del parámetro 'ByRef' '<parametername>' en el argumento coincidente restringe del tipo '<typename1>' al tipo '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: 36df6f1c5363a9517c8f3bec4410f5c3d7e38325
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471050"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="df1e9-103">BC32053: al volver a copiar el valor del parámetro ' ByRef ' ' \<parametername> ' en el argumento coincidente, se reduce el tipo ' \<typename1> ' al tipo ' \<typename2> '</span><span class="sxs-lookup"><span data-stu-id="df1e9-103">BC32053: Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>

<span data-ttu-id="df1e9-104">Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.</span><span class="sxs-lookup"><span data-stu-id="df1e9-104">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>

 <span data-ttu-id="df1e9-105">Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos.</span><span class="sxs-lookup"><span data-stu-id="df1e9-105">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="df1e9-106">También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="df1e9-106">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="df1e9-107">Cuando se usa el tipo de clase o estructura en una llamada a procedimiento, Visual Basic puede usar estos operadores de conversión para convertir el tipo de un argumento al tipo de su parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="df1e9-107">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>

 <span data-ttu-id="df1e9-108">Si pasa el argumento [ByRef](../modifiers/byref.md), Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia.</span><span class="sxs-lookup"><span data-stu-id="df1e9-108">If you pass the argument [ByRef](../modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="df1e9-109">En tal caso, cuando el procedimiento vuelve, Visual Basic debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.</span><span class="sxs-lookup"><span data-stu-id="df1e9-109">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>

 <span data-ttu-id="df1e9-110">Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="df1e9-110">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="df1e9-111">Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="df1e9-111">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="df1e9-112">Si uno de los tipos es su tipo de clase o estructura, Visual Basic debe convertir ambos en y desde el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="df1e9-112">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="df1e9-113">Si una de estas conversiones es la ampliación, la conversión inversa podría estar restringida.</span><span class="sxs-lookup"><span data-stu-id="df1e9-113">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>

 <span data-ttu-id="df1e9-114">**Identificador de error:** BC32053</span><span class="sxs-lookup"><span data-stu-id="df1e9-114">**Error ID:** BC32053</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="df1e9-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="df1e9-115">To correct this error</span></span>

- <span data-ttu-id="df1e9-116">Si es posible, use un argumento de llamada del mismo tipo que el parámetro de procedimiento, por lo que Visual Basic no necesita realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="df1e9-116">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>

- <span data-ttu-id="df1e9-117">Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../modifiers/byval.md) en lugar de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="df1e9-117">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>

- <span data-ttu-id="df1e9-118">Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [ampliación](../modifiers/widening.md), si es posible.</span><span class="sxs-lookup"><span data-stu-id="df1e9-118">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../modifiers/widening.md), if possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="df1e9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df1e9-119">See also</span></span>

- [<span data-ttu-id="df1e9-120">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="df1e9-120">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="df1e9-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="df1e9-121">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="df1e9-122">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="df1e9-122">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="df1e9-123">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="df1e9-123">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="df1e9-124">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="df1e9-124">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="df1e9-125">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="df1e9-125">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="df1e9-126">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="df1e9-126">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="df1e9-127">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df1e9-127">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="df1e9-128">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="df1e9-128">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
