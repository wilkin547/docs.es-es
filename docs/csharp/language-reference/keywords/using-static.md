---
title: using static (Directiva, Referencia de C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5838bede475cf2ad1b72518770241e86206a06bb
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="92546-102">using static (Directiva, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="92546-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="92546-103">La directiva `using static` designa un tipo a cuyos miembros estáticos se puede acceder sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="92546-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="92546-104">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="92546-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="92546-105">donde *fully-qualified-type-name* es el nombre del tipo a cuyos miembros estáticos se puede hacer referencia sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="92546-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="92546-106">Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador CS0246: "The type or namespace name '<type-name>' could not be found" (No se pudo encontrar el nombre de tipo o de espacio de nombres "<type-name>").</span><span class="sxs-lookup"><span data-stu-id="92546-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="92546-107">La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos, aunque también tenga miembros de instancia.</span><span class="sxs-lookup"><span data-stu-id="92546-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="92546-108">Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="92546-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="92546-109">La directiva `using static` se ha agregado en C# 6.</span><span class="sxs-lookup"><span data-stu-id="92546-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="92546-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92546-110">Remarks</span></span>
 
<span data-ttu-id="92546-111">Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro.</span><span class="sxs-lookup"><span data-stu-id="92546-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="92546-112">Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro.</span><span class="sxs-lookup"><span data-stu-id="92546-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="92546-113">Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="92546-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>
  
[!code-csharp[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="92546-114">Al eliminar la necesidad de hacer referencia explícitamente a la clase <xref:System.Math> cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:</span><span class="sxs-lookup"><span data-stu-id="92546-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="92546-115">`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="92546-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="92546-116">Los miembros heredados no se importan.</span><span class="sxs-lookup"><span data-stu-id="92546-116">Inherited members are not imported.</span></span>  <span data-ttu-id="92546-117">Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="92546-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="92546-118">Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.</span><span class="sxs-lookup"><span data-stu-id="92546-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="92546-119">`using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="92546-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="92546-120">Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.</span><span class="sxs-lookup"><span data-stu-id="92546-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="92546-121">Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.</span><span class="sxs-lookup"><span data-stu-id="92546-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="92546-122">La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.</span><span class="sxs-lookup"><span data-stu-id="92546-122">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92546-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92546-123">Example</span></span>

<span data-ttu-id="92546-124">En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases <xref:System.Console>, <xref:System.Math> y <xref:System.String> estén disponibles sin tener que especificar su nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="92546-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="92546-125">En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="92546-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="92546-126">Esto habría hecho que sea posible llamar a la <xref:System.Double.TryParse(System.String,System.Double@)> método sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="92546-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="92546-127">Pero esto crea un código menos legible, ya que es necesario comprobar las instrucciones `using static` para determinar el método `TryParse` de tipo numérico al que se llama.</span><span class="sxs-lookup"><span data-stu-id="92546-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="92546-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="92546-128">See also</span></span>

<span data-ttu-id="92546-129">[using Directive](using-directive.md)  (using [Directiva, Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="92546-129">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="92546-130">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="92546-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="92546-131">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="92546-131">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="92546-132">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  (Usar espacios de nombres)</span><span class="sxs-lookup"><span data-stu-id="92546-132">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="92546-133">[Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="92546-133">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="92546-134">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="92546-134">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   
