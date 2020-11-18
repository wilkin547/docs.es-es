---
title: Diseño de structs
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: da831d1477b451131bb27372d65ad7229fcf3f77
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828626"
---
# <a name="struct-design"></a>Diseño de structs
Normalmente, el tipo de valor de uso general se conoce como struct, su palabra clave de C#. En esta sección se proporcionan instrucciones para el diseño de estructuras generales.

 ❌ NO proporcione un constructor sin parámetros para un struct.

 La siguiente instrucción permite crear matrices de Structs sin tener que ejecutar el constructor en cada elemento de la matriz. Observe que C# no permite que los Structs tengan constructores sin parámetros.

 ❌ NO defina tipos de valores mutables.

 Los tipos de valores mutables tienen varios problemas. Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia. Dado que la copia se crea implícitamente, es posible que los desarrolladores no sepan que están mutando la copia y no el valor original. Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas al usar tipos de valores mutables porque incluso las variables locales, cuando se desreferencian, hacen que se realice una copia.

 ✔️ asegurarse de que el estado de todos los datos de instancia se establece en cero, falso o null (según corresponda) es válido.

 Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de estructuras.

 ✔️ implementar <xref:System.IEquatable%601> en tipos de valor.

 El <xref:System.Object.Equals%2A?displayProperty=nameWithType> método en los tipos de valor produce la conversión boxing y su implementación predeterminada no es muy eficaz, ya que utiliza la reflexión. <xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no cause la conversión boxing.

 ❌ NO se extiende explícitamente <xref:System.ValueType> . De hecho, la mayoría de los lenguajes lo impiden.

 En general, los Structs pueden ser muy útiles, pero solo se deben usar para los valores pequeños, únicos e inmutables a los que no se les aplicará la conversión boxing con frecuencia.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](type.md)
- [Directrices de diseño de marco](index.md)
- [Elegir entre clases y structs](choosing-between-class-and-struct.md)
