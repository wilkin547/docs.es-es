---
title: 'Main() y argumentos de la línea de comandos: Guía de programación de C#'
description: Obtenga información sobre Main() y los argumentos de línea de comandos. El método "Main" es el punto de entrada de un programa ejecutable.
ms.date: 03/08/2021
f1_keywords:
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 05b2030133ca83cf87de7110f820eaad38fad756
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480184"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="88c67-104">Main() y argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88c67-104">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="88c67-105">El método `Main` es el punto de entrada de una aplicación de C#</span><span class="sxs-lookup"><span data-stu-id="88c67-105">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="88c67-106">(las bibliotecas y los servicios no requieren un método `Main` como punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.</span><span class="sxs-lookup"><span data-stu-id="88c67-106">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

<span data-ttu-id="88c67-107">Solo puede haber un punto de entrada en un programa de C#.</span><span class="sxs-lookup"><span data-stu-id="88c67-107">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="88c67-108">Si hay más de una clase que tenga un método `Main`, deberá compilar el programa con la opción del compilador **StartupObject** para especificar qué método `Main` quiere utilizar como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="88c67-108">If you have more than one class that has a `Main` method, you must compile your program with the **StartupObject** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="88c67-109">Para obtener más información, consulte [**StartupObject** (opciones del compilador de C#)](../../language-reference/compiler-options/advanced.md#mainentrypoint-or-startupobject).</span><span class="sxs-lookup"><span data-stu-id="88c67-109">For more information, see [**StartupObject** (C# Compiler Options)](../../language-reference/compiler-options/advanced.md#mainentrypoint-or-startupobject).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

<span data-ttu-id="88c67-110">A partir de C# 9, puede omitir el método `Main` y escribir instrucciones de C# como si estuvieran en el método `Main`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88c67-110">Starting in C# 9, you can omit the `Main` method, and write C# statements as if they were in the `Main` method, as in the following example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

<span data-ttu-id="88c67-111">Para obtener información sobre cómo escribir código de aplicación con un método de punto de entrada implícito, consulte las [instrucciones de nivel superior](top-level-statements.md).</span><span class="sxs-lookup"><span data-stu-id="88c67-111">For information about how to write application code with an implicit entry point method, see [Top-level statements](top-level-statements.md).</span></span>

## <a name="overview"></a><span data-ttu-id="88c67-112">Información general</span><span class="sxs-lookup"><span data-stu-id="88c67-112">Overview</span></span>

- <span data-ttu-id="88c67-113">El método `Main` es el punto de entrada de un programa ejecutable; es donde se inicia y finaliza el control del programa.</span><span class="sxs-lookup"><span data-stu-id="88c67-113">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="88c67-114">`Main` se declara dentro de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="88c67-114">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="88c67-115">El valor de `Main` debe ser [estático](../../language-reference/keywords/static.md) y no [público](../../language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="88c67-115">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="88c67-116">(En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.</span><span class="sxs-lookup"><span data-stu-id="88c67-116">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="88c67-117">`Main` puede tener un tipo de valor devuelto `void`, `int` o, a partir de C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="88c67-117">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="88c67-118">Solo si `Main` devuelve un tipo de valor devuelto `Task` o `Task<int>`, la declaración de `Main` puede incluir el modificador [`async`](../../language-reference/keywords/async.md),</span><span class="sxs-lookup"><span data-stu-id="88c67-118">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="88c67-119">pero tenga en cuenta que se excluirá de forma específica un método `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="88c67-119">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="88c67-120">El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="88c67-120">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="88c67-121">Al usar Visual Studio para crear aplicaciones de Windows, se puede agregar el parámetro manualmente o usar el método <xref:System.Environment.GetCommandLineArgs> con el fin de obtener los [argumentos de la línea de comandos](command-line-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="88c67-121">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="88c67-122">Los parámetros se leen como argumentos de línea de comandos indizados con cero.</span><span class="sxs-lookup"><span data-stu-id="88c67-122">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="88c67-123">A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos en la matriz `args`, pero es el primer elemento del método <xref:System.Environment.GetCommandLineArgs>.</span><span class="sxs-lookup"><span data-stu-id="88c67-123">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="88c67-124">A continuación se muestra una lista de firmas `Main` válidas:</span><span class="sxs-lookup"><span data-stu-id="88c67-124">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="88c67-125">En los ejemplos anteriores se usa el modificador de acceso público.</span><span class="sxs-lookup"><span data-stu-id="88c67-125">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="88c67-126">Es el procedimiento habitual, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="88c67-126">That is typical, but not required.</span></span>

<span data-ttu-id="88c67-127">Al agregar los tipos de valor devuelto `async`, `Task` y `Task<int>`, se simplifica el código de programa cuando las aplicaciones de consola tienen que realizar tareas de inicio y `await` de operaciones asincrónicas en `Main`.</span><span class="sxs-lookup"><span data-stu-id="88c67-127">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="88c67-128">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="88c67-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="88c67-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="88c67-129">See also</span></span>

- [<span data-ttu-id="88c67-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="88c67-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="88c67-131">Métodos</span><span class="sxs-lookup"><span data-stu-id="88c67-131">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="88c67-132">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="88c67-132">Inside a C# Program</span></span>](../inside-a-program/index.md)
