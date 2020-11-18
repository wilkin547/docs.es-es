---
title: Operadores de igualdad
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 85a9e81d28995229e6b47d7fe4d0b541265999f8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821351"
---
# <a name="equality-operators"></a><span data-ttu-id="8dbc7-102">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="8dbc7-102">Equality Operators</span></span>
<span data-ttu-id="8dbc7-103">En esta sección se describe la sobrecarga de los operadores de igualdad y se hace referencia a `operator==` y `operator!=` como operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="8dbc7-104">❌ No sobrecargue uno de los operadores de igualdad y no el otro.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="8dbc7-105">✔️ Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y características de rendimiento similares.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="8dbc7-106">Esto suele significar que `Object.Equals` se debe invalidar Cuando se sobrecargan los operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="8dbc7-107">❌ Evite iniciar excepciones desde operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="8dbc7-108">Por ejemplo, devuelve false si uno de los argumentos es null en lugar de producirse `NullReferenceException` .</span><span class="sxs-lookup"><span data-stu-id="8dbc7-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="8dbc7-109">Operadores de igualdad en tipos de valor</span><span class="sxs-lookup"><span data-stu-id="8dbc7-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="8dbc7-110">✔️ sobrecargan los operadores de igualdad en los tipos de valor, si la igualdad es significativa.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="8dbc7-111">En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="8dbc7-112">Operadores de igualdad en tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="8dbc7-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="8dbc7-113">❌ Evite sobrecargar los operadores de igualdad en tipos de referencia mutable.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="8dbc7-114">Muchos lenguajes tienen operadores de igualdad integrados para los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="8dbc7-115">Los operadores integrados normalmente implementan la igualdad de referencia y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado a la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="8dbc7-116">Este problema se mitiga en los tipos de referencia inmutables porque la inmutabilidad dificulta la diferencia entre la igualdad de referencia y la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="8dbc7-117">❌ Evite sobrecargar los operadores de igualdad en los tipos de referencia si la implementación sería significativamente más lenta que la de igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="8dbc7-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="8dbc7-118">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="8dbc7-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8dbc7-119">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="8dbc7-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8dbc7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dbc7-120">See also</span></span>

- [<span data-ttu-id="8dbc7-121">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="8dbc7-121">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="8dbc7-122">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="8dbc7-122">Usage Guidelines</span></span>](usage-guidelines.md)
