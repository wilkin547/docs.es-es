---
title: "Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
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
ms.openlocfilehash: 1252fc107d46b1d3a1cbef0a61708edc57253910
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="5bc46-102">Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5bc46-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="5bc46-103">La capacidad de tener acceso a un miembro en el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) global es útil cuando el miembro puede estar oculto por otra entidad del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5bc46-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="5bc46-104">Por ejemplo, en el código siguiente, `Console` se resuelve como `TestApp.Console` en lugar de como el tipo `Console` en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="5bc46-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 <span data-ttu-id="5bc46-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-107">Usar `System.Console` todavía provoca un error porque el espacio de nombres `System` está oculto mediante la clase `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="5bc46-107">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 <span data-ttu-id="5bc46-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-109">En cambio, puede solucionar este error con `global::System.Console`, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="5bc46-109">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 <span data-ttu-id="5bc46-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-111">Cuando el identificador izquierdo es `global`, la búsqueda del identificador derecho comienza en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="5bc46-111">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="5bc46-112">Por ejemplo, la siguiente declaración está haciendo referencia a `TestApp` como un miembro del espacio global.</span><span class="sxs-lookup"><span data-stu-id="5bc46-112">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 <span data-ttu-id="5bc46-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-114">Obviamente, no se recomienda crear sus propios espacios de nombres denominados `System`, y es poco probable que encuentre cualquier código donde haya ocurrido esto.</span><span class="sxs-lookup"><span data-stu-id="5bc46-114">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="5bc46-115">En cambio, en proyectos más grandes, es una posibilidad muy real que pueda producirse una duplicación de espacio de nombres de una forma u otra.</span><span class="sxs-lookup"><span data-stu-id="5bc46-115">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="5bc46-116">En estas situaciones, el calificador de espacio de nombres global es su garantía de que puede especificar el espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="5bc46-116">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bc46-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bc46-117">Example</span></span>  
 <span data-ttu-id="5bc46-118">En este ejemplo, el espacio de nombres `System` se usa para incluir la clase `TestClass`, por lo tanto, `global::System.Console` debe usarse para hacer referencia a la clase `System.Console`, que está oculta por el espacio de nombres `System`.</span><span class="sxs-lookup"><span data-stu-id="5bc46-118">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="5bc46-119">Además, el alias `colAlias` se usa para hacer referencia al espacio de nombres `System.Collections`; por lo tanto, la instancia de <xref:System.Collections.Hashtable?displayProperty=fullName> se ha creado con este alias en lugar del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5bc46-119">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=fullName> was created using this alias instead of the namespace.</span></span>  
  
 <span data-ttu-id="5bc46-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bc46-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span></span>  
  
 <span data-ttu-id="5bc46-121">**A 1**</span><span class="sxs-lookup"><span data-stu-id="5bc46-121">**A 1**</span></span>  
<span data-ttu-id="5bc46-122">**B 2**</span><span class="sxs-lookup"><span data-stu-id="5bc46-122">**B 2**</span></span>  
<span data-ttu-id="5bc46-123">**C 3**</span><span class="sxs-lookup"><span data-stu-id="5bc46-123">**C 3**</span></span>   
## <a name="see-also"></a><span data-ttu-id="5bc46-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bc46-124">See Also</span></span>  
 <span data-ttu-id="5bc46-125">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5bc46-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5bc46-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md)  (Espacios de nombres)</span><span class="sxs-lookup"><span data-stu-id="5bc46-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="5bc46-127">[. Operador](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5bc46-127">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="5bc46-128">[Operador ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="5bc46-128">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="5bc46-129">extern</span><span class="sxs-lookup"><span data-stu-id="5bc46-129">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

