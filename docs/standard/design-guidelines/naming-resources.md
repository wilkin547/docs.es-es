---
title: Asignar nombres a recursos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186180"
---
# <a name="naming-resources"></a><span data-ttu-id="7efa8-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="7efa8-102">Naming Resources</span></span>
<span data-ttu-id="7efa8-103">Dado que los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7efa8-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="7efa8-104">**✓ DO** use Pascal de las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="7efa8-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="7efa8-105">**✓ DO** proporcionar descriptivo en lugar de identificadores cortos.</span><span class="sxs-lookup"><span data-stu-id="7efa8-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="7efa8-106">**X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="7efa8-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="7efa8-107">**✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.</span><span class="sxs-lookup"><span data-stu-id="7efa8-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="7efa8-108">**✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="7efa8-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="7efa8-109">El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="7efa8-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="7efa8-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="7efa8-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7efa8-111">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="7efa8-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7efa8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7efa8-112">See also</span></span>

- [<span data-ttu-id="7efa8-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7efa8-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="7efa8-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="7efa8-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
