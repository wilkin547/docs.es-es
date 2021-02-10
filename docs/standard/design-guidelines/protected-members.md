---
description: 'Más información acerca de: Miembros protegidos'
title: Miembros protegidos
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 5860828a5a469c77fbee001d01460a488fda4edf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731765"
---
# <a name="protected-members"></a><span data-ttu-id="6d90c-103">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="6d90c-103">Protected Members</span></span>

<span data-ttu-id="6d90c-104">Los miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero pueden aumentar la eficacia de la extensibilidad a través de la creación de subclases.</span><span class="sxs-lookup"><span data-stu-id="6d90c-104">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="6d90c-105">Se pueden usar para exponer opciones de personalización avanzadas sin complicar innecesariamente la interfaz pública principal.</span><span class="sxs-lookup"><span data-stu-id="6d90c-105">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="6d90c-106">Los diseñadores de marcos deben tener cuidado con los miembros protegidos, ya que el nombre "protegido" puede dar una falsa sensación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d90c-106">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="6d90c-107">Cualquier persona puede crear subclases de una clase no sellada y tener acceso a miembros protegidos, por lo que todas las mismas prácticas de codificación defensivas que se usan para los miembros públicos se aplican a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="6d90c-107">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="6d90c-108">✔️ CONSIDERE la posibilidad de usar miembros protegidos para la personalización avanzada.</span><span class="sxs-lookup"><span data-stu-id="6d90c-108">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="6d90c-109">✔️ TRATE los miembros protegidos de clases no selladas como públicos con fines de análisis de compatibilidad, documentación y seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d90c-109">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="6d90c-110">Cualquier persona puede heredar de una clase y obtener acceso a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="6d90c-110">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="6d90c-111">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="6d90c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6d90c-112">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="6d90c-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6d90c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d90c-113">See also</span></span>

- [<span data-ttu-id="6d90c-114">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d90c-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="6d90c-115">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="6d90c-115">Designing for Extensibility</span></span>](designing-for-extensibility.md)
