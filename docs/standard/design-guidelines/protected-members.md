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
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571090"
---
# <a name="protected-members"></a><span data-ttu-id="edd93-102">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="edd93-102">Protected Members</span></span>
<span data-ttu-id="edd93-103">Miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero puede hacer más eficaz extensibilidad a través de la creación de subclases.</span><span class="sxs-lookup"><span data-stu-id="edd93-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="edd93-104">Puede utilizar para exponer las opciones de personalización avanzada sin complicar innecesariamente la principal interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="edd93-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="edd93-105">Diseñadores de Framework hay que tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="edd93-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="edd93-106">Cualquier persona es capaz de subclase de una clase no sellada y protegidos de obtener acceso a miembros y, por lo que las mismas estable prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="edd93-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="edd93-107">**✓ CONSIDER** con protegidos los miembros para la personalización avanzada.</span><span class="sxs-lookup"><span data-stu-id="edd93-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="edd93-108">**✓ DO** trate los miembros protegidos de clases no selladas como públicos con el fin de análisis de seguridad, documentación y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="edd93-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="edd93-109">Cualquiera puede heredar de una clase y tener acceso a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="edd93-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="edd93-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="edd93-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="edd93-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="edd93-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd93-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="edd93-112">See Also</span></span>  
 [<span data-ttu-id="edd93-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="edd93-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="edd93-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="edd93-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
