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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="9ab39-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9ab39-103">Protobuf reserved fields</span></span>

<span data-ttu-id="9ab39-104">Las garantías de compatibilidad con versiones anteriores en el búfer de protocolo (protobuf) se basan en los números de campo que siempre representan el mismo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="9ab39-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="9ab39-105">Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar.</span><span class="sxs-lookup"><span data-stu-id="9ab39-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="9ab39-106">Para ello, puede usar la palabra clave `reserved`.</span><span class="sxs-lookup"><span data-stu-id="9ab39-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="9ab39-107">Si los campos `displayName` y `marketId` se quitaron del mensaje de `Stock` definido anteriormente, los números de campo deben reservarse como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ab39-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="9ab39-108">También puede usar la palabra clave `reserved` como un marcador de posición para los campos que podrían agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9ab39-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="9ab39-109">Puede expresar números de campo contiguos como un intervalo mediante la palabra clave `to`.</span><span class="sxs-lookup"><span data-stu-id="9ab39-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="9ab39-110">[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="9ab39-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
