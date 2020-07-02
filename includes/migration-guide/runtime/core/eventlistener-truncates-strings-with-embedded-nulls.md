---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620566"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener trunca las cadenas con valores NULL insertados

#### <a name="details"></a>Detalles

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> trunca las cadenas con valores NULL incrustados. Los caracteres NULL no son compatibles con la clase <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. El cambio solo afecta a las aplicaciones que usan <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> para leer datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> en proceso y que utilizan caracteres NULL como delimitadores.

#### <a name="suggestion"></a>Sugerencia

Se deben actualizar los datos de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, si es posible, para que no usen valores NULL insertados.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
