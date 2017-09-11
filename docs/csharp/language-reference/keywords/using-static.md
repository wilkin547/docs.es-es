---
title: using static (Directiva, Referencia de C#)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: b7d69d0262ba6f450e2cc0d5b30692bba181f9d9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="aef9f-102">using static (Directiva, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="aef9f-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="aef9f-103">La directiva `using static` designa un tipo a cuyos miembros estáticos se puede acceder sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="aef9f-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="aef9f-104">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="aef9f-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="aef9f-105">donde *fully-qualified-type-name* es el nombre del tipo a cuyos miembros estáticos se puede hacer referencia sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="aef9f-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="aef9f-106">Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador CS0246: "The type or namespace name '<type-name>' could not be found" (No se pudo encontrar el nombre de tipo o de espacio de nombres "<type-name>").</span><span class="sxs-lookup"><span data-stu-id="aef9f-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="aef9f-107">La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos, aunque también tenga miembros de instancia.</span><span class="sxs-lookup"><span data-stu-id="aef9f-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="aef9f-108">Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="aef9f-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="aef9f-109">La directiva `using static` se ha agregado en C# 6.</span><span class="sxs-lookup"><span data-stu-id="aef9f-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="aef9f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aef9f-110">Remarks</span></span>
 
<span data-ttu-id="aef9f-111">Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro.</span><span class="sxs-lookup"><span data-stu-id="aef9f-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="aef9f-112">Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro.</span><span class="sxs-lookup"><span data-stu-id="aef9f-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="aef9f-113">Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase @System.Math.</span><span class="sxs-lookup"><span data-stu-id="aef9f-113">For example, the following definition of a `Circle` class references a number of members of the @System.Math class.</span></span>
  
<span data-ttu-id="aef9f-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="aef9f-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span></span>

<span data-ttu-id="aef9f-115">Al eliminar la necesidad de hacer referencia explícitamente a la clase @System.Math cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:</span><span class="sxs-lookup"><span data-stu-id="aef9f-115">By eliminating the need to explicitly reference the @System.Math class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

<span data-ttu-id="aef9f-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="aef9f-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span></span>

<span data-ttu-id="aef9f-117">`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="aef9f-117">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="aef9f-118">Los miembros heredados no se importan.</span><span class="sxs-lookup"><span data-stu-id="aef9f-118">Inherited members are not imported.</span></span>  <span data-ttu-id="aef9f-119">Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="aef9f-119">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="aef9f-120">Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.</span><span class="sxs-lookup"><span data-stu-id="aef9f-120">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="aef9f-121">`using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="aef9f-121">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="aef9f-122">Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.</span><span class="sxs-lookup"><span data-stu-id="aef9f-122">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="aef9f-123">Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.</span><span class="sxs-lookup"><span data-stu-id="aef9f-123">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="aef9f-124">La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.</span><span class="sxs-lookup"><span data-stu-id="aef9f-124">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aef9f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aef9f-125">Example</span></span>

<span data-ttu-id="aef9f-126">En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases @System.Console, @System.Math y @System.String estén disponibles sin tener que especificar su nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="aef9f-126">The following example uses the `using static` directive to make the static members of the @System.Console, @System.Math, and @System.String classes available without having to specify their type name.</span></span>

<span data-ttu-id="aef9f-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span><span class="sxs-lookup"><span data-stu-id="aef9f-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span></span>

<span data-ttu-id="aef9f-128">En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo @System.Double.</span><span class="sxs-lookup"><span data-stu-id="aef9f-128">In the example, the `using static` directive could also have been applied to the @System.Double type.</span></span> <span data-ttu-id="aef9f-129">Esto habría permitido llamar al método @System.Double.TryParse(System.String,System.Double@) sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="aef9f-129">This would have made it possible to call the @System.Double.TryParse(System.String,System.Double@) method without specifying a type name.</span></span> <span data-ttu-id="aef9f-130">Pero esto crea un código menos legible, ya que es necesario comprobar las instrucciones `using static` para determinar el método `TryParse` de tipo numérico al que se llama.</span><span class="sxs-lookup"><span data-stu-id="aef9f-130">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="aef9f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="aef9f-131">See also</span></span>

<span data-ttu-id="aef9f-132">[using Directive](using-directive.md)  (using [Directiva, Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="aef9f-132">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="aef9f-133">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="aef9f-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="aef9f-134">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="aef9f-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="aef9f-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  (Usar espacios de nombres)</span><span class="sxs-lookup"><span data-stu-id="aef9f-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="aef9f-136">[Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="aef9f-136">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="aef9f-137">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="aef9f-137">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   

