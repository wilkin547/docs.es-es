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
ms.openlocfilehash: c01e041edbf30813c477e579867abb9099ce0528
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820857"
---
# <a name="naming-resources"></a>Asignar nombres a recursos
Dado que se puede hacer referencia a los recursos localizables a través de ciertos objetos como si fueran propiedades, las directrices de nomenclatura para los recursos son similares a las directrices de propiedad.

 ✔️ usar PascalCasing en las claves de recursos.

 ✔️ proporcionan identificadores descriptivos en lugar de cortos.

 ❌ No use palabras clave específicas del lenguaje de los principales lenguajes CLR.

 ✔️ usar solo caracteres alfanuméricos y caracteres de subrayado en los recursos de nomenclatura.

 ✔️ usar la siguiente Convención de nomenclatura para los recursos de mensajes de excepción.

 El identificador de recursos debe ser el nombre del tipo de excepción más un identificador corto de la excepción:

 `ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`
 `ArgumentExceptionFileNameIsMalformed`

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de nomenclatura](naming-guidelines.md)
