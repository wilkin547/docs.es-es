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
# <a name="naming-resources"></a>Asignar nombres a recursos
Dado que se puede hacer referencia a los recursos localizables a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de propiedad.  
  
 **✓ DO** use Pascal de las claves de recursos.  
  
 **✓ DO** proporcionar descriptivo en lugar de identificadores cortos.  
  
 **X DO NOT** usar palabras clave específicas del idioma de los principales lenguajes CLR.  
  
 **✓ DO** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.  
  
 **✓ DO** usar la siguiente convención de nomenclatura para los recursos de mensaje de excepción.  
  
 El identificador de recursos debe ser el nombre del tipo de excepción más un identificador corto de la excepción:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
