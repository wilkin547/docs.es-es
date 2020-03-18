---
title: Campos reservados de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147950"
---
# <a name="protobuf-reserved-fields"></a>Campos reservados de Protobuf

Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (Protobuf) se basan en números de campo que siempre representan el mismo elemento de datos. Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca debe reutilizarse. Puede hacerlo mediante la `reserved` palabra clave.

Si `displayName` los `marketId` campos y `Stock` se quitaron del mensaje definido anteriormente, sus números de campo deben reservarse como en el ejemplo siguiente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

También puede usar `reserved` la palabra clave como marcador de posición para los campos que se podrían agregar en el futuro. Puede expresar números de campo contiguos como un rango mediante la `to` palabra clave.

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
