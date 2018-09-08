---
title: Miembros protegidos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199744"
---
# <a name="protected-members"></a><span data-ttu-id="5d80a-102">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="5d80a-102">Protected Members</span></span>
<span data-ttu-id="5d80a-103">Miembros protegidos por sí solos no proporcionan ninguna extensibilidad, pero puede hacer más eficaz extensibilidad a través de la creación de subclases.</span><span class="sxs-lookup"><span data-stu-id="5d80a-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="5d80a-104">Se puede usar para exponer las opciones de personalización avanzada sin complicar innecesariamente la principal interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="5d80a-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="5d80a-105">Los diseñadores de Framework deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5d80a-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="5d80a-106">Cualquier persona es capaz de subclase de una clase no sellada y los miembros acceso protegido y por lo que las mismas defensivas prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="5d80a-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="5d80a-107">**✓ CONSIDER** con protegidos los miembros para la personalización avanzada.</span><span class="sxs-lookup"><span data-stu-id="5d80a-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="5d80a-108">**✓ DO** trate los miembros protegidos de clases no selladas como públicos con el fin de análisis de seguridad, documentación y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="5d80a-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="5d80a-109">Cualquier persona puede heredar de una clase y tener acceso a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="5d80a-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="5d80a-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="5d80a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5d80a-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="5d80a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d80a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d80a-112">See also</span></span>

- [<span data-ttu-id="5d80a-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d80a-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="5d80a-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="5d80a-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
