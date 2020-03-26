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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="1a4c2-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="1a4c2-103">Protobuf reserved fields</span></span>

<span data-ttu-id="1a4c2-104">Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (Protobuf) se basan en números de campo que siempre representan el mismo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="1a4c2-105">Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca debe reutilizarse.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="1a4c2-106">Puede aplicar esto mediante `reserved` la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="1a4c2-107">Si `displayName` los `marketId` campos y `Stock` se quitaron del mensaje definido anteriormente, sus números de campo deben reservarse como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="1a4c2-108">También puede usar `reserved` la palabra clave como marcador de posición para los campos que se podrían agregar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="1a4c2-109">Puede expresar números de campo contiguos como un rango mediante la `to` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1a4c2-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="1a4c2-110">[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="1a4c2-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
