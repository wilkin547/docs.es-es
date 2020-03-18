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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="f913d-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="f913d-103">Protobuf reserved fields</span></span>

<span data-ttu-id="f913d-104">Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (Protobuf) se basan en números de campo que siempre representan el mismo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="f913d-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="f913d-105">Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca debe reutilizarse.</span><span class="sxs-lookup"><span data-stu-id="f913d-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="f913d-106">Puede hacerlo mediante la `reserved` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f913d-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="f913d-107">Si `displayName` los `marketId` campos y `Stock` se quitaron del mensaje definido anteriormente, sus números de campo deben reservarse como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f913d-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="f913d-108">También puede usar `reserved` la palabra clave como marcador de posición para los campos que se podrían agregar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f913d-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="f913d-109">Puede expresar números de campo contiguos como un rango mediante la `to` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f913d-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="f913d-110">[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="f913d-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
