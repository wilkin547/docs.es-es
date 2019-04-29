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
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937402"
---
# <a name="protected-members"></a><span data-ttu-id="8207f-102">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="8207f-102">Protected Members</span></span>
<span data-ttu-id="8207f-103">Miembros protegidos por sí solos no proporcionan ninguna extensibilidad, pero puede hacer más eficaz extensibilidad a través de la creación de subclases.</span><span class="sxs-lookup"><span data-stu-id="8207f-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="8207f-104">Se puede usar para exponer las opciones de personalización avanzada sin complicar innecesariamente la principal interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="8207f-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="8207f-105">Los diseñadores de Framework deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8207f-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="8207f-106">Cualquier persona es capaz de subclase de una clase no sellada y los miembros acceso protegido y por lo que las mismas defensivas prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="8207f-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="8207f-107">**✓ CONSIDER** con protegidos los miembros para la personalización avanzada.</span><span class="sxs-lookup"><span data-stu-id="8207f-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="8207f-108">**✓ DO** trate los miembros protegidos de clases no selladas como públicos con el fin de análisis de seguridad, documentación y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="8207f-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="8207f-109">Cualquier persona puede heredar de una clase y tener acceso a los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="8207f-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="8207f-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="8207f-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8207f-111">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8207f-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8207f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8207f-112">See also</span></span>

- [<span data-ttu-id="8207f-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8207f-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="8207f-114">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="8207f-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
