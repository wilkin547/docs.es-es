---
title: Campos reservados de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111041"
---
# <a name="protobuf-reserved-fields"></a>Campos reservados de Protobuf

Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (Protobuf) se basan en números de campo que siempre representan el mismo elemento de datos. Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca debe reutilizarse. Puede aplicar esto mediante `reserved` la palabra clave.

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
