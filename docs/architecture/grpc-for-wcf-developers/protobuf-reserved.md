---
title: 'Campos reservados de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los campos reservados para la compatibilidad entre versiones.
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967309"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="340b9-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="340b9-103">Protobuf reserved fields</span></span>

<span data-ttu-id="340b9-104">Las garantías de compatibilidad con versiones anteriores de protobuf se basan en los números de campo que siempre representan el mismo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="340b9-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="340b9-105">Si se quita un campo de un mensaje en una nueva versión del servicio, ese número de campo nunca se debe volver a usar.</span><span class="sxs-lookup"><span data-stu-id="340b9-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="340b9-106">Esto se puede aplicar mediante la palabra clave `reserved`.</span><span class="sxs-lookup"><span data-stu-id="340b9-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="340b9-107">Si los campos `displayName` y `marketId` se quitaron del mensaje de `Stock` definido anteriormente, los números de campo deben reservarse como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="340b9-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="340b9-108">La palabra clave `reserved` también se puede usar como marcador de posición para los campos que podrían agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="340b9-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="340b9-109">Los números de campo contiguos se pueden expresar como un intervalo mediante la palabra clave `to`.</span><span class="sxs-lookup"><span data-stu-id="340b9-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="340b9-110">[Anterior](protobuf-repeated.md)
>[Siguiente](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="340b9-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
