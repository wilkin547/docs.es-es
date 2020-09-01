---
description: using (Directiva, Referencia de C# Reference)
title: using (Directiva, Referencia de C# Reference)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: f22a67348b19b8c97513ca685b2b10b34b1fd6fd
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141951"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="05921-103">using (Directiva, Referencia de C# Reference)</span><span class="sxs-lookup"><span data-stu-id="05921-103">using directive (C# Reference)</span></span>

<span data-ttu-id="05921-104">La directiva `using` tiene tres usos:</span><span class="sxs-lookup"><span data-stu-id="05921-104">The `using` directive has three uses:</span></span>

- <span data-ttu-id="05921-105">Permitir el uso de tipos en un espacio de nombres de manera que no tenga que calificar el uso de un tipo en dicho espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="05921-105">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>

    ```csharp
    using System.Text;
    ```

- <span data-ttu-id="05921-106">Permitirle acceder a los miembros estáticos y a los tipos anidados de un tipo sin tener que calificar el acceso con el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="05921-106">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span>

    ```csharp
    using static System.Math;
    ```

    <span data-ttu-id="05921-107">Para obtener más información, vea [using static (Directiva)](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="05921-107">For more information, see the [using static directive](using-static.md).</span></span>

- <span data-ttu-id="05921-108">Para crear un alias para un espacio de nombre o un tipo.</span><span class="sxs-lookup"><span data-stu-id="05921-108">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="05921-109">Esto se conoce como *alias using (Directiva)*.</span><span class="sxs-lookup"><span data-stu-id="05921-109">This is called a *using alias directive*.</span></span>

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

<span data-ttu-id="05921-110">La palabra clave `using` también se usa para crear *instrucciones using*, que ayudan a garantizar que los objetos <xref:System.IDisposable>, como archivos y fuentes, se tratan correctamente.</span><span class="sxs-lookup"><span data-stu-id="05921-110">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="05921-111">Consulte [using (Instrucción)](using-statement.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="05921-111">See [using Statement](using-statement.md) for more information.</span></span>

## <a name="using-static-type"></a><span data-ttu-id="05921-112">Uso de tipos estáticos</span><span class="sxs-lookup"><span data-stu-id="05921-112">Using static type</span></span>

<span data-ttu-id="05921-113">Puede acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:</span><span class="sxs-lookup"><span data-stu-id="05921-113">You can access static members of a type without having to qualify the access with the type name:</span></span>

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a><span data-ttu-id="05921-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05921-114">Remarks</span></span>

<span data-ttu-id="05921-115">El ámbito de una directiva `using` se limita al archivo en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="05921-115">The scope of a `using` directive is limited to the file in which it appears.</span></span>

<span data-ttu-id="05921-116">La directiva `using` puede aparecer:</span><span class="sxs-lookup"><span data-stu-id="05921-116">The `using` directive can appear:</span></span>

- <span data-ttu-id="05921-117">Al principio de un archivo de código fuente, antes de las definiciones de espacio de nombres o tipo.</span><span class="sxs-lookup"><span data-stu-id="05921-117">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="05921-118">En cualquier espacio de nombres, pero antes de cualquier espacio de nombres o tipos declarados en este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="05921-118">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="05921-119">De lo contrario, se generará el error de compilador [CS1529](../../misc/cs1529.md).</span><span class="sxs-lookup"><span data-stu-id="05921-119">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>

<span data-ttu-id="05921-120">Cree una directiva de alias `using` para facilitar la calificación de un identificador como espacio de nombres o tipo.</span><span class="sxs-lookup"><span data-stu-id="05921-120">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="05921-121">En cualquier directiva `using`, hay que usar el espacio de nombres o el tipo con cualificación completa, independientemente de las directivas `using` que los precedan.</span><span class="sxs-lookup"><span data-stu-id="05921-121">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="05921-122">No se puede usar ningún alias `using` en la declaración de una directiva `using`.</span><span class="sxs-lookup"><span data-stu-id="05921-122">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="05921-123">Por ejemplo, el código siguiente genera un error de compilador:</span><span class="sxs-lookup"><span data-stu-id="05921-123">For example, the following generates a compiler error:</span></span>

```csharp
using s = System.Text;
using s.RegularExpressions; // Generates a compiler error.
```

<span data-ttu-id="05921-124">Cree una directiva `using` para usar los tipos de un espacio de nombres sin tener que especificarlo.</span><span class="sxs-lookup"><span data-stu-id="05921-124">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="05921-125">Una directiva `using` no proporciona acceso a los espacios de nombres que están anidados en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="05921-125">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>

<span data-ttu-id="05921-126">Los espacios de nombres se dividen en dos categorías: definidos por el sistema y definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="05921-126">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="05921-127">Los espacios de nombres definidos por el usuario son espacios de nombres definidos en el código.</span><span class="sxs-lookup"><span data-stu-id="05921-127">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="05921-128">Para obtener una lista de los espacios de nombres definidos por el sistema, vea [Explorador de API de .NET](../../../../api/index.md).</span><span class="sxs-lookup"><span data-stu-id="05921-128">For a list of the system-defined namespaces, see [.NET API Browser](../../../../api/index.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="05921-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="05921-129">Example 1</span></span>

<span data-ttu-id="05921-130">En el ejemplo siguiente se muestra cómo definir y usar un alias `using` para un espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="05921-130">The following example shows how to define and use a `using` alias for a namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

<span data-ttu-id="05921-131">Una directiva de alias using no puede tener un tipo genérico abierto en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="05921-131">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="05921-132">Por ejemplo, no puede crear un alias using para un elemento `List<T>`, pero puede crear uno para un elemento `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="05921-132">For example, you cannot create a using alias for a `List<T>`, but you can create one for a `List<int>`.</span></span>

## <a name="example-2"></a><span data-ttu-id="05921-133">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="05921-133">Example 2</span></span>

<span data-ttu-id="05921-134">En el ejemplo siguiente se muestra cómo definir una directiva `using` y un alias `using` para una clase:</span><span class="sxs-lookup"><span data-stu-id="05921-134">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="05921-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="05921-135">C# language specification</span></span>

<span data-ttu-id="05921-136">Para obtener más información, vea la sección [Directivas using](~/_csharplang/spec/namespaces.md#using-directives) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="05921-136">For more information, see [Using directives](~/_csharplang/spec/namespaces.md#using-directives) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="05921-137">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="05921-137">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="05921-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="05921-138">See also</span></span>

- [<span data-ttu-id="05921-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="05921-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="05921-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="05921-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="05921-141">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="05921-141">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="05921-142">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="05921-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="05921-143">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="05921-143">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
- [<span data-ttu-id="05921-144">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="05921-144">using Statement</span></span>](using-statement.md)
