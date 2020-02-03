---
title: Operadores de igualdad
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741695"
---
# <a name="equality-operators"></a><span data-ttu-id="1097a-102">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="1097a-102">Equality Operators</span></span>
<span data-ttu-id="1097a-103">En esta sección se describe la sobrecarga de los operadores de igualdad y se hace referencia a `operator==` y `operator!=` como operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1097a-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="1097a-104">❌ no sobrecargan uno de los operadores de igualdad y no el otro.</span><span class="sxs-lookup"><span data-stu-id="1097a-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="1097a-105">✔️ Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y características de rendimiento similares.</span><span class="sxs-lookup"><span data-stu-id="1097a-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="1097a-106">Esto suele significar que `Object.Equals` debe invalidarse cuando se sobrecargan los operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1097a-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="1097a-107">❌ evitar que se inicien excepciones desde operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1097a-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="1097a-108">Por ejemplo, devuelve false si uno de los argumentos es null en lugar de producir `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="1097a-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="1097a-109">Operadores de igualdad en tipos de valor</span><span class="sxs-lookup"><span data-stu-id="1097a-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="1097a-110">✔️ sobrecargan los operadores de igualdad en los tipos de valor, si la igualdad es significativa.</span><span class="sxs-lookup"><span data-stu-id="1097a-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="1097a-111">En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="1097a-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="1097a-112">Operadores de igualdad en tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="1097a-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="1097a-113">❌ evitar la sobrecarga de operadores de igualdad en tipos de referencia mutable.</span><span class="sxs-lookup"><span data-stu-id="1097a-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="1097a-114">Muchos lenguajes tienen operadores de igualdad integrados para los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1097a-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="1097a-115">Los operadores integrados normalmente implementan la igualdad de referencia y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado a la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="1097a-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="1097a-116">Este problema se mitiga en los tipos de referencia inmutables porque la inmutabilidad dificulta la diferencia entre la igualdad de referencia y la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="1097a-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="1097a-117">❌ evitar la sobrecarga de operadores de igualdad en tipos de referencia si la implementación sería significativamente más lenta que la de igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="1097a-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="1097a-118">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1097a-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1097a-119">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1097a-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1097a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1097a-120">See also</span></span>

- [<span data-ttu-id="1097a-121">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1097a-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="1097a-122">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="1097a-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
