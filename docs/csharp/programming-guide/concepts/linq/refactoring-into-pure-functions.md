---
title: Refactorizar en funciones puras (C#)
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: fcb396984d58b5601d278a860b272211e785dcfb
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185563"
---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="4b29c-102">Refactorizar en funciones puras (C#)</span><span class="sxs-lookup"><span data-stu-id="4b29c-102">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="4b29c-103">Un aspecto importante de las transformaciones funcionales puras es aprender cómo refactorizar código usando funciones puras.</span><span class="sxs-lookup"><span data-stu-id="4b29c-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b29c-104">La nomenclatura común en la programación funcional consiste en refactorizar programas usando funciones puras.</span><span class="sxs-lookup"><span data-stu-id="4b29c-104">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="4b29c-105">En Visual Basic y C++, esto se alinea con el uso de funciones en los lenguajes respectivos.</span><span class="sxs-lookup"><span data-stu-id="4b29c-105">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="4b29c-106">No obstante, en C#, las funciones son métodos llamados.</span><span class="sxs-lookup"><span data-stu-id="4b29c-106">However, in C#, functions are called methods.</span></span> <span data-ttu-id="4b29c-107">Con fines de análisis, una función pura se implementa como un método en C#.</span><span class="sxs-lookup"><span data-stu-id="4b29c-107">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="4b29c-108">Tal como se indicó previamente en esta sección, una función pura tiene dos características útiles:</span><span class="sxs-lookup"><span data-stu-id="4b29c-108">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
-   <span data-ttu-id="4b29c-109">No tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="4b29c-109">It has no side effects.</span></span> <span data-ttu-id="4b29c-110">La función no cambia variables o datos de ningún tipo fuera de la función.</span><span class="sxs-lookup"><span data-stu-id="4b29c-110">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
-   <span data-ttu-id="4b29c-111">Es coherente.</span><span class="sxs-lookup"><span data-stu-id="4b29c-111">It is consistent.</span></span> <span data-ttu-id="4b29c-112">Con el mismo conjunto de datos de entrada, siempre devolverá el mismo valor de salida.</span><span class="sxs-lookup"><span data-stu-id="4b29c-112">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="4b29c-113">Una forma de realizar una transición a la programación funcional es refactorizar código existente para eliminar efectos secundarios innecesarios y dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="4b29c-113">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="4b29c-114">De esta forma puede crear versiones de función pura del código existente.</span><span class="sxs-lookup"><span data-stu-id="4b29c-114">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="4b29c-115">En este tema se trata qué es una función pura y qué no es.</span><span class="sxs-lookup"><span data-stu-id="4b29c-115">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="4b29c-116">El tutorial [Tutorial: Manipular contenido en un documento de WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) muestra cómo manipular un documento de WordprocessingML e incluye dos ejemplos de cómo refactorizar usando una función pura.</span><span class="sxs-lookup"><span data-stu-id="4b29c-116">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="4b29c-117">Eliminar efectos secundarios y dependencias externas</span><span class="sxs-lookup"><span data-stu-id="4b29c-117">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="4b29c-118">Los siguientes ejemplos contraponen dos funciones no puras y una función pura.</span><span class="sxs-lookup"><span data-stu-id="4b29c-118">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="4b29c-119">Función no pura que cambia un miembro de clase</span><span class="sxs-lookup"><span data-stu-id="4b29c-119">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="4b29c-120">En el siguiente código, la función `HyphenatedConcat` no es una función pura porque modifica el miembro de datos `aMember` en la clase:</span><span class="sxs-lookup"><span data-stu-id="4b29c-120">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 <span data-ttu-id="4b29c-121">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4b29c-121">This code produces the following output:</span></span>  
  
```  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="4b29c-122">Tenga en cuenta que es irrelevante si los datos que se están modificando tienen acceso a `public` o `private`, o si son un miembro de `static` o un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="4b29c-122">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="4b29c-123">Una función pura no cambia datos fuera de la función.</span><span class="sxs-lookup"><span data-stu-id="4b29c-123">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="4b29c-124">Función no pura que cambia un argumento</span><span class="sxs-lookup"><span data-stu-id="4b29c-124">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="4b29c-125">Asimismo, la siguiente versión de esta misma función no es pura porque modifica el contenido de su parámetro, `sb`.</span><span class="sxs-lookup"><span data-stu-id="4b29c-125">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 <span data-ttu-id="4b29c-126">Esta versión del programa crea el mismo resultado que la primera versión porque la función `HyphenatedConcat` ha cambiado el valor (estado) de su primer parámetro invocando la función de miembro <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b29c-126">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="4b29c-127">Tenga en cuenta que esta modificación se produce a pesar del hecho que `HyphenatedConcat` usar el paso de parámetros llamada por valor.</span><span class="sxs-lookup"><span data-stu-id="4b29c-127">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b29c-128">Para los tipos de referencia, si pasa un parámetro por valor, tiene como resultado una copia de la referencia a un objeto que se está pasando.</span><span class="sxs-lookup"><span data-stu-id="4b29c-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="4b29c-129">Esta copia sigue asociada con los mismos datos de la instancia que la referencia original (hasta que la variable de referencia se asigna a un objeto nuevo).</span><span class="sxs-lookup"><span data-stu-id="4b29c-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="4b29c-130">La llamada por referencia no es necesariamente requerida para que una función modifique un parámetro.</span><span class="sxs-lookup"><span data-stu-id="4b29c-130">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="4b29c-131">Función pura</span><span class="sxs-lookup"><span data-stu-id="4b29c-131">Pure Function</span></span>  
<span data-ttu-id="4b29c-132">La versión siguiente del programa muestra cómo implementar la función `HyphenatedConcat` como una función pura.</span><span class="sxs-lookup"><span data-stu-id="4b29c-132">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 <span data-ttu-id="4b29c-133">De nuevo, esta versión crea la misma línea de salida: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="4b29c-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="4b29c-134">Tenga en cuenta que para conservar un valor concatenado, se almacena en la variable intermedia `s2`.</span><span class="sxs-lookup"><span data-stu-id="4b29c-134">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="4b29c-135">Un enfoque que puede ser muy útil para escribir funciones que son localmente impuras (es decir, declaran y modifican variables locales) pero que son globalmente puras.</span><span class="sxs-lookup"><span data-stu-id="4b29c-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="4b29c-136">Tales funciones tienen muchas características deseables de facilidad de creación, pero evitan algunas de las expresiones de programación funcional más complicadas, como tener que usar una recursión cuando un simple bucle lograría lo mismo.</span><span class="sxs-lookup"><span data-stu-id="4b29c-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="4b29c-137">Operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="4b29c-137">Standard Query Operators</span></span>  
 <span data-ttu-id="4b29c-138">Una característica importante de los operadores de consulta estándar es que se implementan como funciones puras.</span><span class="sxs-lookup"><span data-stu-id="4b29c-138">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="4b29c-139">Para obtener más información, vea [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#)).</span><span class="sxs-lookup"><span data-stu-id="4b29c-139">For more information, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b29c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b29c-140">See Also</span></span>

- [<span data-ttu-id="4b29c-141">Introducción a las transformaciones funcionales puras (C#)</span><span class="sxs-lookup"><span data-stu-id="4b29c-141">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
- [<span data-ttu-id="4b29c-142">Diferencias entre la programación funcional y la programación imperativa (C#)</span><span class="sxs-lookup"><span data-stu-id="4b29c-142">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
