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
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497610"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
