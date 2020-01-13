---
title: if-else - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 98c1a8dceec3e5a47627841988e2d722c56fc36c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715264"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="f8545-102">if-else (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f8545-102">if-else (C# Reference)</span></span>

<span data-ttu-id="f8545-103">Una instrucción `if` identifica qué instrucción se debe ejecutar dependiendo del valor de una expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="f8545-103">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="f8545-104">En el ejemplo siguiente, la variable `bool``condition` se establece en `true` y, a continuación, se comprueba en la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="f8545-104">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="f8545-105">El resultado es `The variable is set to true.`</span><span class="sxs-lookup"><span data-stu-id="f8545-105">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="f8545-106">Puede ejecutar los ejemplos de este tema situándolos en el método `Main` de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="f8545-106">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="f8545-107">Una instrucción `if` en C# puede tener dos formas, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8545-107">An `if` statement in C# can take two forms, as the following example shows.</span></span>

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

<span data-ttu-id="f8545-108">En una instrucción `if-else` , si `condition` se evalúa como true, se ejecuta `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="f8545-108">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="f8545-109">Si `condition` es false, se ejecuta `else-statement` .</span><span class="sxs-lookup"><span data-stu-id="f8545-109">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="f8545-110">Puesto que `condition` no puede ser simultáneamente true y false, la `then-statement` y la `else-statement` de una instrucción `if-else` nunca se podrán ejecutar a la vez.</span><span class="sxs-lookup"><span data-stu-id="f8545-110">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="f8545-111">Después de ejecutar la `then-statement` o la `else-statement` , el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="f8545-111">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="f8545-112">En una instrucción `if` que no incluya una instrucción `else` , si `condition` es true, se ejecutará la `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="f8545-112">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="f8545-113">Si `condition` es false, el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="f8545-113">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="f8545-114">Tanto la `then-statement` como la `else-statement` pueden constar de una única instrucción o de varias instrucciones entre llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="f8545-114">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="f8545-115">Para una única instrucción, las llaves son opcionales pero se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="f8545-115">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="f8545-116">La instrucción o las instrucciones en la `then-statement` y la `else-statement` pueden ser de cualquier tipo, incluida otra instrucción `if` anidada dentro de la instrucción `if` .</span><span class="sxs-lookup"><span data-stu-id="f8545-116">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="f8545-117">En instrucciones `if` anidadas, cada cláusula `else` pertenece a la última `if` que no tiene su `else`correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f8545-117">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="f8545-118">En el ejemplo siguiente, `Result1` aparece si `m > 10` y `n > 20` se evalúan como true.</span><span class="sxs-lookup"><span data-stu-id="f8545-118">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="f8545-119">Si `m > 10` es true, pero `n > 20` es false, aparece `Result2` .</span><span class="sxs-lookup"><span data-stu-id="f8545-119">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="f8545-120">En su lugar, si desea que `Result2` aparezca cuando `(m > 10)` es false, puede especificar dicha asociación mediante llaves para establecer el inicio y el fin de la instrucción `if` anidada, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8545-120">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="f8545-121">`Result2` aparece si la condición `(m > 10)` se evalúa como false.</span><span class="sxs-lookup"><span data-stu-id="f8545-121">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="f8545-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8545-122">Example</span></span>

<span data-ttu-id="f8545-123">En el ejemplo siguiente, se escribe un carácter desde el teclado y el programa usa una instrucción `if` anidada para determinar si el carácter de entrada es un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="f8545-123">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="f8545-124">Si el carácter de entrada es un carácter alfabético, el programa comprueba si el carácter de entrada está en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f8545-124">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="f8545-125">Aparece un mensaje para cada caso.</span><span class="sxs-lookup"><span data-stu-id="f8545-125">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="f8545-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8545-126">Example</span></span>

<span data-ttu-id="f8545-127">También puede anidar una instrucción `if` dentro de un bloque else, tal como se muestra en el siguiente código parcial.</span><span class="sxs-lookup"><span data-stu-id="f8545-127">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="f8545-128">El ejemplo anida instrucciones `if` dentro de dos bloques más y, a continuación, un bloque.</span><span class="sxs-lookup"><span data-stu-id="f8545-128">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="f8545-129">Los comentarios de especifican qué condiciones son true o false en cada bloque.</span><span class="sxs-lookup"><span data-stu-id="f8545-129">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="f8545-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8545-130">Example</span></span>

<span data-ttu-id="f8545-131">El ejemplo siguiente determina si un carácter de entrada es una letra minúscula, una letra mayúscula o un número.</span><span class="sxs-lookup"><span data-stu-id="f8545-131">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="f8545-132">Si estas tres condiciones son false, el carácter no es un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="f8545-132">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="f8545-133">En el ejemplo se muestra un mensaje para cada caso.</span><span class="sxs-lookup"><span data-stu-id="f8545-133">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="f8545-134">Puesto que puede ser válida tanto una instrucción del bloque else como del bloque then, puede usar cualquier expresión booleana válida para la condición.</span><span class="sxs-lookup"><span data-stu-id="f8545-134">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="f8545-135">Puede usar [operadores lógicos](../operators/boolean-logical-operators.md) como `!`, `&&`, `||`, `&`, `|` y `^` para hacer condiciones compuestas.</span><span class="sxs-lookup"><span data-stu-id="f8545-135">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="f8545-136">En el código siguiente, se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="f8545-136">The following code shows examples.</span></span>

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

## <a name="c-language-specification"></a><span data-ttu-id="f8545-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f8545-137">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f8545-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8545-138">See also</span></span>

- [<span data-ttu-id="f8545-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f8545-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f8545-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f8545-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f8545-141">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f8545-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f8545-142">?: !</span><span class="sxs-lookup"><span data-stu-id="f8545-142">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="f8545-143">if-else (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="f8545-143">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="f8545-144">switch</span><span class="sxs-lookup"><span data-stu-id="f8545-144">switch</span></span>](switch.md)
