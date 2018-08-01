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
ms.openlocfilehash: b7cfda4e6a340d040de02903b9b64f0339751c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571191"
---
# <a name="naming-resources"></a><span data-ttu-id="74876-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="74876-102">Naming Resources</span></span>
<span data-ttu-id="74876-103">Porque los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las instrucciones de nomenclatura para los recursos son similares a las directrices de propiedad.</span><span class="sxs-lookup"><span data-stu-id="74876-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="74876-104">**✓ DO** use Pascal de las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="74876-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="74876-105">**✓ DO** proporcionar descriptivo en lugar de identificadores cortos.</span><span class="sxs-lookup"><span data-stu-id="74876-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="74876-106">**X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="74876-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="74876-107">**✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.</span><span class="sxs-lookup"><span data-stu-id="74876-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="74876-108">**✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="74876-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="74876-109">El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="74876-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="74876-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="74876-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="74876-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="74876-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74876-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="74876-112">See Also</span></span>  
 [<span data-ttu-id="74876-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74876-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="74876-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="74876-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
