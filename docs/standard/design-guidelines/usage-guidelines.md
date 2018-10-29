---
title: Instrucciones de uso
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e583bf7768c60477effb6c1cf9b838ae4c8c182
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197943"
---
# <a name="usage-guidelines"></a>Instrucciones de uso

Esta sección contiene directrices para utilizar tipos comunes en las API accesibles públicamente. Trata de uso directo de tipos de marco (por ejemplo, los atributos de serialización) y la sobrecarga de operadores comunes integrados.
  
El <xref:System.IDisposable?displayProperty=nameWithType> interfaz no está cubierta en esta sección, pero se trata en el [patrón Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sección.

> [!NOTE]
> Para obtener directrices e información adicional sobre otro común, tipos integrados de .NET Framework, vea los temas de referencia para los siguientes elementos: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>En esta sección

[Matrices](arrays.md)  
[Atributos](attributes.md)  
[Colecciones](guidelines-for-collections.md)  
[Serialización](serialization.md)  
[Uso de System.Xml](system-xml-usage.md)  
[Operadores de igualdad](equality-operators.md)  

*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*

*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
