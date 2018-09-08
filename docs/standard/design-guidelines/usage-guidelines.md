---
title: Instrucciones de uso
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04e44a6b58fd334b6a23e113922b980f69de627b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198652"
---
# <a name="usage-guidelines"></a>Instrucciones de uso

Esta sección contiene directrices para utilizar tipos comunes en las API accesibles públicamente. Trata de uso directo de tipos de marco (por ejemplo, los atributos de serialización) y la sobrecarga de operadores comunes integrados.
  
El <xref:System.IDisposable?displayProperty=nameWithType> interfaz no está cubierta en esta sección, pero se trata en el [patrón Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sección.

> [!NOTE]
> Para instrucciones detalladas e información adicional sobre otro común, tipos integrados de .NET Framework, vea los temas de referencia para los siguientes elementos: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

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
