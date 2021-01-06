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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="e8550-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="e8550-103">Protobuf reserved fields</span></span>

<span data-ttu-id="e8550-104">Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (protobuf) se basan en los números de campo que siempre representan el mismo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="e8550-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="e8550-105">Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar.</span><span class="sxs-lookup"><span data-stu-id="e8550-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="e8550-106">Puede aplicar este comportamiento mediante la `reserved` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e8550-106">You can enforce this behavior by using the `reserved` keyword.</span></span>

<span data-ttu-id="e8550-107">Si los `displayName` `marketId` campos y se quitaron del `Stock` mensaje definido anteriormente, sus números de campo deben reservarse como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8550-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="e8550-108">También puede usar la `reserved` palabra clave como marcador de posición para los campos que podrían agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e8550-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="e8550-109">Puede expresar números de campo contiguos como un intervalo mediante la `to` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e8550-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="e8550-110">[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="e8550-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
