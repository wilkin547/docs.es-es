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
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "48260685"
---
# <a name="naming-resources"></a>Asignar nombres a recursos
Dado que los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de la propiedad.  
  
 **✓ DO** use Pascal de las claves de recursos.  
  
 **✓ DO** proporcionar descriptivo en lugar de identificadores cortos.  
  
 **X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.  
  
 **✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.  
  
 **✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.  
  
 El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
