---
title: 'Enumeraciones de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo declarar y usar enumeraciones en protobuf.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f18196f54caba824d7101782a88cf3bf699560d5
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841418"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="7a650-103">Enumeraciones de Protobuf</span><span class="sxs-lookup"><span data-stu-id="7a650-103">Protobuf enumerations</span></span>

<span data-ttu-id="7a650-104">Protobuf admite tipos de enumeración, como se ha podido ver en la sección anterior, donde se usó una enumeración para determinar el tipo de un campo de `oneof`.</span><span class="sxs-lookup"><span data-stu-id="7a650-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="7a650-105">Puede definir sus propios tipos de enumeración y protobuf los compilará en tipos de C# enumeración.</span><span class="sxs-lookup"><span data-stu-id="7a650-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="7a650-106">Dado que protobuf se puede usar con distintos lenguajes, las convenciones de nomenclatura para las enumeraciones C# son diferentes de las convenciones.</span><span class="sxs-lookup"><span data-stu-id="7a650-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="7a650-107">Sin embargo, el generador de código es Clever y convierte los nombres en el C# caso tradicional.</span><span class="sxs-lookup"><span data-stu-id="7a650-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="7a650-108">Si el equivalente en mayúsculas y minúsculas Pascal del nombre de campo comienza con el nombre de la enumeración, se quita.</span><span class="sxs-lookup"><span data-stu-id="7a650-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="7a650-109">Por ejemplo, en esta enumeración protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`, que es equivalente al nombre de enumeración de mayúsculas y minúsculas Pascal: `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="7a650-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="7a650-110">Por lo tanto, el generador C# crea una enumeración equivalente al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a650-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="7a650-111">Las definiciones de enumeración protobuf **deben** tener una constante cero como primer campo.</span><span class="sxs-lookup"><span data-stu-id="7a650-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="7a650-112">Como en C#, puede declarar varios campos con el mismo valor, pero debe habilitar explícitamente esta opción mediante la opción `allow_alias` en la enumeración:</span><span class="sxs-lookup"><span data-stu-id="7a650-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="7a650-113">Puede declarar enumeraciones en el nivel superior de un archivo `.proto`, o anidadas en una definición de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7a650-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="7a650-114">Las enumeraciones anidadas, como los mensajes anidados, se declararán dentro de `.Types` clase estática en la clase de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="7a650-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="7a650-115">No hay ninguna manera de aplicar el atributo [[flags]](xref:System.FlagsAttribute) a una enumeración generada por protobuf y protobuf no entiende las combinaciones de enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="7a650-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="7a650-116">Eche un vistazo al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a650-116">Take a look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="7a650-117">Si establece `product.AvailableIn` en `Region.NorthAmerica | Region.SouthAmerica`, se serializa como el valor entero `3`.</span><span class="sxs-lookup"><span data-stu-id="7a650-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="7a650-118">Cuando un cliente o un servidor intenta deserializar el valor, no encontrará ninguna coincidencia en la definición de enumeración para `3` y se `Region.None`rá el resultado.</span><span class="sxs-lookup"><span data-stu-id="7a650-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="7a650-119">La mejor manera de trabajar con varios valores de enumeración en protobuf es usar un campo `repeated` del tipo enum.</span><span class="sxs-lookup"><span data-stu-id="7a650-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7a650-120">[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="7a650-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
