---
title: 'Utilizar espacios de nombres: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 71d97f7c1c0c3ece0cdce3de4318d8a9d65baed3
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241934"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="79548-102">Uso de espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="79548-102">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="79548-103">Los espacios de nombres se usan mucho en programas de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="79548-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="79548-104">En primer lugar, las clases de .NET usan espacios de nombres para organizar sus clases.</span><span class="sxs-lookup"><span data-stu-id="79548-104">Firstly, the .NET classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="79548-105">En segundo lugar, declarar sus propios espacios de nombres puede ayudar a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="79548-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="79548-106">Acceso a los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="79548-106">Accessing namespaces</span></span>

 <span data-ttu-id="79548-107">La mayoría de las aplicaciones de C# comienzan con una sección de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="79548-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="79548-108">En esta sección se muestran los espacios de nombres que la aplicación usará frecuentemente, y evita que el programador especifique un nombre completo cada vez que se use un método que se incluye dentro.</span><span class="sxs-lookup"><span data-stu-id="79548-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="79548-109">Por ejemplo, incluyendo la línea:</span><span class="sxs-lookup"><span data-stu-id="79548-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="79548-110">Al comienzo de un programa, el programador puede usar el código:</span><span class="sxs-lookup"><span data-stu-id="79548-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="79548-111">En lugar de:</span><span class="sxs-lookup"><span data-stu-id="79548-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="79548-112">Alias de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="79548-112">Namespace aliases</span></span>

 <span data-ttu-id="79548-113">También puede usar la [directiva `using`](../../language-reference/keywords/using-directive.md) para crear un alias de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="79548-113">You can also use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="79548-114">Use el [calificador de alias de espacio de nombres `::`](../../language-reference/operators/namespace-alias-qualifier.md) para tener acceso a los miembros del espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="79548-114">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="79548-115">En el ejemplo siguiente se muestra cómo crear y usar un alias para un espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="79548-115">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="79548-116">Uso de los espacios de nombres para controlar el ámbito</span><span class="sxs-lookup"><span data-stu-id="79548-116">Using namespaces to control scope</span></span>

 <span data-ttu-id="79548-117">La palabra clave `namespace` se usa para declarar un ámbito.</span><span class="sxs-lookup"><span data-stu-id="79548-117">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="79548-118">La capacidad de crear ámbitos en su proyecto le ayuda a organizar código y le permite crear tipos únicos globalmente.</span><span class="sxs-lookup"><span data-stu-id="79548-118">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="79548-119">En el ejemplo siguiente, una clase denominada `SampleClass` se define en dos espacios de nombres, uno anidado dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="79548-119">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="79548-120">El token [`.`](../../language-reference/operators/member-access-operators.md#member-access-expression-) se usa para diferenciar a qué método se llama.</span><span class="sxs-lookup"><span data-stu-id="79548-120">The [`.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="79548-121">Nombres completos</span><span class="sxs-lookup"><span data-stu-id="79548-121">Fully qualified names</span></span>

 <span data-ttu-id="79548-122">Los espacios de nombres y los tipos tienen títulos únicos descritos mediante nombres completos que indican una jerarquía lógica.</span><span class="sxs-lookup"><span data-stu-id="79548-122">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="79548-123">Por ejemplo, la instrucción `A.B` implica que `A` es el nombre del espacio de nombres o el tipo, y `B` está anidado en su interior.</span><span class="sxs-lookup"><span data-stu-id="79548-123">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="79548-124">En el ejemplo siguiente, existen espacios de nombres y clases anidadas.</span><span class="sxs-lookup"><span data-stu-id="79548-124">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="79548-125">El nombre completo se indica como un comentario que sigue a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="79548-125">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="79548-126">En el segmento de código anterior:</span><span class="sxs-lookup"><span data-stu-id="79548-126">In the previous code segment:</span></span>  
  
- <span data-ttu-id="79548-127">El espacio de nombres `N1` es un miembro del espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="79548-127">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="79548-128">Su nombre completo es `N1`.</span><span class="sxs-lookup"><span data-stu-id="79548-128">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="79548-129">El espacio de nombres `N2` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="79548-129">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="79548-130">Su nombre completo es `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="79548-130">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="79548-131">La clase `C1` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="79548-131">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="79548-132">Su nombre completo es `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="79548-132">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="79548-133">El nombre de la clase `C2` se usa dos veces en este código.</span><span class="sxs-lookup"><span data-stu-id="79548-133">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="79548-134">En cambio, los nombres completos son únicos.</span><span class="sxs-lookup"><span data-stu-id="79548-134">However, the fully qualified names are unique.</span></span> <span data-ttu-id="79548-135">La primera instancia de `C2` se declara dentro de `C1`; por lo tanto, su nombre completo es: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="79548-135">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="79548-136">La segunda instancia de `C2` se declara dentro de un espacio de nombres `N2`; por lo tanto, su nombre completo es `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="79548-136">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="79548-137">Con el segmento de código anterior, puede agregar un nuevo miembro de clase, `C3`, al espacio de nombres `N1.N2` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="79548-137">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="79548-138">En general, use el [calificador de alias de espacio de nombres`::`](../../language-reference/operators/namespace-alias-qualifier.md) para hacer referencia a un alias de espacio de nombres o `global::` para hacer referencia al espacio de nombres global y `.` para calificar tipos o miembros.</span><span class="sxs-lookup"><span data-stu-id="79548-138">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="79548-139">Es un error usar `::` con un alias que haga referencia a un tipo en lugar de a un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="79548-139">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="79548-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79548-140">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="79548-141">Recuerde que la palabra `global` no es un alias predefinido; por lo tanto, `global.X` no tiene ningún significado especial.</span><span class="sxs-lookup"><span data-stu-id="79548-141">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="79548-142">Adquiere un significado especial solo cuando se usa con `::`.</span><span class="sxs-lookup"><span data-stu-id="79548-142">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="79548-143">La advertencia del compilador CS0440 se genera si define un alias denominado global porque `global::` siempre hace referencia al espacio de nombres global y no a un alias.</span><span class="sxs-lookup"><span data-stu-id="79548-143">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="79548-144">Por ejemplo, la línea siguiente genera la advertencia:</span><span class="sxs-lookup"><span data-stu-id="79548-144">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="79548-145">Usar `::` con alias es una buena idea y protege contra la introducción inesperada de tipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="79548-145">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="79548-146">Por ejemplo, considere este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79548-146">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="79548-147">Esto funciona, pero si un tipo denominado `Alias` fuera a introducirse posteriormente, `Alias.` se enlazaría a ese tipo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="79548-147">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="79548-148">Usar `Alias::Exception` garantiza que `Alias` se trata como un alias de espacio de nombres y no se confunde con un tipo.</span><span class="sxs-lookup"><span data-stu-id="79548-148">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="79548-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="79548-149">See also</span></span>

- [<span data-ttu-id="79548-150">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="79548-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="79548-151">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="79548-151">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="79548-152">Expresión de acceso a miembro</span><span class="sxs-lookup"><span data-stu-id="79548-152">Member access expression</span></span>](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [<span data-ttu-id="79548-153">Operador ::</span><span class="sxs-lookup"><span data-stu-id="79548-153">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="79548-154">extern alias</span><span class="sxs-lookup"><span data-stu-id="79548-154">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
