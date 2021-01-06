---
title: 'Campos reservados de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
ms.date: 12/15/2020
ms.openlocfilehash: d82043d619c5b3b81091ae4ea381e4778c1cf6ba
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938525"
---
# <a name="protobuf-reserved-fields"></a>Campos reservados de Protobuf

Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (protobuf) se basan en los números de campo que siempre representan el mismo elemento de datos. Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar. Puede aplicar este comportamiento mediante la `reserved` palabra clave.

Si los `displayName` `marketId` campos y se quitaron del `Stock` mensaje definido anteriormente, sus números de campo deben reservarse como en el ejemplo siguiente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

También puede usar la `reserved` palabra clave como marcador de posición para los campos que podrían agregarse en el futuro. Puede expresar números de campo contiguos como un intervalo mediante la `to` palabra clave.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)
