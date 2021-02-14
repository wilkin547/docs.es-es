---
description: 'Más información acerca de: Instrucciones de diseño de tipos'
title: Instrucciones de diseño de tipos
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: d2c193d41dda118558cc5e7541f7e2dfbaf1a369
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641842"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="d51fe-103">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="d51fe-103">Type Design Guidelines</span></span>

<span data-ttu-id="d51fe-104">Desde la perspectiva de CLR, solo hay dos categorías de tipos (tipos de referencia y tipos de valor) pero para la finalidad de un debate sobre el diseño del marco, dividimos los tipos en grupos más lógicos, cada uno con sus propias reglas de diseño específicas.</span><span class="sxs-lookup"><span data-stu-id="d51fe-104">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>

 <span data-ttu-id="d51fe-105">Las clases son el caso general de los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d51fe-105">Classes are the general case of reference types.</span></span> <span data-ttu-id="d51fe-106">Componen la mayor parte de los tipos en la mayoría de los marcos.</span><span class="sxs-lookup"><span data-stu-id="d51fe-106">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="d51fe-107">Las clases deben su popularidad al amplio conjunto de características orientadas a objetos que admiten y a su aplicabilidad general.</span><span class="sxs-lookup"><span data-stu-id="d51fe-107">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="d51fe-108">Las clases base y las clases abstractas son grupos lógicos especiales relacionados con la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="d51fe-108">Base classes and abstract classes are special logical groups related to extensibility.</span></span>

 <span data-ttu-id="d51fe-109">Las interfaces son tipos que tanto los tipos de referencia como los tipos de valor pueden implementar.</span><span class="sxs-lookup"><span data-stu-id="d51fe-109">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="d51fe-110">Por tanto, pueden actuar como raíces de jerarquías polimórficas de tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="d51fe-110">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="d51fe-111">Además, las interfaces se pueden usar para simular la herencia múltiple, que no es compatible de forma nativa con CLR.</span><span class="sxs-lookup"><span data-stu-id="d51fe-111">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>

 <span data-ttu-id="d51fe-112">Los structs son el caso general de los tipos de valor y se deben reservar para tipos pequeños y simples, similares a los primitivos del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d51fe-112">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>

 <span data-ttu-id="d51fe-113">Las enumeraciones son un caso especial de tipos de valor que se usan para definir breves conjuntos de valores, como los días de la semana, los colores de la consola, etc.</span><span class="sxs-lookup"><span data-stu-id="d51fe-113">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>

 <span data-ttu-id="d51fe-114">Las clases estáticas son tipos diseñados para ser contenedores de miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="d51fe-114">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="d51fe-115">Normalmente se utilizan para proporcionar accesos directos a otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="d51fe-115">They are commonly used to provide shortcuts to other operations.</span></span>

 <span data-ttu-id="d51fe-116">Los delegados, las excepciones, los atributos, las matrices y las colecciones son casos especiales de tipos de referencia destinados a usos específicos, y las instrucciones para su diseño y uso se tratan en otra parte de este libro.</span><span class="sxs-lookup"><span data-stu-id="d51fe-116">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>

 <span data-ttu-id="d51fe-117">✔️ DEBE asegurarse de que cada tipo es un conjunto bien definido de miembros relacionados, no solo una colección aleatoria de funcionalidad no relacionada.</span><span class="sxs-lookup"><span data-stu-id="d51fe-117">✔️ DO ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d51fe-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d51fe-118">In This Section</span></span>

 <span data-ttu-id="d51fe-119">[Elegir entre clases y structs](choosing-between-class-and-struct.md) [Diseño de clases abstractas](abstract-class.md) [Diseño de clases estáticas](static-class.md) [Diseño de interfaces](interface.md) [Diseño de structs](struct.md) [Diseño de enumeraciones](enum.md) [Tipos anidados](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d51fe-119">[Choosing Between Class and Struct](choosing-between-class-and-struct.md) [Abstract Class Design](abstract-class.md) [Static Class Design](static-class.md) [Interface Design](interface.md) [Struct Design](struct.md) [Enum Design](enum.md) [Nested Types](nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d51fe-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d51fe-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d51fe-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d51fe-121">See also</span></span>

- [<span data-ttu-id="d51fe-122">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d51fe-122">Framework Design Guidelines</span></span>](index.md)
