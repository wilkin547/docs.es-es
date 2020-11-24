---
title: Instrucciones de diseño de tipos
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: a20744f76433ff12456967e4d41d9a13b6f5d46c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677536"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="dd38d-102">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="dd38d-102">Type Design Guidelines</span></span>

<span data-ttu-id="dd38d-103">Desde la perspectiva de CLR, solo hay dos categorías de tipos: tipos de referencia y tipos de valor, pero para la finalidad de un debate sobre el diseño del marco, dividimos los tipos en grupos más lógicos, cada uno con sus propias reglas de diseño específicas.</span><span class="sxs-lookup"><span data-stu-id="dd38d-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>

 <span data-ttu-id="dd38d-104">Las clases son el caso general de los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dd38d-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="dd38d-105">Componen la mayor parte de los tipos en la mayoría de los marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dd38d-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="dd38d-106">Las clases deben tener su popularidad al amplio conjunto de características orientadas a objetos que admiten y a su aplicabilidad general.</span><span class="sxs-lookup"><span data-stu-id="dd38d-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="dd38d-107">Las clases base y las clases abstractas son grupos lógicos especiales relacionados con la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="dd38d-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>

 <span data-ttu-id="dd38d-108">Las interfaces son tipos que pueden ser implementados por tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="dd38d-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="dd38d-109">Por tanto, pueden actuar como raíces de jerarquías polimórficas de tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="dd38d-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="dd38d-110">Además, las interfaces se pueden usar para simular la herencia múltiple, que no es compatible de forma nativa con CLR.</span><span class="sxs-lookup"><span data-stu-id="dd38d-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>

 <span data-ttu-id="dd38d-111">Los Structs son el caso general de los tipos de valor y se deben reservar para tipos pequeños y simples, similares a los primitivos del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="dd38d-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>

 <span data-ttu-id="dd38d-112">Las enumeraciones son un caso especial de tipos de valor que se usan para definir breves conjuntos de valores, como los días de la semana, los colores de la consola, etc.</span><span class="sxs-lookup"><span data-stu-id="dd38d-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>

 <span data-ttu-id="dd38d-113">Las clases estáticas son tipos diseñados para ser contenedores de miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="dd38d-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="dd38d-114">Normalmente se utilizan para proporcionar accesos directos a otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="dd38d-114">They are commonly used to provide shortcuts to other operations.</span></span>

 <span data-ttu-id="dd38d-115">Los delegados, las excepciones, los atributos, las matrices y las colecciones son casos especiales de tipos de referencia destinados a usos específicos, y las instrucciones para su diseño y uso se tratan en otra parte de este libro.</span><span class="sxs-lookup"><span data-stu-id="dd38d-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>

 <span data-ttu-id="dd38d-116">✔️ asegurarse de que cada tipo es un conjunto bien definido de miembros relacionados, no solo una colección aleatoria de funcionalidad no relacionada.</span><span class="sxs-lookup"><span data-stu-id="dd38d-116">✔️ DO ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="dd38d-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dd38d-117">In This Section</span></span>

 <span data-ttu-id="dd38d-118">[Elección entre clase y struct clase](choosing-between-class-and-struct.md) [abstracta diseño](abstract-class.md) de clases [estáticas](static-class.md) [diseño](interface.md) de clases [estructura](struct.md) [Enum Design](enum.md) de diseño de clase [tipo anidado](nested-types.md) *partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="dd38d-118">[Choosing Between Class and Struct](choosing-between-class-and-struct.md) [Abstract Class Design](abstract-class.md) [Static Class Design](static-class.md) [Interface Design](interface.md) [Struct Design](struct.md) [Enum Design](enum.md) [Nested Types](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="dd38d-119">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="dd38d-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="dd38d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd38d-120">See also</span></span>

- [<span data-ttu-id="dd38d-121">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="dd38d-121">Framework Design Guidelines</span></span>](index.md)
