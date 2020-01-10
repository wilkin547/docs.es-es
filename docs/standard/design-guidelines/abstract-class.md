---
title: Diseño de clases abstractas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709600"
---
# <a name="abstract-class-design"></a><span data-ttu-id="bc3f4-102">Diseño de clases abstractas</span><span class="sxs-lookup"><span data-stu-id="bc3f4-102">Abstract Class Design</span></span>
<span data-ttu-id="bc3f4-103">**X DO NOT** definir constructores internos públicos o protegidos en tipos abstractos.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="bc3f4-104">Los constructores solo deben ser públicos si los usuarios deben crear instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="bc3f4-105">Dado que no se pueden crear instancias de un tipo abstracto, un tipo abstracto con un constructor público se ha diseñado incorrectamente y puede inducir a error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="bc3f4-106">**✓ DO** definir un constructor interno o protegidos en las clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="bc3f4-107">Un constructor protegido es más común y simplemente permite que la clase base realice su propia inicialización cuando se creen subtipos.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="bc3f4-108">Se puede usar un constructor interno para limitar las implementaciones concretas de la clase abstracta al ensamblado que define la clase.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="bc3f4-109">**✓ DO** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="bc3f4-110">Esto ayuda a validar el diseño de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="bc3f4-111">Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la clase abstracta <xref:System.IO.Stream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bc3f4-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="bc3f4-112">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="bc3f4-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bc3f4-113">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="bc3f4-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3f4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc3f4-114">See also</span></span>

- [<span data-ttu-id="bc3f4-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="bc3f4-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="bc3f4-116">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc3f4-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
