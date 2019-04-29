---
title: Diseño de structs
ms.date: 10/22/2008
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
author: KrzysztofCwalina
ms.openlocfilehash: cc5b8d7effda31b0236477b217bccf5cf2137f8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650146"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Elección entre clase y estructura](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
