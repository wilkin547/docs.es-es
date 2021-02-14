---
description: 'Más información acerca de: Diseño de structs'
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
ms.openlocfilehash: a28dd3e452d22e61d95ec521fdbde6539e38ed78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641907"
---
# <a name="struct-design"></a>Diseño de structs

Normalmente, el tipo de valor de uso general se conoce como struct, su palabra clave en C#. En esta sección se proporcionan instrucciones para el diseño de estructuras generales.

 ❌ NO proporcione un constructor sin parámetros para un struct.

 La siguiente instrucción permite crear matrices de structs sin tener que ejecutar el constructor en cada elemento de la matriz. Tenga en cuenta que C# no permite que los structs tengan constructores sin parámetros.

 ❌ NO defina tipos de valores mutables.

 Los tipos de valores mutables tienen varios problemas. Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia. Dado que la copia se crea implícitamente, es posible que los desarrolladores no sean conscientes de que están mutando la copia y no el valor original. Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas al usar tipos de valores mutables porque incluso las variables locales, cuando se desreferencian, provocan una copia.

 ✔️ DEBE asegurarse de que el estado donde todos los datos de instancia están establecidos en cero, falso o null (según corresponda) es válido.

 Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de structs.

 ✔️ DEBE implementar <xref:System.IEquatable%601> en tipos de valor.

 El método <xref:System.Object.Equals%2A?displayProperty=nameWithType> en tipos de valor produce la conversión boxing y su implementación predeterminada no es muy eficaz, ya que utiliza la reflexión. <xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no cause la conversión boxing.

 ❌ NO extienda explícitamente <xref:System.ValueType>. De hecho, la mayoría de los lenguajes lo impiden.

 En general, los structs pueden ser muy útiles, pero solo se deben usar para los valores pequeños, únicos e inmutables a los que no se les aplicará la conversión boxing con frecuencia.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](type.md)
- [Instrucciones de diseño de .NET Framework](index.md)
- [Elegir entre clases y structs](choosing-between-class-and-struct.md)
