---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804401"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>Los nombres de eventos de ETW no pueden diferir solamente en un sufijo "Start" o "Stop".

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6 y 4.6.1, el entorno de ejecución inicia una excepción <xref:System.ArgumentException> cuando dos nombres de evento de Seguimiento de eventos para Windows (ETW) solamente difieren en un sufijo &quot;Start&quot; o &quot;Stop&quot; (como cuando un evento se denomina <code>LogUser</code> y otro <code>LogUserStart</code>). En este caso, el entorno en tiempo de ejecución no puede crear el origen de eventos, que no puede emitir ningún registro.|
|Sugerencia|Para evitar la excepción, asegúrese de que no haya dos nombres de evento que solo difieran en un sufijo &quot;Start&quot; o &quot;Stop&quot;. Este requisito se ha eliminado a partir de .NET Framework 4.6.2; el entorno de ejecución puede eliminar la ambigüedad de los nombres de evento que solo difieren en el sufijo &quot;Start&quot; y &quot;Stop&quot;.|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|

