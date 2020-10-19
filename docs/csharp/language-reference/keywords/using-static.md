---
description: using static (Directiva, Referencia de C#)
title: using static (Directiva, Referencia de C#)
ms.date: 03/10/2017
f1_keywords:
- using-static_CSharpKeyword
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: d117d4423a2f7c782cd6365a73e6c18298d89abc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162237"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="b0a45-103">using static (Directiva, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b0a45-103">using static directive (C# Reference)</span></span>

<span data-ttu-id="b0a45-104">La directiva `using static` designa un tipo a cuyos miembros estáticos y tipos anidados se puede acceder sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="b0a45-104">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="b0a45-105">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="b0a45-105">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="b0a45-106">donde *nombre-completo-del-tipo* es el nombre del tipo a cuyos miembros estáticos y tipos anidados se puede hacer referencia sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="b0a45-106">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="b0a45-107">Si no proporciona un nombre de tipo completo (el nombre del espacio de nombres completo junto con el nombre del tipo), C# genera el error del compilador [CS0246](../compiler-messages/cs0246.md): "No se pudo encontrar el tipo o el nombre del espacio de nombres 'type/namespace' (¿falta una directiva using o una referencia de ensamblado?)".</span><span class="sxs-lookup"><span data-stu-id="b0a45-107">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="b0a45-108">La directiva `using static` se aplica a cualquier tipo que tenga miembros estáticos (o tipos anidados), aunque también tenga miembros de instancia.</span><span class="sxs-lookup"><span data-stu-id="b0a45-108">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="b0a45-109">Pero los miembros de instancia solo pueden invocarse a través de la instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="b0a45-109">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="b0a45-110">La directiva `using static` se ha agregado en C# 6.</span><span class="sxs-lookup"><span data-stu-id="b0a45-110">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0a45-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0a45-111">Remarks</span></span>

<span data-ttu-id="b0a45-112">Normalmente, cuando se llama a un miembro estático, se especifica el nombre de tipo junto con el nombre de miembro.</span><span class="sxs-lookup"><span data-stu-id="b0a45-112">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="b0a45-113">Especificar varias veces el mismo nombre de tipo para invocar los miembros del tipo puede traducirse en código detallado y poco claro.</span><span class="sxs-lookup"><span data-stu-id="b0a45-113">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="b0a45-114">Por ejemplo, la siguiente definición de una clase `Circle` hace referencia a un número de miembros de la clase <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="b0a45-114">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="b0a45-115">Al eliminar la necesidad de hacer referencia explícitamente a la clase <xref:System.Math> cada vez que se hace referencia a un miembro, la directiva `using static` genera un código mucho más limpio:</span><span class="sxs-lookup"><span data-stu-id="b0a45-115">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="b0a45-116">`using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="b0a45-116">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="b0a45-117">Los miembros heredados no se importan.</span><span class="sxs-lookup"><span data-stu-id="b0a45-117">Inherited members are not imported.</span></span>  <span data-ttu-id="b0a45-118">Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0a45-118">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="b0a45-119">Las funciones de nivel superior F# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C# válido.</span><span class="sxs-lookup"><span data-stu-id="b0a45-119">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="b0a45-120">`using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="b0a45-120">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="b0a45-121">Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.</span><span class="sxs-lookup"><span data-stu-id="b0a45-121">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="b0a45-122">Los métodos con el mismo nombre que se importen desde tipos distintos con distintas directivas `using static` en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.</span><span class="sxs-lookup"><span data-stu-id="b0a45-122">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="b0a45-123">La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C#.</span><span class="sxs-lookup"><span data-stu-id="b0a45-123">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="b0a45-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0a45-124">Example</span></span>

<span data-ttu-id="b0a45-125">En el ejemplo siguiente se usa la directiva `using static` para que los miembros estáticos de las clases <xref:System.Console>, <xref:System.Math> y <xref:System.String> estén disponibles sin tener que especificar su nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="b0a45-125">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="b0a45-126">En el ejemplo, también podría haberse aplicado la directiva `using static` al tipo <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="b0a45-126">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="b0a45-127">Esto habría permitido llamar al método <xref:System.Double.TryParse(System.String,System.Double@)> sin especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="b0a45-127">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="b0a45-128">Sin embargo, el código que se crea es menos legible, ya que es necesario comprobar las directivas `using static` para determinar el método `TryParse` del tipo numérico al que se llama.</span><span class="sxs-lookup"><span data-stu-id="b0a45-128">However, this creates less readable code, since it becomes necessary to check the `using static` directives to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0a45-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a45-129">See also</span></span>

- [<span data-ttu-id="b0a45-130">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="b0a45-130">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="b0a45-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b0a45-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0a45-132">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b0a45-132">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b0a45-133">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="b0a45-133">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="b0a45-134">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="b0a45-134">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
