---
title: 'Utilizar espacios de nombres: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: c5bede7475fdbee3f3524984a9be97b95b44817d
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452683"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="d7f6e-102">Utilizar espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d7f6e-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="d7f6e-103">Los espacios de nombres se usan mucho en programas de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="d7f6e-104">En primer lugar, las clases de .NET Framework usan espacios de nombres para organizar sus clases.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="d7f6e-105">En segundo lugar, declarar sus propios espacios de nombres puede ayudar a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="d7f6e-106">Acceder a los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d7f6e-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="d7f6e-107">La mayoría de las aplicaciones de C# comienzan con una sección de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="d7f6e-108">En esta sección se muestran los espacios de nombres que la aplicación usará frecuentemente, y evita que el programador especifique un nombre completo cada vez que se use un método que se incluye dentro.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="d7f6e-109">Por ejemplo, incluyendo la línea:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="d7f6e-110">Al comienzo de un programa, el programador puede usar el código:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="d7f6e-111">En lugar de:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="d7f6e-112">Alias de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d7f6e-112">Namespace Aliases</span></span>  
 <span data-ttu-id="d7f6e-113">La [directiva Using](../../../csharp/language-reference/keywords/using-directive.md) también puede usarse para crear un alias para un [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d7f6e-113">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="d7f6e-114">Por ejemplo, si está usando un espacio de nombres escrito previamente que contiene espacios de nombres anidados, puede que quiera declarar un alias para proporcionar una manera abreviada de hacer referencia a uno en concreto, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-114">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#7)]  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="d7f6e-115">Usar los espacios de nombres para controlar el ámbito</span><span class="sxs-lookup"><span data-stu-id="d7f6e-115">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="d7f6e-116">La palabra clave `namespace` se usa para declarar un ámbito.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-116">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="d7f6e-117">La capacidad de crear ámbitos en su proyecto le ayuda a organizar código y le permite crear tipos únicos globalmente.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-117">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="d7f6e-118">En el ejemplo siguiente, una clase denominada `SampleClass` se define en dos espacios de nombres, uno anidado dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-118">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="d7f6e-119">El [operador `.` de acceso a miembros](../../language-reference/operators/member-access-operators.md#member-access-operator-) se utiliza para diferenciar el método al que se llama.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-119">The [member access `.` operator](../../language-reference/operators/member-access-operators.md#member-access-operator-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="d7f6e-120">nombres completos</span><span class="sxs-lookup"><span data-stu-id="d7f6e-120">Fully Qualified Names</span></span>  
 <span data-ttu-id="d7f6e-121">Los espacios de nombres y los tipos tienen títulos únicos descritos mediante nombres completos que indican una jerarquía lógica.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-121">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="d7f6e-122">Por ejemplo, la instrucción `A.B` implica que `A` es el nombre del espacio de nombres o el tipo, y `B` está anidado en su interior.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-122">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="d7f6e-123">En el ejemplo siguiente, existen espacios de nombres y clases anidadas.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-123">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="d7f6e-124">El nombre completo se indica como un comentario que sigue a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-124">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="d7f6e-125">En el segmento de código anterior:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-125">In the previous code segment:</span></span>  
  
- <span data-ttu-id="d7f6e-126">El espacio de nombres `N1` es un miembro del espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-126">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="d7f6e-127">Su nombre completo es `N1`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-127">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="d7f6e-128">El espacio de nombres `N2` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-128">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="d7f6e-129">Su nombre completo es `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-129">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="d7f6e-130">La clase `C1` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-130">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="d7f6e-131">Su nombre completo es `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-131">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="d7f6e-132">El nombre de la clase `C2` se usa dos veces en este código.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-132">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="d7f6e-133">En cambio, los nombres completos son únicos.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-133">However, the fully qualified names are unique.</span></span> <span data-ttu-id="d7f6e-134">La primera instancia de `C2` se declara dentro de `C1`; por lo tanto, su nombre completo es: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-134">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="d7f6e-135">La segunda instancia de `C2` se declara dentro de un espacio de nombres `N2`; por lo tanto, su nombre completo es `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-135">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="d7f6e-136">Con el segmento de código anterior, puede agregar un nuevo miembro de clase, `C3`, al espacio de nombres `N1.N2` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-136">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="d7f6e-137">En general, use `::` para hacer referencia a un alias de espacio de nombres o `global::` para hacer referencia al espacio de nombres global y `.` para calificar tipos o miembros.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-137">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="d7f6e-138">Es un error usar `::` con un alias que haga referencia a un tipo en lugar de a un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-138">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="d7f6e-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-139">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="d7f6e-140">Recuerde que la palabra `global` no es un alias predefinido; por lo tanto, `global.X` no tiene ningún significado especial.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-140">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="d7f6e-141">Adquiere un significado especial solo cuando se usa con `::`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-141">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="d7f6e-142">La advertencia del compilador CS0440 se genera si define un alias denominado global porque `global::` siempre hace referencia al espacio de nombres global y no a un alias.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-142">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="d7f6e-143">Por ejemplo, la línea siguiente genera la advertencia:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-143">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="d7f6e-144">Usar `::` con alias es una buena idea y protege contra la introducción inesperada de tipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-144">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="d7f6e-145">Por ejemplo, considere este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7f6e-145">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="d7f6e-146">Esto funciona, pero si un tipo denominado `Alias` fuera a introducirse posteriormente, `Alias.` se enlazaría a ese tipo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-146">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="d7f6e-147">Usar `Alias::Exception` garantiza que `Alias` se trata como un alias de espacio de nombres y no se confunde con un tipo.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-147">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="d7f6e-148">Vea el tema [Cómo: Usar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) para obtener más información sobre el alias `global`.</span><span class="sxs-lookup"><span data-stu-id="d7f6e-148">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f6e-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7f6e-149">See also</span></span>

- [<span data-ttu-id="d7f6e-150">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d7f6e-150">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d7f6e-151">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d7f6e-151">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="d7f6e-152">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d7f6e-152">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)
- [<span data-ttu-id="d7f6e-153">. !</span><span class="sxs-lookup"><span data-stu-id="d7f6e-153">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="d7f6e-154">:: !</span><span class="sxs-lookup"><span data-stu-id="d7f6e-154">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="d7f6e-155">extern</span><span class="sxs-lookup"><span data-stu-id="d7f6e-155">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
