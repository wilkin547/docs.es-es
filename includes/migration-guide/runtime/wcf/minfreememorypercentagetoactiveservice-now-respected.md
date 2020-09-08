---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496285"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>Ahora se respeta MinFreeMemoryPercentageToActiveService

#### <a name="details"></a>Detalles

Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF. Está diseñado para evitar las excepciones <xref:System.OutOfMemoryException?displayProperty=fullName>. En .NET Framework 4.5, este ajuste no tenía ningún efecto. En .NET Framework 4.5.1, este ajuste se respeta.

#### <a name="suggestion"></a>Sugerencia

Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
