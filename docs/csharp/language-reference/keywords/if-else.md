---
title: if-else (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
dev_langs:
- CSharp
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 694761a9b03fadf2dff97e61e37c0af52658f9e4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="if-else-c-reference"></a><span data-ttu-id="93da7-102">if-else (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="93da7-102">if-else (C# Reference)</span></span>
<span data-ttu-id="93da7-103">Una instrucción `if` identifica qué instrucción se debe ejecutar dependiendo del valor de una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="93da7-103">An `if` statement identifies which statement to run based on the value of a `Boolean` expression.</span></span> <span data-ttu-id="93da7-104">En el ejemplo siguiente, la variable `Boolean` `result` se establece en `true` y, a continuación, se comprueba en la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="93da7-104">In the following example, the `Boolean` variable `result` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="93da7-105">El resultado es `The condition is true`</span><span class="sxs-lookup"><span data-stu-id="93da7-105">The output is `The condition is true`.</span></span>  
  
 <span data-ttu-id="93da7-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span></span>  
  
 <span data-ttu-id="93da7-107">Puede ejecutar los ejemplos de este tema situándolos en el método `Main` de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="93da7-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>  
  
 <span data-ttu-id="93da7-108">Una instrucción `if` en C# puede tener dos formas, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="93da7-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>  
  
```csharp  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 <span data-ttu-id="93da7-109">En una instrucción `if-else` , si `condition` se evalúa como true, se ejecuta `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="93da7-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="93da7-110">Si `condition` es false, se ejecuta `else-statement` .</span><span class="sxs-lookup"><span data-stu-id="93da7-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="93da7-111">Puesto que `condition` no puede ser simultáneamente true y false, la `then-statement` y la `else-statement` de una instrucción `if-else` nunca se podrán ejecutar a la vez.</span><span class="sxs-lookup"><span data-stu-id="93da7-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="93da7-112">Después de ejecutar la `then-statement` o la `else-statement` , el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="93da7-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="93da7-113">En una instrucción `if` que no incluya una instrucción `else` , si `condition` es true, se ejecutará la `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="93da7-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="93da7-114">Si `condition` es false, el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="93da7-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="93da7-115">Tanto la `then-statement` como la `else-statement` pueden constar de una única instrucción o de varias instrucciones entre llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="93da7-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="93da7-116">Para una única instrucción, las llaves son opcionales pero se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="93da7-116">For a single statement, the braces are optional but recommended.</span></span>  
  
 <span data-ttu-id="93da7-117">La instrucción o las instrucciones en la `then-statement` y la `else-statement` pueden ser de cualquier tipo, incluida otra instrucción `if` anidada dentro de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="93da7-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="93da7-118">En instrucciones `if` anidadas, cada cláusula `else` pertenece a la última `if` que no tiene su `else`correspondiente.</span><span class="sxs-lookup"><span data-stu-id="93da7-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="93da7-119">En el ejemplo siguiente, `Result1` aparece si `m > 10` y `n > 20` se evalúan como true.</span><span class="sxs-lookup"><span data-stu-id="93da7-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="93da7-120">Si `m > 10` es true, pero `n > 20` es false, aparece `Result2` .</span><span class="sxs-lookup"><span data-stu-id="93da7-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>  
  
 <span data-ttu-id="93da7-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span></span>  
  
 <span data-ttu-id="93da7-122">En su lugar, si desea que `Result2` aparezca cuando `(m > 10)` es false, puede especificar dicha asociación mediante llaves para establecer el inicio y el fin de la instrucción `if` anidada, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="93da7-122">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>  
  
 <span data-ttu-id="93da7-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span></span>  
  
 <span data-ttu-id="93da7-124">`Result2` aparece si la condición `(m > 10)` se evalúa como false.</span><span class="sxs-lookup"><span data-stu-id="93da7-124">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93da7-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93da7-125">Example</span></span>  
 <span data-ttu-id="93da7-126">En el ejemplo siguiente, se escribe un carácter desde el teclado y el programa usa una instrucción `if` anidada para determinar si el carácter de entrada es un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="93da7-126">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="93da7-127">Si el carácter de entrada es un carácter alfabético, el programa comprueba si el carácter de entrada está en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="93da7-127">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="93da7-128">Aparece un mensaje para cada caso.</span><span class="sxs-lookup"><span data-stu-id="93da7-128">A message appears for each case.</span></span>  
  
 <span data-ttu-id="93da7-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="93da7-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93da7-130">Example</span></span>  
 <span data-ttu-id="93da7-131">También puede anidar una instrucción `if` dentro de un bloque else, tal como se muestra en el siguiente código parcial.</span><span class="sxs-lookup"><span data-stu-id="93da7-131">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="93da7-132">El ejemplo anida instrucciones `if` dentro de dos bloques más y, a continuación, un bloque.</span><span class="sxs-lookup"><span data-stu-id="93da7-132">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="93da7-133">Los comentarios de especifican qué condiciones son true o false en cada bloque.</span><span class="sxs-lookup"><span data-stu-id="93da7-133">The comments specify which conditions are true or false in each block.</span></span>  
  
 <span data-ttu-id="93da7-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="93da7-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93da7-135">Example</span></span>  
 <span data-ttu-id="93da7-136">El ejemplo siguiente determina si un carácter de entrada es una letra minúscula, una letra mayúscula o un número.</span><span class="sxs-lookup"><span data-stu-id="93da7-136">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="93da7-137">Si estas tres condiciones son false, el carácter no es un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="93da7-137">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="93da7-138">En el ejemplo se muestra un mensaje para cada caso.</span><span class="sxs-lookup"><span data-stu-id="93da7-138">The example displays a message for each case.</span></span>  
  
 <span data-ttu-id="93da7-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="93da7-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span></span>  
  
 <span data-ttu-id="93da7-140">Puesto que puede ser válida tanto una instrucción del bloque else como del bloque then, puede usar cualquier expresión booleana válida para la condición.</span><span class="sxs-lookup"><span data-stu-id="93da7-140">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="93da7-141">Puede usar operadores lógicos tales como [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) y [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="93da7-141">You can use logical operators such as [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="93da7-142">para hacer condiciones compuestas.</span><span class="sxs-lookup"><span data-stu-id="93da7-142">to make compound conditions.</span></span> <span data-ttu-id="93da7-143">En el código siguiente, se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="93da7-143">The following code shows examples.</span></span>  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="93da7-144">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="93da7-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93da7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="93da7-145">See Also</span></span>  
 <span data-ttu-id="93da7-146">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="93da7-146">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="93da7-147">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="93da7-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="93da7-148">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="93da7-148">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="93da7-149">[Operador ?:](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="93da7-149">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 <span data-ttu-id="93da7-150">[if-else (Instrucción) (C++)](/cpp/cpp/if-else-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="93da7-150">[if-else Statement (C++)](/cpp/cpp/if-else-statement-cpp) </span></span>  
 [<span data-ttu-id="93da7-151">switch</span><span class="sxs-lookup"><span data-stu-id="93da7-151">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)

