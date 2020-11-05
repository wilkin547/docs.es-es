---
title: Operaciones de cadenas que no distinguen entre referencias culturales
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET], culture-insensitive string operations
- strings [.NET], culture-insensitive string operations
- localization [.NET], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
ms.openlocfilehash: 3a6085d15dbaa30144436b163a6ecb777698f4f1
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064007"
---
# <a name="culture-insensitive-string-operations"></a>Operaciones de cadenas que no distinguen entre referencias culturales

Las operaciones de cadena que tienen en cuenta la referencia cultural pueden resultar ventajosas si va a crear aplicaciones diseñadas para mostrar los resultados en función de la referencia cultural. De manera predeterminada, los métodos que tienen en cuenta las referencias culturales obtienen la referencia cultural que van a usar de la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A> del subproceso actual.

En ocasiones, las operaciones de cadena que tienen en cuenta la referencia cultural no son el comportamiento más deseable. Si se utilizan operaciones que tienen en cuenta las referencias culturales cuando los resultados deben ser independientes de las referencias culturales, podrían producirse errores de código en referencias culturales con reglas de ordenación y asignaciones de mayúsculas y minúsculas personalizadas. Para obtener un ejemplo, vea [Comparaciones de cadenas que usan la referencia cultural actual](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) en el artículo [Prácticas recomendadas para utilizar las cadenas](../base-types/best-practices-strings.md).

Si las operaciones de cadenas deberían tener en cuenta las referencias culturales o no depende de cómo use la aplicación los resultados. Las operaciones de cadena que muestran los resultados al usuario normalmente deberían tener en cuenta las referencias culturales. Por ejemplo, si una aplicación muestra al usuario una lista ordenada de cadenas localizadas en un cuadro de lista, la aplicación debería realizar una ordenación que tuviera en cuenta las referencias culturales.

Los resultados de las operaciones de cadenas que se usan internamente no deberían normalmente tener en cuenta las referencias culturales. En general, si la aplicación está trabajando con nombres de archivo, formatos de persistencia o información simbólica que no se muestra al usuario final, los resultados de las operaciones de cadenas no deberían variar en función de la referencia cultural. Por ejemplo, si una aplicación compara una cadena para determinar si es una etiqueta XML reconocida, la comparación no debería tener en cuenta las referencias culturales. Asimismo, si una decisión de seguridad se basa en el resultado de una comparación de cadenas o de cambio de mayúsculas a minúsculas, la operación no debería tener en cuenta las referencias culturales para asegurarse de que el resultado no se vea afectado por el valor de <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.

Con independencia de que desarrolle o no una aplicación que incluya código para controlar ciertos aspectos de la localización y la globalización, debería conocer los métodos de .NET que recuperan resultados que tienen en cuenta las referencias culturales de manera predeterminada.

## <a name="see-also"></a>Vea también

- [Globalización y localización](index.md)
