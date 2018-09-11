---
title: 'Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: c15271abb55cb29a200185e4b512a76a4913d848
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44195184"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="690f3-102">Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="690f3-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="690f3-103">La capacidad de tener acceso a un miembro en el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) global es útil cuando el miembro puede estar oculto por otra entidad del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="690f3-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="690f3-104">Por ejemplo, en el código siguiente, `Console` se resuelve como `TestApp.Console` en lugar de como el tipo `Console` en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="690f3-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 <span data-ttu-id="690f3-105">Usar `System.Console` todavía provoca un error porque el espacio de nombres `System` está oculto mediante la clase `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="690f3-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 <span data-ttu-id="690f3-106">En cambio, puede solucionar este error con `global::System.Console`, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="690f3-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 <span data-ttu-id="690f3-107">Cuando el identificador izquierdo es `global`, la búsqueda del identificador derecho comienza en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="690f3-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="690f3-108">Por ejemplo, la siguiente declaración está haciendo referencia a `TestApp` como un miembro del espacio global.</span><span class="sxs-lookup"><span data-stu-id="690f3-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 <span data-ttu-id="690f3-109">Obviamente, no se recomienda crear sus propios espacios de nombres denominados `System`, y es poco probable que encuentre cualquier código donde haya ocurrido esto.</span><span class="sxs-lookup"><span data-stu-id="690f3-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="690f3-110">En cambio, en proyectos más grandes, es una posibilidad muy real que pueda producirse una duplicación de espacio de nombres de una forma u otra.</span><span class="sxs-lookup"><span data-stu-id="690f3-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="690f3-111">En estas situaciones, el calificador de espacio de nombres global es su garantía de que puede especificar el espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="690f3-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="690f3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="690f3-112">Example</span></span>  
 <span data-ttu-id="690f3-113">En este ejemplo, el espacio de nombres `System` se usa para incluir la clase `TestClass`, por lo tanto, `global::System.Console` debe usarse para hacer referencia a la clase `System.Console`, que está oculta por el espacio de nombres `System`.</span><span class="sxs-lookup"><span data-stu-id="690f3-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="690f3-114">Además, el alias `colAlias` se usa para hacer referencia al espacio de nombres `System.Collections`; por lo tanto, la instancia de <xref:System.Collections.Hashtable?displayProperty=nameWithType> se ha creado con este alias en lugar del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="690f3-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
<span data-ttu-id="690f3-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="690f3-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="690f3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="690f3-116">See Also</span></span>

- [<span data-ttu-id="690f3-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="690f3-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="690f3-118">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="690f3-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="690f3-119">. .</span><span class="sxs-lookup"><span data-stu-id="690f3-119">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="690f3-120">Operador ::</span><span class="sxs-lookup"><span data-stu-id="690f3-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="690f3-121">extern</span><span class="sxs-lookup"><span data-stu-id="690f3-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
