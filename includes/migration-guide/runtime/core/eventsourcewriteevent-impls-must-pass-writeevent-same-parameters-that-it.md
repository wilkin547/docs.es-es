---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620575"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)

#### <a name="details"></a>Detalles

El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.

#### <a name="suggestion"></a>Sugerencia

Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=fullName> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> en proceso para un origen de eventos que infringe este contrato.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
