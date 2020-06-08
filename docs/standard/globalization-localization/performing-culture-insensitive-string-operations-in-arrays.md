---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
ms.openlocfilehash: 02690f78184ca4f216df7346a84f0266c2dcec99
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288607"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices

Las sobrecargas de los métodos <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>. Los resultados que tienen en cuenta las referencias culturales devueltos por estos métodos pueden variar en función de la referencia cultural según las diferencias de los criterios de ordenación. Para eliminar el comportamiento que tiene en cuenta las referencias culturales, use una de las sobrecargas de este método que acepta un parámetro `comparer`. El parámetro `comparer` especifica la implementación <xref:System.Collections.IComparer> para usarla al comparar elementos en la matriz. Para el parámetro, especifique una clase de comparador invariable personalizada que use <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Se proporciona una clase de comparador invariable personalizada en el subtema "Uso de la clase SortedList" del tema [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](performing-culture-insensitive-string-operations-in-collections.md).

> [!NOTE]
> Pasar **CultureInfo.InvariantCulture** a un método de comparación realiza una comparación que no tiene en cuenta la referencia cultural. Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno. Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación. Para una comparación no lingüística o la compatibilidad con las decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor <xref:System.StringComparison>. A continuación, la aplicación debe pasar <xref:System.StringComparison.Ordinal>.

## <a name="see-also"></a>Vea también

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>
- <xref:System.Collections.IComparer>
- [Realizar operaciones de cadenas que no distinguen entre referencias culturales](performing-culture-insensitive-string-operations.md)
