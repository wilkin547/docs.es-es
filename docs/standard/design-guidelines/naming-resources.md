---
title: Asignar nombres a recursos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b100366952b1f536d187eb72c6d80c86bb3e572e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="naming-resources"></a><span data-ttu-id="0617e-102">Asignar nombres a recursos</span><span class="sxs-lookup"><span data-stu-id="0617e-102">Naming Resources</span></span>
<span data-ttu-id="0617e-103">Porque los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las instrucciones de nomenclatura para los recursos son similares a las directrices de propiedad.</span><span class="sxs-lookup"><span data-stu-id="0617e-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="0617e-104">**✓ HACER** use Pascal de las claves de recursos.</span><span class="sxs-lookup"><span data-stu-id="0617e-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="0617e-105">**✓ HACER** proporcionar descriptivo en lugar de identificadores cortos.</span><span class="sxs-lookup"><span data-stu-id="0617e-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="0617e-106">**X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.</span><span class="sxs-lookup"><span data-stu-id="0617e-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="0617e-107">**✓ HACER** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.</span><span class="sxs-lookup"><span data-stu-id="0617e-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="0617e-108">**✓ HACER** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0617e-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="0617e-109">El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:</span><span class="sxs-lookup"><span data-stu-id="0617e-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="0617e-110">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="0617e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0617e-111">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0617e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0617e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0617e-112">See Also</span></span>  
 [<span data-ttu-id="0617e-113">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0617e-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0617e-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0617e-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
