---
title: 'Cómo: Acceder a un miembro con un puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200356"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="52b22-102">Cómo: Acceder a un miembro con un puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="52b22-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="52b22-103">Para tener acceso a un miembro de un struct que se declara en un contexto no seguro, puede usar el operador de acceso a miembros, como se muestra en el ejemplo siguiente en el que `p` es un puntero a un [struct](../../../csharp/language-reference/keywords/struct.md) que contiene un miembro `x`.</span><span class="sxs-lookup"><span data-stu-id="52b22-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="52b22-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52b22-104">Example</span></span>  
 <span data-ttu-id="52b22-105">En este ejemplo, se declara un [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, que contiene dos coordenadas `x` e `y` y se crean instancias de la misma.</span><span class="sxs-lookup"><span data-stu-id="52b22-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="52b22-106">Usando el operador de acceso a miembros `->` y un puntero a la instancia `home`, se asignan valores a `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="52b22-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52b22-107">Tenga en cuenta que la expresión `p->x` es equivalente a la expresión `(*p).x`, y puede obtener el mismo resultado con cualquiera de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="52b22-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="52b22-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="52b22-108">See also</span></span>

- [<span data-ttu-id="52b22-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="52b22-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="52b22-110">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="52b22-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="52b22-111">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="52b22-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="52b22-112">Tipos</span><span class="sxs-lookup"><span data-stu-id="52b22-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="52b22-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="52b22-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="52b22-114">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="52b22-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="52b22-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="52b22-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
