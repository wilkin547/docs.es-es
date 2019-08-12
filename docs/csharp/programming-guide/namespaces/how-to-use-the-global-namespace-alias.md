---
title: 'Procedimiento Utilizar el alias del espacio de nombres global: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796281"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="3f07f-102">Procedimiento Utilizar el alias del espacio de nombres global (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3f07f-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="3f07f-103">La capacidad de tener acceso a un miembro en el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) global es útil cuando el miembro puede estar oculto por otra entidad del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="3f07f-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="3f07f-104">Por ejemplo, en el código siguiente, `Console` se resuelve como `TestApp.Console` en lugar de como el tipo `Console` en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="3f07f-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="3f07f-105">Usar `System.Console` todavía provoca un error porque el espacio de nombres `System` está oculto mediante la clase `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="3f07f-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="3f07f-106">En cambio, puede solucionar este error con `global::System.Console`, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="3f07f-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="3f07f-107">Cuando el identificador izquierdo es `global`, la búsqueda del identificador derecho comienza en el espacio de nombres global.</span><span class="sxs-lookup"><span data-stu-id="3f07f-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="3f07f-108">Por ejemplo, la siguiente declaración está haciendo referencia a `TestApp` como un miembro del espacio global.</span><span class="sxs-lookup"><span data-stu-id="3f07f-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="3f07f-109">Obviamente, no se recomienda crear sus propios espacios de nombres denominados `System`, y es poco probable que encuentre cualquier código donde haya ocurrido esto.</span><span class="sxs-lookup"><span data-stu-id="3f07f-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="3f07f-110">En cambio, en proyectos más grandes, es una posibilidad muy real que pueda producirse una duplicación de espacio de nombres de una forma u otra.</span><span class="sxs-lookup"><span data-stu-id="3f07f-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="3f07f-111">En estas situaciones, el calificador de espacio de nombres global es su garantía de que puede especificar el espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="3f07f-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f07f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f07f-112">See also</span></span>

- [<span data-ttu-id="3f07f-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3f07f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3f07f-114">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="3f07f-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="3f07f-115">:: !</span><span class="sxs-lookup"><span data-stu-id="3f07f-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="3f07f-116">extern</span><span class="sxs-lookup"><span data-stu-id="3f07f-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
