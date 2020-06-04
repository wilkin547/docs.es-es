---
title: Refactorización en funciones puras
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 415b088661eca347330f4776901d68ee514d8dad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413484"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a><span data-ttu-id="fe802-102">Refactorizar en funciones puras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe802-102">Refactoring Into Pure Functions (Visual Basic)</span></span>

<span data-ttu-id="fe802-103">Un aspecto importante de las transformaciones funcionales puras es aprender cómo refactorizar código usando funciones puras.</span><span class="sxs-lookup"><span data-stu-id="fe802-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>

<span data-ttu-id="fe802-104">Tal como se indicó previamente en esta sección, una función pura tiene dos características útiles:</span><span class="sxs-lookup"><span data-stu-id="fe802-104">As noted previously in this section, a pure function has two useful characteristics:</span></span>

- <span data-ttu-id="fe802-105">No tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe802-105">It has no side effects.</span></span> <span data-ttu-id="fe802-106">La función no cambia variables o datos de ningún tipo fuera de la función.</span><span class="sxs-lookup"><span data-stu-id="fe802-106">The function does not change any variables or the data of any type outside of the function.</span></span>

- <span data-ttu-id="fe802-107">Es coherente.</span><span class="sxs-lookup"><span data-stu-id="fe802-107">It is consistent.</span></span> <span data-ttu-id="fe802-108">Con el mismo conjunto de datos de entrada, siempre devolverá el mismo valor de salida.</span><span class="sxs-lookup"><span data-stu-id="fe802-108">Given the same set of input data, it will always return the same output value.</span></span>

 <span data-ttu-id="fe802-109">Una forma de realizar una transición a la programación funcional es refactorizar código existente para eliminar efectos secundarios innecesarios y dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="fe802-109">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="fe802-110">De esta forma puede crear versiones de función pura del código existente.</span><span class="sxs-lookup"><span data-stu-id="fe802-110">In this way, you can create pure function versions of existing code.</span></span>

<span data-ttu-id="fe802-111">En este tema se trata qué es una función pura y qué no es.</span><span class="sxs-lookup"><span data-stu-id="fe802-111">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="fe802-112">En el tutorial [: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) se muestra cómo manipular un documento WordprocessingML e incluye dos ejemplos de cómo refactorizar usando una función pura.</span><span class="sxs-lookup"><span data-stu-id="fe802-112">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>

## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="fe802-113">Eliminar efectos secundarios y dependencias externas</span><span class="sxs-lookup"><span data-stu-id="fe802-113">Eliminating Side Effects and External Dependencies</span></span>

<span data-ttu-id="fe802-114">Los siguientes ejemplos contraponen dos funciones no puras y una función pura.</span><span class="sxs-lookup"><span data-stu-id="fe802-114">The following examples contrast two non-pure functions and a pure function.</span></span>

### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="fe802-115">Función no pura que cambia un miembro de clase</span><span class="sxs-lookup"><span data-stu-id="fe802-115">Non-Pure Function that Changes a Class Member</span></span>

<span data-ttu-id="fe802-116">En el siguiente código, la función `HyphenatedConcat` no es una función pura porque modifica el miembro de datos `aMember` en la clase:</span><span class="sxs-lookup"><span data-stu-id="fe802-116">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

<span data-ttu-id="fe802-117">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="fe802-117">This code produces the following output:</span></span>

```console
StringOne-StringTwo
```

<span data-ttu-id="fe802-118">Tenga en cuenta que es irrelevante si los datos que se están modificando tienen `public` `private` acceso o son `shared` miembros o un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="fe802-118">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member.</span></span> <span data-ttu-id="fe802-119">Una función pura no cambia datos fuera de la función.</span><span class="sxs-lookup"><span data-stu-id="fe802-119">A pure function does not change any data outside of the function.</span></span>

### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="fe802-120">Función no pura que cambia un argumento</span><span class="sxs-lookup"><span data-stu-id="fe802-120">Non-Pure Function that Changes an Argument</span></span>

<span data-ttu-id="fe802-121">Asimismo, la siguiente versión de esta misma función no es pura porque modifica el contenido de su parámetro, `sb`.</span><span class="sxs-lookup"><span data-stu-id="fe802-121">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

<span data-ttu-id="fe802-122">Esta versión del programa crea el mismo resultado que la primera versión porque la función `HyphenatedConcat` ha cambiado el valor (estado) de su primer parámetro invocando la función de miembro <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="fe802-122">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="fe802-123">Tenga en cuenta que esta modificación se produce a pesar del hecho que `HyphenatedConcat` usar el paso de parámetros llamada por valor.</span><span class="sxs-lookup"><span data-stu-id="fe802-123">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe802-124">Para los tipos de referencia, si pasa un parámetro por valor, tiene como resultado una copia de la referencia a un objeto que se está pasando.</span><span class="sxs-lookup"><span data-stu-id="fe802-124">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="fe802-125">Esta copia sigue asociada con los mismos datos de la instancia que la referencia original (hasta que la variable de referencia se asigna a un objeto nuevo).</span><span class="sxs-lookup"><span data-stu-id="fe802-125">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="fe802-126">La llamada por referencia no es necesariamente requerida para que una función modifique un parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe802-126">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>

### <a name="pure-function"></a><span data-ttu-id="fe802-127">Función pura</span><span class="sxs-lookup"><span data-stu-id="fe802-127">Pure Function</span></span>

<span data-ttu-id="fe802-128">La versión siguiente del programa muestra cómo implementar la función `HyphenatedConcat` como una función pura.</span><span class="sxs-lookup"><span data-stu-id="fe802-128">This next version of the program hows how to implement the `HyphenatedConcat` function as a pure function.</span></span>

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

<span data-ttu-id="fe802-129">De nuevo, esta versión crea la misma línea de salida: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="fe802-129">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="fe802-130">Tenga en cuenta que para conservar un valor concatenado, se almacena en la variable intermedia `s2`.</span><span class="sxs-lookup"><span data-stu-id="fe802-130">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>

<span data-ttu-id="fe802-131">Un enfoque que puede ser muy útil para escribir funciones que son localmente impuras (es decir, declaran y modifican variables locales) pero que son globalmente puras.</span><span class="sxs-lookup"><span data-stu-id="fe802-131">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="fe802-132">Tales funciones tienen muchas características deseables de facilidad de creación, pero evitan algunas de las expresiones de programación funcional más complicadas, como tener que usar una recursión cuando un simple bucle lograría lo mismo.</span><span class="sxs-lookup"><span data-stu-id="fe802-132">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>

## <a name="standard-query-operators"></a><span data-ttu-id="fe802-133">Operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="fe802-133">Standard Query Operators</span></span>

<span data-ttu-id="fe802-134">Una característica importante de los operadores de consulta estándar es que se implementan como funciones puras.</span><span class="sxs-lookup"><span data-stu-id="fe802-134">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>

<span data-ttu-id="fe802-135">Para obtener más información, vea [información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe802-135">For more information, see [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe802-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe802-136">See also</span></span>

- [<span data-ttu-id="fe802-137">Introducción a las transformaciones funcionales puras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe802-137">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="fe802-138">Programación funcional frente a programación imperativa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe802-138">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](functional-programming-vs-imperative-programming.md)
