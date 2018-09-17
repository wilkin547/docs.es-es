---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22815b5ab993b36bc8bcb91f89f346cb6d812e19
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698252"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
Las sobrecargas de los métodos <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>. Los resultados que tienen en cuenta las referencias culturales devueltos por estos métodos pueden variar en función de la referencia cultural según las diferencias de los criterios de ordenación. Para eliminar el comportamiento que tiene en cuenta las referencias culturales, use una de las sobrecargas de este método que acepta un parámetro `comparer`. El parámetro `comparer` especifica la implementación <xref:System.Collections.IComparer> para usarla al comparar elementos en la matriz. Para el parámetro, especifique una clase de comparador invariable personalizada que use <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Se proporciona una clase de comparador invariable personalizada en el subtema "Uso de la clase SortedList" del tema [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).  
  
 **Nota** Pasar **CultureInfo.InvariantCulture** a un método de comparación realiza una comparación que no tiene en cuenta la referencia cultural. Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno. Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación. Para una comparación no lingüística o la compatibilidad con las decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor <xref:System.StringComparison>. A continuación, la aplicación debe pasar <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
- <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
- <xref:System.Collections.IComparer>  
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
