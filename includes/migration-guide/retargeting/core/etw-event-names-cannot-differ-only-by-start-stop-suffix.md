---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614677"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>Los nombres de eventos de ETW no pueden diferir solamente en un sufijo "Start" o "Stop".

#### <a name="details"></a>Detalles

En .NET Framework 4.6 y 4.6.1, el entorno de ejecución inicia una excepción <xref:System.ArgumentException> cuando dos nombres de evento de Seguimiento de eventos para Windows (ETW) solamente difieren en un sufijo "Start" o "Stop" (como cuando un evento se denomina `LogUser` y otro `LogUserStart`). En este caso, el entorno en tiempo de ejecución no puede crear el origen de eventos, que no puede emitir ningún registro.

#### <a name="suggestion"></a>Sugerencia

Para evitar la excepción, asegúrese de que no haya dos nombres de evento que solo difieran en un sufijo "Start" o "Stop". Este requisito se ha eliminado a partir de .NET Framework 4.6.2; el entorno de ejecución puede eliminar la ambigüedad de los nombres de evento que solo difieren en el sufijo "Start" y "Stop".

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6         |
| Tipo    | Redestinación |
