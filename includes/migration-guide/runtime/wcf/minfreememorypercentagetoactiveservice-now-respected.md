---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620650"
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
