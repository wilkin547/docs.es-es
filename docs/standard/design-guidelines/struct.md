---
title: Diseño de structs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dfa32112a2eb85a93cdd1e7a72d4411a3b197a1a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="struct-design"></a>Diseño de structs
El tipo de valor de uso general más a menudo se conoce como un struct, la palabra clave de C#. Esta sección proporciona instrucciones para el diseño de la estructura general.  
  
 **X DO NOT** proporcionar un constructor predeterminado para un struct.  
  
 Seguir esta directriz permite matrices de structs crearse sin tener que ejecutar el constructor en cada elemento de la matriz. Tenga en cuenta que C# no permite estructuras tengan constructores predeterminados.  
  
 **X DO NOT** definir tipos de valor mutable.  
  
 Tipos de valor mutable tienen varios problemas. Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia. Dado que la copia se crea implícitamente, los desarrolladores no sea consciente de que se Muta la copia y no el valor original. Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas al utilizar tipos de valor mutable porque incluso las variables locales, cuando se desreferencia, hacer una copia en realizarse.  
  
 **✓ HACER** asegurarse de que un estado donde todos los datos de la instancia se establece en cero, false o null (según corresponda) es válido.  
  
 Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de las estructuras.  
  
 **✓ HACER** implementar <xref:System.IEquatable%601> en tipos de valor.  
  
 El <xref:System.Object.Equals%2A?displayProperty=nameWithType> método en tipos de valor provoca conversión boxing y la implementación predeterminada no es muy eficaz, ya que usa la reflexión. <xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no producirá la conversión boxing.  
  
 **X DO NOT** extender explícitamente <xref:System.ValueType>. De hecho, la mayoría de los lenguajes evitar esto.  
  
 En general, las estructuras pueden ser muy útiles, pero solo deben usarse para los valores pequeños, únicos e inmutable que no se realizar la conversión boxing con frecuencia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Elección entre clase y estructura](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
