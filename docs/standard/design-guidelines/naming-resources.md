---
title: Asignar nombres a recursos
description: Revise las directrices de nomenclatura de los recursos en .NET, que son similares a las directrices para asignar nombres a las propiedades.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 08046fb78638546b3dcab856674424c92c03fe83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706416"
---
# <a name="naming-resources"></a><span data-ttu-id="38ed9-103">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="38ed9-103">Naming Resources</span></span>

<span data-ttu-id="38ed9-104">Dado que se puede hacer referencia a los recursos localizables a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de propiedad.</span><span class="sxs-lookup"><span data-stu-id="38ed9-104">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="38ed9-105">✔️ usar PascalCasing en las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="38ed9-105">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="38ed9-106">✔️ proporcionan identificadores descriptivos en lugar de cortos.</span><span class="sxs-lookup"><span data-stu-id="38ed9-106">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="38ed9-107">❌ No use palabras clave específicas del lenguaje de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="38ed9-107">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="38ed9-108">✔️ usar solo caracteres alfanuméricos y caracteres de subrayado en los recursos de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="38ed9-108">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="38ed9-109">✔️ usar la siguiente Convención de nomenclatura para los recursos de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="38ed9-109">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="38ed9-110">El identificador de recursos debe ser el nombre del tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="38ed9-110">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="38ed9-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="38ed9-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="38ed9-112">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="38ed9-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="38ed9-113">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="38ed9-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="38ed9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38ed9-114">See also</span></span>

- [<span data-ttu-id="38ed9-115">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="38ed9-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="38ed9-116">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="38ed9-116">Naming Guidelines</span></span>](naming-guidelines.md)
