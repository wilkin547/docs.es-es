---
title: 'Campos reservados de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542981"
---
# <a name="protobuf-reserved-fields"></a>Campos reservados de Protobuf

Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (protobuf) se basan en los números de campo que siempre representan el mismo elemento de datos. Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar. Para ello, puede usar la palabra clave `reserved`. 

Si los campos `displayName` y `marketId` se quitaron del mensaje de `Stock` definido anteriormente, los números de campo deben reservarse como en el ejemplo siguiente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

También puede usar la palabra clave `reserved` como un marcador de posición para los campos que podrían agregarse en el futuro. Puede expresar números de campo contiguos como un intervalo mediante la palabra clave `to`.

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
