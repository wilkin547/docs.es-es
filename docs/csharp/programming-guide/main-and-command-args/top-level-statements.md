---
title: 'Instrucciones de nivel superior: Guía de programación de C#'
description: Obtenga información sobre las instrucciones de nivel superior en C# 9 y versiones posteriores.
ms.date: 03/08/2021
helpviewer_keywords:
- C# language, top-level statements
- C# language, Main method
ms.openlocfilehash: 69ff5fd606f5e12f55bd3e6dfc15fc7e64d8352b
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190450"
---
# <a name="top-level-statements-c-programming-guide"></a><span data-ttu-id="aed83-103">Instrucciones de nivel superior (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="aed83-103">Top-level statements (C# Programming Guide)</span></span>

<span data-ttu-id="aed83-104">A partir de C# 9, no es necesario incluir explícitamente un método `Main` en un proyecto de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="aed83-104">Starting in C# 9, you don't have to explicitly include a `Main` method in a console application project.</span></span> <span data-ttu-id="aed83-105">En su lugar, puede usar la característica de *instrucciones de nivel superior* para minimizar el código que tiene que escribir.</span><span class="sxs-lookup"><span data-stu-id="aed83-105">Instead, you can use the *top-level statements* feature to minimize the code you have to write.</span></span> <span data-ttu-id="aed83-106">En este caso, el compilador genera una clase y un punto de entrada de método `Main` para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aed83-106">In this case, the compiler generates a class and `Main` method entry point for the application.</span></span>

<span data-ttu-id="aed83-107">A continuación se muestra un archivo *Program.cs* que es un programa de C# completo en C# 9:</span><span class="sxs-lookup"><span data-stu-id="aed83-107">Here's a *Program.cs* file that is a complete C# program in C# 9:</span></span>

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

<span data-ttu-id="aed83-108">Las instrucciones de nivel superior permiten escribir programas sencillos para utilidades pequeñas, como Azure Functions y Acciones de GitHub.</span><span class="sxs-lookup"><span data-stu-id="aed83-108">Top-level statements let you write simple programs for small utilities such as Azure Functions and GitHub Actions.</span></span> <span data-ttu-id="aed83-109">También facilitan a los nuevos programadores de C# empezar a aprender y escribir código.</span><span class="sxs-lookup"><span data-stu-id="aed83-109">They also make it simpler for new C# programmers to get started learning and writing code.</span></span>

<span data-ttu-id="aed83-110">En las secciones siguientes se explican las reglas de lo que puede y no puede hacer con las instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-110">The following sections explain the rules on what you can and can't do with top-level statements.</span></span>

## <a name="only-one-top-level-file"></a><span data-ttu-id="aed83-111">Solo un archivo de nivel superior</span><span class="sxs-lookup"><span data-stu-id="aed83-111">Only one top-level file</span></span>

<span data-ttu-id="aed83-112">Una aplicación debe tener solo un punto de entrada, por lo que un proyecto solo puede tener un archivo con instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-112">An application must have only one entry point, so a project can have only one file with top-level statements.</span></span> <span data-ttu-id="aed83-113">Al colocar instrucciones de nivel superior en más de un archivo de un proyecto, se produce el error del compilador siguiente:</span><span class="sxs-lookup"><span data-stu-id="aed83-113">Putting top-level statements in more than one file in a project results in the following compiler error:</span></span>

> <span data-ttu-id="aed83-114">CS8802 Solo una unidad de compilación puede tener instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-114">CS8802 Only one compilation unit can have top-level statements.</span></span>

<span data-ttu-id="aed83-115">Un proyecto puede tener cualquier número de archivos de código fuente adicionales que no tengan instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-115">A project can have any number of additional source code files that don't have top-level statements.</span></span>

## <a name="no-other-entry-points"></a><span data-ttu-id="aed83-116">Ningún otro punto de entrada</span><span class="sxs-lookup"><span data-stu-id="aed83-116">No other entry points</span></span>

<span data-ttu-id="aed83-117">Puede escribir un método `Main` de forma explícita, pero no puede funcionar como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="aed83-117">You can write a `Main` method explicitly, but it can't function as an entry point.</span></span> <span data-ttu-id="aed83-118">El compilador emite la advertencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="aed83-118">The compiler issues the following warning:</span></span>

> <span data-ttu-id="aed83-119">CS7022 El punto de entrada del programa es código global: se ignora el punto de entrada "Main()".</span><span class="sxs-lookup"><span data-stu-id="aed83-119">CS7022 The entry point of the program is global code; ignoring 'Main()' entry point.</span></span>

<span data-ttu-id="aed83-120">En un proyecto con instrucciones de nivel superior, no se puede usar la opción del compilador [-main](../../language-reference/compiler-options/main-compiler-option.md) para seleccionar el punto de entrada, incluso si el proyecto tiene uno o varios métodos `Main`.</span><span class="sxs-lookup"><span data-stu-id="aed83-120">In a project with top-level statements, you can't use the [-main](../../language-reference/compiler-options/main-compiler-option.md) compiler option to select the entry point, even if the project has one or more `Main` methods.</span></span>

## <a name="using-directives"></a><span data-ttu-id="aed83-121">Directivas `using`</span><span class="sxs-lookup"><span data-stu-id="aed83-121">`using` directives</span></span>

<span data-ttu-id="aed83-122">Si incluye directivas using, deben aparecer en primer lugar en el archivo, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aed83-122">If you include using directives, they must come first in the file, as in this example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

## <a name="global-namespace"></a><span data-ttu-id="aed83-123">Espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="aed83-123">Global namespace</span></span>

<span data-ttu-id="aed83-124">Las instrucciones de nivel superior están implícitamente en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="aed83-124">Top-level statements are implicitly in the global namespace.</span></span>

## <a name="namespaces-and-type-definitions"></a><span data-ttu-id="aed83-125">Espacios de nombres y definiciones de tipos</span><span class="sxs-lookup"><span data-stu-id="aed83-125">Namespaces and type definitions</span></span>

<span data-ttu-id="aed83-126">Un archivo con instrucciones de nivel superior también puede contener espacios de nombres y definiciones de tipos, pero deben aparecer después de las instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-126">A file with top-level statements can also contain namespaces and type definitions, but they must come after the top-level statements.</span></span> <span data-ttu-id="aed83-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aed83-127">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-2/Program.cs":::

## `args`

<span data-ttu-id="aed83-128">Las instrucciones de nivel superior pueden hacer referencia a la variable `args` para acceder a los argumentos de línea de comandos que se hayan escrito.</span><span class="sxs-lookup"><span data-stu-id="aed83-128">Top-level statements can reference the `args` variable to access any command-line arguments that were entered.</span></span> <span data-ttu-id="aed83-129">La variable `args` nunca es NULL, pero su valor `Length` es cero si no se han proporcionado argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aed83-129">The `args` variable is never null but its `Length` is zero if no command-line arguments were provided.</span></span> <span data-ttu-id="aed83-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aed83-130">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-3/Program.cs":::

## `await`

<span data-ttu-id="aed83-131">Puede llamar a un método asincrónico mediante el uso `await`.</span><span class="sxs-lookup"><span data-stu-id="aed83-131">You can call an async method by using `await`.</span></span> <span data-ttu-id="aed83-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aed83-132">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-4/Program.cs":::

## <a name="exit-code-for-the-process"></a><span data-ttu-id="aed83-133">Código de salida para el proceso</span><span class="sxs-lookup"><span data-stu-id="aed83-133">Exit code for the process</span></span>

<span data-ttu-id="aed83-134">Para devolver un valor `int` cuando finaliza la aplicación, use la instrucción `return` como lo haría en un método `Main` que devuelva una instancia de `int`.</span><span class="sxs-lookup"><span data-stu-id="aed83-134">To return an `int` value when the application ends, use the `return` statement as you would in a `Main` method that returns an `int`.</span></span> <span data-ttu-id="aed83-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aed83-135">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-5/Program.cs":::

## <a name="implicit-entry-point-method"></a><span data-ttu-id="aed83-136">Método de punto de entrada implícito</span><span class="sxs-lookup"><span data-stu-id="aed83-136">Implicit entry point method</span></span>

<span data-ttu-id="aed83-137">El compilador genera un método que actúa como el punto de entrada del programa para un proyecto con instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="aed83-137">The compiler generates a method to serve as the program entry point for a project with top-level statements.</span></span> <span data-ttu-id="aed83-138">El nombre de este método no es en realidad `Main`, es un detalle de implementación al que el código no puede hacer referencia directamente.</span><span class="sxs-lookup"><span data-stu-id="aed83-138">The name of this method isn't actually `Main`, it's an implementation detail that your code can't reference directly.</span></span> <span data-ttu-id="aed83-139">La signatura del método depende de si las instrucciones de nivel superior contienen la palabra clave `await` o la instrucción `return`.</span><span class="sxs-lookup"><span data-stu-id="aed83-139">The signature of the method depends on whether the top-level statements contain the `await` keyword or the `return` statement.</span></span> <span data-ttu-id="aed83-140">En la tabla siguiente se muestra el aspecto que tendría la signatura del método, utilizando el nombre del método `Main` en la tabla para mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="aed83-140">The following table shows what the method signature would look like, using the method name `Main` in the table for convenience.</span></span>

| <span data-ttu-id="aed83-141">El código de nivel superior contiene</span><span class="sxs-lookup"><span data-stu-id="aed83-141">Top-level code contains</span></span>| <span data-ttu-id="aed83-142">Signatura de `Main` implícita</span><span class="sxs-lookup"><span data-stu-id="aed83-142">Implicit `Main` signature</span></span>                    |
|------------------------|----------------------------------------------|
| <span data-ttu-id="aed83-143">`await` y `return`</span><span class="sxs-lookup"><span data-stu-id="aed83-143">`await` and `return`</span></span>   | `static async Task<int> Main(string[] args)` |
| `await`                | `static async Task Main(string[] args)`      |
| `return`               | `static int Main(string[] args)`             |
| <span data-ttu-id="aed83-144">No `await` ni `return`</span><span class="sxs-lookup"><span data-stu-id="aed83-144">No `await` or `return`</span></span> | `static void Main(string[] args)`            |

## <a name="c-language-specification"></a><span data-ttu-id="aed83-145">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="aed83-145">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
[<span data-ttu-id="aed83-146">Instrucciones de nivel superior</span><span class="sxs-lookup"><span data-stu-id="aed83-146">Top-level statements</span></span>](~/_csharplang/proposals/csharp-9.0/top-level-statements.md)

## <a name="see-also"></a><span data-ttu-id="aed83-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="aed83-147">See also</span></span>

- [<span data-ttu-id="aed83-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="aed83-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="aed83-149">Métodos</span><span class="sxs-lookup"><span data-stu-id="aed83-149">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="aed83-150">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="aed83-150">Inside a C# Program</span></span>](../inside-a-program/index.md)
