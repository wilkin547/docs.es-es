---
title: "Cómo: Probar la igualdad de referencias (identidad) (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2dbbd7c0e5ebb507ca3dda0f248d9f1c8f9595fe
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="3e3df-102">Cómo: Probar la igualdad de referencias (identidad) (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3e3df-102">How to: Test for Reference Equality (Identity) (C# Programming Guide)</span></span>
<span data-ttu-id="3e3df-103">No tiene que implementar ninguna lógica personalizada para admitir las comparaciones de igualdad de referencias en los tipos.</span><span class="sxs-lookup"><span data-stu-id="3e3df-103">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="3e3df-104">Esta funcionalidad se proporciona para todos los tipos mediante el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> estático.</span><span class="sxs-lookup"><span data-stu-id="3e3df-104">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3e3df-105">En el ejemplo siguiente, se muestra cómo determinar si dos variables tienen *igualdad de referencia*, lo que significa que hacen referencia al mismo objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="3e3df-105">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="3e3df-106">En el ejemplo también se muestra por qué <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> siempre devuelve `false` para los tipos de valor y por qué no se debe usar <xref:System.Object.ReferenceEquals%2A> para determinar la igualdad entre cadenas.</span><span class="sxs-lookup"><span data-stu-id="3e3df-106">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e3df-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e3df-107">Example</span></span>  
 [!code-csharp[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 <span data-ttu-id="3e3df-108">La implementación de `Equals` en la clase base universal <xref:System.Object?displayProperty=nameWithType> también realiza una comprobación de la igualdad de referencias; sin embargo, es mejor no seguir este procedimiento porque, en el caso de que una clase invalide el método, los resultados podrían no ser los esperados.</span><span class="sxs-lookup"><span data-stu-id="3e3df-108">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="3e3df-109">Lo mismo se cumple para los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="3e3df-109">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="3e3df-110">Cuando se usan en tipos de referencia, el comportamiento predeterminado de == y `!=` consiste en realizar una comprobación de la igualdad de referencias.</span><span class="sxs-lookup"><span data-stu-id="3e3df-110">When they are operating on reference types, the default behavior of == and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="3e3df-111">Sin embargo, las clases derivadas pueden sobrecargar el operador para realizar una comprobación de la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="3e3df-111">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="3e3df-112">Para minimizar las posibilidades de error, lo mejor es usar siempre <xref:System.Object.ReferenceEquals%2A> cuando deba determinarse si dos objetos tienen igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="3e3df-112">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="3e3df-113">El runtime siempre aplica el método Intern a las cadenas constantes dentro del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3e3df-113">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="3e3df-114">Es decir, solo se conserva una instancia de cada cadena literal única.</span><span class="sxs-lookup"><span data-stu-id="3e3df-114">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="3e3df-115">Sin embargo, el runtime no garantiza que se vaya a aplicar el método Intern a las cadenas creadas en tiempo de ejecución, ni tampoco que dicho método se aplique a dos cadenas constantes iguales en distintos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3e3df-115">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3df-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e3df-116">See Also</span></span>  
 [<span data-ttu-id="3e3df-117">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="3e3df-117">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)
