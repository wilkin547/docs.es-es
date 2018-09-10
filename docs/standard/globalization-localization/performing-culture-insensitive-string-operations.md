---
title: Realizar operaciones de cadenas que no distinguen entre referencias culturales
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748b4170e9e4c0df048c542d06bcb64a56ccf677
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199952"
---
# <a name="performing-culture-insensitive-string-operations"></a>Realizar operaciones de cadena que no distinguen entre referencias culturales
La mayoría de los métodos de .NET Framework que realizan operaciones de cadenas que no distinguen entre referencias culturales de manera predeterminada proporcionan sobrecargas de método que permiten especificar explícitamente la referencia cultural que se usará para pasar un parámetro <xref:System.Globalization.CultureInfo>. Estas sobrecargas permiten eliminar variaciones de referencia cultural en reglas de ordenación y asignaciones de mayúsculas y minúsculas y garantizan resultados que no distinguen entre referencias culturales.  
  
 En esta sección se proporcionan los temas siguientes para mostrar cómo realizar operaciones de cadenas que no distinguen entre referencias culturales con métodos de .NET Framework que tienen en cuenta las referencias culturales de manera predeterminada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Realizar comparaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Se describe cómo usar los métodos <xref:System.String.Compare%2A?displayProperty=nameWithType> y <xref:System.String.CompareTo%2A?displayProperty=nameWithType> para realizar comparaciones de cadenas que no distinguen entre referencias culturales.  
  
 [Realizar cambios de mayúsculas y minúsculas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Se describe cómo usar los métodos <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> y <xref:System.Char.ToLower%2A?displayProperty=nameWithType> para realizar cambios de mayúsculas y minúsculas que no distinguen entre referencias culturales.  
  
 [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Se describe cómo usar las clases <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider>, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> y <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> para realizar operaciones en colecciones que no distinguen entre referencias culturales.  
  
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales en matrices](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Se describe cómo usar los métodos <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> para realizar operaciones en matrices que no distinguen entre referencias culturales.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Operaciones de cadenas que no distinguen referencias culturales](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Describe por qué debe tomar en cuenta la referencia cultural cuando realiza operaciones en cadenas y proporciona guías que indiquen cuándo realizar operaciones que tienen en cuenta las referencias culturales y cuándo las que no distinguen entre referencias culturales.

## <a name="see-also"></a>Vea también

- [Ordenación de tablas de pesos](https://www.microsoft.com/en-us/download/details.aspx?id=10921)
