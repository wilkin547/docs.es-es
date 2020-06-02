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
ms.openlocfilehash: 762ba99c4751ba40f5f33e99455cf950af35cdf6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290154"
---
# <a name="naming-resources"></a><span data-ttu-id="d117e-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="d117e-102">Naming Resources</span></span>
<span data-ttu-id="d117e-103">Dado que se puede hacer referencia a los recursos localizables a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d117e-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="d117e-104">✔️ usar PascalCasing en las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="d117e-104">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="d117e-105">✔️ proporcionan identificadores descriptivos en lugar de cortos.</span><span class="sxs-lookup"><span data-stu-id="d117e-105">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="d117e-106">❌No use palabras clave específicas del lenguaje de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="d117e-106">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="d117e-107">✔️ usar solo caracteres alfanuméricos y caracteres de subrayado en los recursos de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="d117e-107">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="d117e-108">✔️ usar la siguiente Convención de nomenclatura para los recursos de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="d117e-108">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="d117e-109">El identificador de recursos debe ser el nombre del tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="d117e-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="d117e-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="d117e-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="d117e-111">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d117e-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d117e-112">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="d117e-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d117e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d117e-113">See also</span></span>

- [<span data-ttu-id="d117e-114">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="d117e-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d117e-115">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="d117e-115">Naming Guidelines</span></span>](naming-guidelines.md)
