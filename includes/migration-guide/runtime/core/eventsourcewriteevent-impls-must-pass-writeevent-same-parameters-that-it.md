---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235801"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)

|   |   |
|---|---|
|Detalles|El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.|
|Sugerencia|Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=name> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> en proceso para un origen de eventos que infringe este contrato.|
|Ámbito|Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
