---
title: Miembros protegidos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 44d342662e1aaeb51f14470f354f2dadd9a6f18d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743650"
---
# <a name="protected-members"></a><span data-ttu-id="c0e1c-102">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="c0e1c-102">Protected Members</span></span>
<span data-ttu-id="c0e1c-103">Los miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero pueden realizar la extensibilidad mediante subclases más eficaces.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="c0e1c-104">Se pueden usar para exponer opciones de personalización avanzadas sin complicar innecesariamente la interfaz pública principal.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="c0e1c-105">Los diseñadores de Marcos deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una sensación falsa de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="c0e1c-106">Cualquier persona puede subclase de una clase no sellada y tener acceso a miembros protegidos, por lo que todas las mismas prácticas de codificación defensivas que se usan para los miembros públicos se aplican a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="c0e1c-107">✔️ considere la posibilidad de usar miembros protegidos para la personalización avanzada.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-107">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="c0e1c-108">✔️ tratar los miembros protegidos de clases no selladas como públicos con el fin de la seguridad, la documentación y el análisis de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-108">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="c0e1c-109">Cualquier persona puede heredar de una clase y obtener acceso a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="c0e1c-109">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="c0e1c-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="c0e1c-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c0e1c-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="c0e1c-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c0e1c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0e1c-112">See also</span></span>

- [<span data-ttu-id="c0e1c-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0e1c-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c0e1c-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="c0e1c-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
