---
title: Realizar operaciones de cadenas que no distinguen entre referencias culturales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>Realizar operaciones de cadenas que no distinguen entre referencias culturales
Mayoría de los métodos de .NET Framework que realizan operaciones de cadenas dependientes de la referencia cultural predeterminada proporciona sobrecargas de método que permiten especificar explícitamente la referencia cultural a usar pasando un <xref:System.Globalization.CultureInfo> parámetro. Estas sobrecargas permiten eliminar variaciones de referencia cultural en reglas de ordenación y asignaciones de mayúsculas y minúsculas y garantizan resultados que no distinguen entre referencias culturales.  
  
 En esta sección se proporcionan los temas siguientes para mostrar cómo realizar operaciones de cadenas que no distinguen entre referencias culturales con métodos de .NET Framework que tienen en cuenta las referencias culturales de manera predeterminada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Realizar comparaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Describe cómo utilizar el <xref:System.String.Compare%2A?displayProperty=nameWithType> y <xref:System.String.CompareTo%2A?displayProperty=nameWithType> métodos para realizar comparaciones de cadenas de la referencia cultural.  
  
 [Realizar cambios de mayúsculas y minúsculas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Describe cómo utilizar el <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, y <xref:System.Char.ToLower%2A?displayProperty=nameWithType> métodos para realizar cambios de mayúsculas de la referencia cultural.  
  
 [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Describe cómo utilizar el <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> (clase), <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> y <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> para realizar operaciones de la referencia cultural en colecciones.  
  
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales en matrices](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Describe cómo utilizar el <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> métodos para realizar operaciones de la referencia cultural en matrices.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Operaciones de cadenas que no distinguen referencias culturales](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Describe por qué debe tomar en cuenta la referencia cultural cuando realiza operaciones en cadenas y proporciona guías que indiquen cuándo realizar operaciones que tienen en cuenta las referencias culturales y cuándo las que no distinguen entre referencias culturales.
