---
title: "Main() y argumentos de la línea de comandos (Guía de programación de C#)"
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 51408654abd0dcd2f7159438b507c44bd579bfd9
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="840f6-102">Main() y argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="840f6-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="840f6-103">El método `Main` es el punto de entrada de una aplicación de C#</span><span class="sxs-lookup"><span data-stu-id="840f6-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="840f6-104">(las bibliotecas y los servicios no requieren un método `Main` como punto de entrada). Cuando se inicia la aplicación, el método `Main` es el primero que se invoca.</span><span class="sxs-lookup"><span data-stu-id="840f6-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="840f6-105">Solo puede haber un punto de entrada en un programa de C#.</span><span class="sxs-lookup"><span data-stu-id="840f6-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="840f6-106">Si hay más de una clase que tiene un método `Main`, debe compilar el programa con la opción del compilador **/main** para especificar qué método `Main` desea utilizar como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="840f6-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="840f6-107">Para obtener más información, consulte [/main (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="840f6-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 <span data-ttu-id="840f6-108">[!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="840f6-108">[!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]</span></span>

## <a name="overview"></a><span data-ttu-id="840f6-109">Información general</span><span class="sxs-lookup"><span data-stu-id="840f6-109">Overview</span></span>

- <span data-ttu-id="840f6-110">El método `Main` es el punto de entrada de un programa ejecutable; es donde se inicia y finaliza el control del programa.</span><span class="sxs-lookup"><span data-stu-id="840f6-110">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="840f6-111">`Main` se declara dentro de una clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="840f6-111">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="840f6-112">El valor de `Main` debe ser [estático](../../../csharp/language-reference/keywords/static.md) y no [público](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="840f6-112">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="840f6-113">(En el ejemplo anterior, recibe el acceso predeterminado de [privado](../../../csharp/language-reference/keywords/private.md)). La clase o estructura envolvente no debe ser estático.</span><span class="sxs-lookup"><span data-stu-id="840f6-113">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="840f6-114">`Main` puede tener un tipo de valor devuelto `void`, `int` o, a partir de C# 7.1, `Task` o `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="840f6-114">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="840f6-115">Solo si `Main` devuelve un tipo de valor devuelto `Task` o `Task<int>`, la declaración de `Main` puede incluir el modificador [`async`](../../language-reference/keywords/async.md),</span><span class="sxs-lookup"><span data-stu-id="840f6-115">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="840f6-116">pero tenga en cuenta que se excluirá de forma específica un método `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="840f6-116">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="840f6-117">El método `Main` se puede declarar con o sin un parámetro `string[]` que contiene los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="840f6-117">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="840f6-118">Al usar [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] para crear aplicaciones Windows, se puede agregar el parámetro manualmente o utilizar la clase <xref:System.Environment> con el fin de obtener los argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="840f6-118">When using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="840f6-119">Los parámetros se leen como argumentos de línea de comandos indizados con cero.</span><span class="sxs-lookup"><span data-stu-id="840f6-119">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="840f6-120">A diferencia de C y C++, el nombre del programa no se trata como el primer argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="840f6-120">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="840f6-121">Al agregar los tipos de valor devuelto `async`, `Task` y `Task<int>`, se simplifica el código de programa cuando las aplicaciones de consola tienen que realizar tareas de inicio y `await` de operaciones asincrónicas en `Main`.</span><span class="sxs-lookup"><span data-stu-id="840f6-121">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="840f6-122">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="840f6-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="840f6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="840f6-123">See also</span></span>
<span data-ttu-id="840f6-124">[Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[Guía de programación de C#](../../../csharp/programming-guide/index.md)
[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)
[Dentro de un programa de C#](../../../csharp/programming-guide/inside-a-program/index.md)</span><span class="sxs-lookup"><span data-stu-id="840f6-124">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[C# Programming Guide](../../../csharp/programming-guide/index.md)
[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md)
[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md)</span></span>

