---
title: "Constantes (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 85273420e9e0dbf4b8f24568d97be127c85d5f42
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="068e9-102">Constantes (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="068e9-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="068e9-103">Las constantes son valores inmutables que se conocen en tiempo de compilación y que no cambian durante la vida del programa.</span><span class="sxs-lookup"><span data-stu-id="068e9-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="068e9-104">Las constantes se declaran con el modificador [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="068e9-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="068e9-105">Solo los tipos integrados de C# (excluido <xref:System.Object?displayProperty=fullName>) pueden declararse como `const`.</span><span class="sxs-lookup"><span data-stu-id="068e9-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=fullName>) may be declared as `const`.</span></span> <span data-ttu-id="068e9-106">Para obtener una lista de los tipos integrados, vea [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="068e9-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="068e9-107">Los tipos definidos por el usuario, incluidas las clases, las estructuras y las matrices, no pueden ser `const`.</span><span class="sxs-lookup"><span data-stu-id="068e9-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="068e9-108">Use el modificador [readonly](../../../csharp/language-reference/keywords/readonly.md) para crear una clase, una estructura o una matriz que se inicialice una vez en tiempo de ejecución (por ejemplo, en un constructor) y que posteriormente no se pueda cambiar.</span><span class="sxs-lookup"><span data-stu-id="068e9-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="068e9-109">C# no admite métodos, propiedades ni eventos `const`.</span><span class="sxs-lookup"><span data-stu-id="068e9-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="068e9-110">El tipo enum permite definir constantes con nombre para los tipos integrados enteros (por ejemplo, `int`, `uint`, `long`, etc.).</span><span class="sxs-lookup"><span data-stu-id="068e9-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="068e9-111">Para más información, vea [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="068e9-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="068e9-112">Las constantes se deben inicializar al declararse.</span><span class="sxs-lookup"><span data-stu-id="068e9-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="068e9-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="068e9-113">For example:</span></span>  
  
 <span data-ttu-id="068e9-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="068e9-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span></span>  
  
 <span data-ttu-id="068e9-115">En este ejemplo la constante `months` siempre es 12 y ni siquiera la propia clase la puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="068e9-115">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="068e9-116">De hecho, cuando el compilador detecta un identificador de constante en el código fuente de C# (por ejemplo, `months`), sustituye directamente el valor literal en el código de lenguaje intermedio (IL) que genera.</span><span class="sxs-lookup"><span data-stu-id="068e9-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="068e9-117">Dado que no hay ninguna dirección de variable asociada a una constante en tiempo de ejecución, no se pueden pasar los campos `const` por referencia ni pueden aparecer como un valor L en una expresión.</span><span class="sxs-lookup"><span data-stu-id="068e9-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="068e9-118">Tenga cuidado al hacer referencia a valores de constante definidos en otro código como archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="068e9-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="068e9-119">Si una nueva versión del archivo DLL define un nuevo valor para la constante, el programa conservará el valor literal anterior hasta que se vuelva a compilar con la versión nueva.</span><span class="sxs-lookup"><span data-stu-id="068e9-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="068e9-120">Se pueden declarar varias constantes del mismo tipo a la vez, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="068e9-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 <span data-ttu-id="068e9-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="068e9-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span></span>  
  
 <span data-ttu-id="068e9-122">La expresión que se usa para inicializar una constante puede hacer referencia a otra constante si no crea una referencia circular.</span><span class="sxs-lookup"><span data-stu-id="068e9-122">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="068e9-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="068e9-123">For example:</span></span>  
  
 <span data-ttu-id="068e9-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="068e9-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span></span>  
  
 <span data-ttu-id="068e9-125">Las constantes se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="068e9-125">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="068e9-126">Estos modificadores de acceso definen cómo los usuarios de la clase pueden acceder a la constante.</span><span class="sxs-lookup"><span data-stu-id="068e9-126">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="068e9-127">Para más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="068e9-127">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="068e9-128">A las constantes se accede como si fueran campos [estáticos](../../../csharp/language-reference/keywords/static.md) porque el valor de la constante es el mismo para todas las instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="068e9-128">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="068e9-129">No use la palabra clave `static` para declararlas.</span><span class="sxs-lookup"><span data-stu-id="068e9-129">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="068e9-130">Las expresiones que no están en la clase que define la constante deben usar el nombre de la clase, un punto y el nombre de la constante para acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="068e9-130">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="068e9-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="068e9-131">For example:</span></span>  
  
 <span data-ttu-id="068e9-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="068e9-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="068e9-133">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="068e9-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="068e9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="068e9-134">See Also</span></span>  
 <span data-ttu-id="068e9-135">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="068e9-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="068e9-136">[Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="068e9-136">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="068e9-137">[Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="068e9-137">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="068e9-138">[Tipos](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="068e9-138">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="068e9-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="068e9-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span></span>  
 [<span data-ttu-id="068e9-140">Immutability in C# Part One: Kinds of Immutability (Inmutabilidad en C# (primera parte): tipos de inmutabilidad)</span><span class="sxs-lookup"><span data-stu-id="068e9-140">Immutability in C# Part One: Kinds of Immutability</span></span>](http://go.microsoft.com/fwlink/?LinkId=112379)

