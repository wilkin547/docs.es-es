---
title: Asignar nombres a recursos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709171"
---
# <a name="naming-resources"></a><span data-ttu-id="be4e5-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="be4e5-102">Naming Resources</span></span>
<span data-ttu-id="be4e5-103">Dado que se puede hacer referencia a los recursos localizables a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de propiedad.</span><span class="sxs-lookup"><span data-stu-id="be4e5-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="be4e5-104">**✓ DO** use Pascal de las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="be4e5-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="be4e5-105">**✓ DO** proporcionar descriptivo en lugar de identificadores cortos.</span><span class="sxs-lookup"><span data-stu-id="be4e5-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="be4e5-106">**X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="be4e5-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="be4e5-107">**✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.</span><span class="sxs-lookup"><span data-stu-id="be4e5-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="be4e5-108">**✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="be4e5-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="be4e5-109">El identificador de recursos debe ser el nombre del tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="be4e5-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="be4e5-110">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="be4e5-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="be4e5-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="be4e5-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4e5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="be4e5-112">See also</span></span>

- [<span data-ttu-id="be4e5-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be4e5-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="be4e5-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="be4e5-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
