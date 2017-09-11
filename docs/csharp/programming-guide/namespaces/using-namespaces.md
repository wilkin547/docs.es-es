---
title: "Utilizar espacios de nombres (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.names
dev_langs:
- CSharp
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
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
ms.openlocfilehash: 61b5d78f1c4924e3858c14876d36e52d4ee46ceb
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="c46f5-102">Utilizar espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c46f5-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="c46f5-103">Los espacios de nombres se usan mucho en programas de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="c46f5-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="c46f5-104">En primer lugar, las clases de .NET Framework usan espacios de nombres para organizar sus clases.</span><span class="sxs-lookup"><span data-stu-id="c46f5-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="c46f5-105">En segundo lugar, declarar sus propios espacios de nombres puede ayudar a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="c46f5-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="c46f5-106">Acceder a los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="c46f5-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="c46f5-107">La mayoría de las aplicaciones de C# comienzan con una sección de directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="c46f5-108">En esta sección se muestran los espacios de nombres que la aplicación usará frecuentemente, y evita que el programador especifique un nombre completo cada vez que se use un método que se incluye dentro.</span><span class="sxs-lookup"><span data-stu-id="c46f5-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="c46f5-109">Por ejemplo, incluyendo la línea:</span><span class="sxs-lookup"><span data-stu-id="c46f5-109">For example, by including the line:</span></span>  
  
 <span data-ttu-id="c46f5-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-111">Al comienzo de un programa, el programador puede usar el código:</span><span class="sxs-lookup"><span data-stu-id="c46f5-111">At the start of a program, the programmer can use the code:</span></span>  
  
 <span data-ttu-id="c46f5-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-113">En lugar de:</span><span class="sxs-lookup"><span data-stu-id="c46f5-113">Instead of:</span></span>  
  
 <span data-ttu-id="c46f5-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span></span>  
  
## <a name="namespace-aliases"></a><span data-ttu-id="c46f5-115">Alias de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="c46f5-115">Namespace Aliases</span></span>  
 <span data-ttu-id="c46f5-116">La [directiva Using](../../../csharp/language-reference/keywords/using-directive.md) también puede usarse para crear un alias para un [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c46f5-116">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="c46f5-117">Por ejemplo, si está usando un espacio de nombres escrito previamente que contiene espacios de nombres anidados, puede que quiera declarar un alias para proporcionar una manera abreviada de hacer referencia a uno en concreto, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c46f5-117">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 <span data-ttu-id="c46f5-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span></span>  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="c46f5-119">Usar los espacios de nombres para controlar el ámbito</span><span class="sxs-lookup"><span data-stu-id="c46f5-119">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="c46f5-120">La palabra clave `namespace` se usa para declarar un ámbito.</span><span class="sxs-lookup"><span data-stu-id="c46f5-120">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="c46f5-121">La capacidad de crear ámbitos en su proyecto le ayuda a organizar código y le permite crear tipos únicos globalmente.</span><span class="sxs-lookup"><span data-stu-id="c46f5-121">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="c46f5-122">En el ejemplo siguiente, una clase denominada `SampleClass` se define en dos espacios de nombres, uno anidado dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="c46f5-122">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="c46f5-123">[. El operador ](../../../csharp/language-reference/operators/member-access-operator.md) se usa para diferenciar a qué método se llama.</span><span class="sxs-lookup"><span data-stu-id="c46f5-123">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 <span data-ttu-id="c46f5-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="c46f5-125">nombres completos</span><span class="sxs-lookup"><span data-stu-id="c46f5-125">Fully Qualified Names</span></span>  
 <span data-ttu-id="c46f5-126">Los espacios de nombres y los tipos tienen títulos únicos descritos mediante nombres completos que indican una jerarquía lógica.</span><span class="sxs-lookup"><span data-stu-id="c46f5-126">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="c46f5-127">Por ejemplo, la instrucción `A.B` implica que `A` es el nombre del espacio de nombres o el tipo, y `B` está anidado en su interior.</span><span class="sxs-lookup"><span data-stu-id="c46f5-127">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="c46f5-128">En el ejemplo siguiente, existen espacios de nombres y clases anidadas.</span><span class="sxs-lookup"><span data-stu-id="c46f5-128">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="c46f5-129">El nombre completo se indica como un comentario que sigue a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="c46f5-129">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 <span data-ttu-id="c46f5-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-131">En el segmento de código anterior:</span><span class="sxs-lookup"><span data-stu-id="c46f5-131">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="c46f5-132">El espacio de nombres `N1` es un miembro del espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="c46f5-132">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="c46f5-133">Su nombre completo es `N1`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-133">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="c46f5-134">El espacio de nombres `N2` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-134">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="c46f5-135">Su nombre completo es `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-135">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="c46f5-136">La clase `C1` es un miembro de `N1`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-136">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="c46f5-137">Su nombre completo es `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-137">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="c46f5-138">El nombre de la clase `C2` se usa dos veces en este código.</span><span class="sxs-lookup"><span data-stu-id="c46f5-138">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="c46f5-139">En cambio, los nombres completos son únicos.</span><span class="sxs-lookup"><span data-stu-id="c46f5-139">However, the fully qualified names are unique.</span></span> <span data-ttu-id="c46f5-140">La primera instancia de `C2` se declara dentro de `C1`; por lo tanto, su nombre completo es: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-140">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="c46f5-141">La segunda instancia de `C2` se declara dentro de un espacio de nombres `N2`; por lo tanto, su nombre completo es `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-141">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="c46f5-142">Con el segmento de código anterior, puede agregar un nuevo miembro de clase, `C3`, al espacio de nombres `N1.N2` de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="c46f5-142">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 <span data-ttu-id="c46f5-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-144">En general, use `::` para hacer referencia a un alias de espacio de nombres o `global::` para hacer referencia al espacio de nombres global y `.` para calificar tipos o miembros.</span><span class="sxs-lookup"><span data-stu-id="c46f5-144">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="c46f5-145">Es un error usar `::` con un alias que haga referencia a un tipo en lugar de a un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c46f5-145">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="c46f5-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c46f5-146">For example:</span></span>  
  
 <span data-ttu-id="c46f5-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-149">Recuerde que la palabra `global` no es un alias predefinido; por lo tanto, `global.X` no tiene ningún significado especial.</span><span class="sxs-lookup"><span data-stu-id="c46f5-149">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="c46f5-150">Adquiere un significado especial solo cuando se usa con `::`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-150">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="c46f5-151">La advertencia del compilador CS0440 se genera si define un alias denominado global porque `global::` siempre hace referencia al espacio de nombres global y no a un alias.</span><span class="sxs-lookup"><span data-stu-id="c46f5-151">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="c46f5-152">Por ejemplo, la línea siguiente genera la advertencia:</span><span class="sxs-lookup"><span data-stu-id="c46f5-152">For example, the following line generates the warning:</span></span>  
  
 <span data-ttu-id="c46f5-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-154">Usar `::` con alias es una buena idea y protege contra la introducción inesperada de tipos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c46f5-154">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="c46f5-155">Por ejemplo, considere este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c46f5-155">For example, consider this example:</span></span>  
  
 <span data-ttu-id="c46f5-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="c46f5-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span></span>  
  
 <span data-ttu-id="c46f5-158">Esto funciona, pero si un tipo denominado `Alias` fuera a introducirse posteriormente, `Alias.` se enlazaría a ese tipo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c46f5-158">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="c46f5-159">Usar `Alias::Exception` garantiza que `Alias` se trata como un alias de espacio de nombres y no se confunde con un tipo.</span><span class="sxs-lookup"><span data-stu-id="c46f5-159">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="c46f5-160">Vea el tema [Cómo: Usar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) para obtener más información sobre el alias `global`.</span><span class="sxs-lookup"><span data-stu-id="c46f5-160">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46f5-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="c46f5-161">See Also</span></span>  
 <span data-ttu-id="c46f5-162">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c46f5-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c46f5-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md)  (Espacios de nombres)</span><span class="sxs-lookup"><span data-stu-id="c46f5-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="c46f5-164">[Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="c46f5-164">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="c46f5-165">[. Operador](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c46f5-165">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="c46f5-166">[Operador ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="c46f5-166">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="c46f5-167">extern</span><span class="sxs-lookup"><span data-stu-id="c46f5-167">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

