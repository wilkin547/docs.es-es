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
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756889"
---
# <a name="naming-resources"></a><span data-ttu-id="83b64-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="83b64-102">Naming Resources</span></span>
<span data-ttu-id="83b64-103">Dado que los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="83b64-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="83b64-104">**✓ DO** use Pascal de las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="83b64-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="83b64-105">**✓ DO** proporcionar descriptivo en lugar de identificadores cortos.</span><span class="sxs-lookup"><span data-stu-id="83b64-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="83b64-106">**X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="83b64-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="83b64-107">**✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.</span><span class="sxs-lookup"><span data-stu-id="83b64-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="83b64-108">**✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="83b64-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="83b64-109">El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="83b64-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="83b64-110">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="83b64-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="83b64-111">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="83b64-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b64-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b64-112">See also</span></span>

- [<span data-ttu-id="83b64-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83b64-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="83b64-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="83b64-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
