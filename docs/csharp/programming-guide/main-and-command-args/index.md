---
title: Main() y argumentos de la línea de comandos (Guía de programación de C#)
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 144d03edf28464717430bd0ae83db637578d8296
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "43892261"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="03e41-102">Main() y argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="03e41-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="03e41-103">El método `Main` es el punto de entrada de una aplicación de C#</span><span class="sxs-lookup"><span data-stu-id="03e41-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="03e41-104">(las bibliotecas y los servicios no requieren un método `Main` como punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.</span><span class="sxs-lookup"><span data-stu-id="03e41-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="03e41-105">Solo puede haber un punto de entrada en un programa de C#.</span><span class="sxs-lookup"><span data-stu-id="03e41-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="03e41-106">Si hay más de una clase que tiene un método `Main`, debe compilar el programa con la opción del compilador **/main** para especificar qué método `Main` desea utilizar como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="03e41-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="03e41-107">Para obtener más información, consulte [/main (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="03e41-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="03e41-108">Información general</span><span class="sxs-lookup"><span data-stu-id="03e41-108">Overview</span></span>

- <span data-ttu-id="03e41-109">El método `Main` es el punto de entrada de un programa ejecutable; es donde se inicia y finaliza el control del programa.</span><span class="sxs-lookup"><span data-stu-id="03e41-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="03e41-110">`Main` se declara dentro de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="03e41-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="03e41-111">El valor de `Main` debe ser [estático](../../../csharp/language-reference/keywords/static.md) y no [público](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="03e41-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="03e41-112">(En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../../csharp/language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.</span><span class="sxs-lookup"><span data-stu-id="03e41-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="03e41-113">`Main` puede tener un tipo de valor devuelto `void`, `int` o, a partir de C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="03e41-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="03e41-114">Solo si `Main` devuelve un tipo de valor devuelto `Task` o `Task<int>`, la declaración de `Main` puede incluir el modificador [`async`](../../language-reference/keywords/async.md),</span><span class="sxs-lookup"><span data-stu-id="03e41-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="03e41-115">pero tenga en cuenta que se excluirá de forma específica un método `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="03e41-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="03e41-116">El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="03e41-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="03e41-117">Al usar Visual Studio para crear aplicaciones de Windows, se puede agregar el parámetro manualmente o usar la clase <xref:System.Environment> con el fin de obtener los argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="03e41-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="03e41-118">Los parámetros se leen como argumentos de línea de comandos indizados con cero.</span><span class="sxs-lookup"><span data-stu-id="03e41-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="03e41-119">A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="03e41-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="03e41-120">Al agregar los tipos de valor devuelto `async`, `Task` y `Task<int>`, se simplifica el código de programa cuando las aplicaciones de consola tienen que realizar tareas de inicio y `await` de operaciones asincrónicas en `Main`.</span><span class="sxs-lookup"><span data-stu-id="03e41-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03e41-121">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="03e41-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="03e41-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e41-122">See Also</span></span>

- [<span data-ttu-id="03e41-123">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="03e41-123">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="03e41-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="03e41-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="03e41-125">Métodos</span><span class="sxs-lookup"><span data-stu-id="03e41-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [<span data-ttu-id="03e41-126">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="03e41-126">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
