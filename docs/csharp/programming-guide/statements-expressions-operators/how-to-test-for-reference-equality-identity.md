---
title: 'Procedimiento Probar la igualdad de referencias (identidad): Guía de programación de C#'
description: Aprenda a probar la igualdad de referencia (Identidad). Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 1d1a0e5d80ac8d2a689e75acbc6099b92e16f23f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151446"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="94755-104">Procedimiento Probar la igualdad de referencias (identidad) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="94755-104">How to test for reference equality (Identity) (C# Programming Guide)</span></span>

<span data-ttu-id="94755-105">No tiene que implementar ninguna lógica personalizada para admitir las comparaciones de igualdad de referencias en los tipos.</span><span class="sxs-lookup"><span data-stu-id="94755-105">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="94755-106">Esta funcionalidad se proporciona para todos los tipos mediante el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> estático.</span><span class="sxs-lookup"><span data-stu-id="94755-106">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="94755-107">En el ejemplo siguiente, se muestra cómo determinar si dos variables tienen *igualdad de referencia*, lo que significa que hacen referencia al mismo objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="94755-107">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="94755-108">En el ejemplo también se muestra por qué <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> siempre devuelve `false` para los tipos de valor y por qué no se debe usar <xref:System.Object.ReferenceEquals%2A> para determinar la igualdad entre cadenas.</span><span class="sxs-lookup"><span data-stu-id="94755-108">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94755-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94755-109">Example</span></span>  

 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 <span data-ttu-id="94755-110">La implementación de `Equals` en la clase base universal <xref:System.Object?displayProperty=nameWithType> también realiza una comprobación de la igualdad de referencias; sin embargo, es mejor no seguir este procedimiento porque, en el caso de que una clase invalide el método, los resultados podrían no ser los esperados.</span><span class="sxs-lookup"><span data-stu-id="94755-110">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="94755-111">Lo mismo se cumple para los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="94755-111">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="94755-112">Cuando se usan en tipos de referencia, el comportamiento predeterminado de `==` y `!=` consiste en realizar una comprobación de la igualdad de referencias.</span><span class="sxs-lookup"><span data-stu-id="94755-112">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="94755-113">Sin embargo, las clases derivadas pueden sobrecargar el operador para realizar una comprobación de la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="94755-113">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="94755-114">Para minimizar las posibilidades de error, lo mejor es usar siempre <xref:System.Object.ReferenceEquals%2A> cuando deba determinarse si dos objetos tienen igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="94755-114">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="94755-115">El runtime siempre aplica el método Intern a las cadenas constantes dentro del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94755-115">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="94755-116">Es decir, solo se conserva una instancia de cada cadena literal única.</span><span class="sxs-lookup"><span data-stu-id="94755-116">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="94755-117">Sin embargo, el runtime no garantiza que se vaya a aplicar el método Intern a las cadenas creadas en tiempo de ejecución, ni tampoco que dicho método se aplique a dos cadenas constantes iguales en distintos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="94755-117">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94755-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94755-118">See also</span></span>

- [<span data-ttu-id="94755-119">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="94755-119">Equality Comparisons</span></span>](./equality-comparisons.md)
