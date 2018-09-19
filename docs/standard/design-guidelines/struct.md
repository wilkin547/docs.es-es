---
title: Diseño de structs
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46324625"
---
# <a name="struct-design"></a>Diseño de structs
El tipo de valor de uso general más a menudo se conoce como una estructura, su palabra clave de C#. Esta sección proporciona instrucciones para el diseño de la estructura general.  
  
 **X DO NOT** proporcionar un constructor predeterminado para un struct.  
  
 Seguir esta directriz permite que las matrices de structs crearse sin tener que ejecutar el constructor en cada elemento de la matriz. Tenga en cuenta que C# no permite que las estructuras tienen constructores predeterminados.  
  
 **X DO NOT** definir tipos de valor mutable.  
  
 Tipos de valor mutable tienen varios problemas. Por ejemplo, un captador de propiedad que devuelve un tipo de valor, el llamador recibe una copia. Dado que la copia se crea implícitamente, los desarrolladores podrían no ser consciente de que son una mutación de la copia y no el valor original. Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas con los tipos de valor mutable porque incluso las variables locales, cuando se desreferencia, hacer una copia en realizarse.  
  
 **✓ DO** asegurarse de que un estado donde todos los datos de la instancia se establece en cero, false o null (según corresponda) es válido.  
  
 Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de las estructuras.  
  
 **✓ DO** implementar <xref:System.IEquatable%601> en tipos de valor.  
  
 El <xref:System.Object.Equals%2A?displayProperty=nameWithType> boxing hace que el método en tipos de valor y su implementación predeterminada no es muy eficaz, porque usa la reflexión. <xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no provocará la conversión boxing.  
  
 **X DO NOT** extender explícitamente <xref:System.ValueType>. De hecho, la mayoría de los lenguajes evitar esto.  
  
 En general, los structs pueden ser muy útiles pero solo debe usarse para valores pequeños, únicos, inmutable que no se copia por boxing con frecuencia.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Elección entre clase y estructura](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
