---
title: 'Campos reservados de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841394"
---
# <a name="protobuf-reserved-fields"></a>Campos reservados de Protobuf

Las garantías de compatibilidad con versiones anteriores de protobuf se basan en los números de campo que siempre representan el mismo elemento de datos. Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar. Esto se puede aplicar mediante la palabra clave `reserved`. Si los campos `displayName` y `marketId` se quitaron del mensaje de `Stock` definido anteriormente, los números de campo deben reservarse como en el ejemplo siguiente.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

La palabra clave `reserved` también se puede usar como marcador de posición para los campos que podrían agregarse en el futuro. Los números de campo contiguos se pueden expresar como un intervalo mediante la palabra clave `to`.

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
