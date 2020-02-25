---
title: 'Enumeraciones de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo declarar y usar enumeraciones en protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543149"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="01ec7-103">Enumeraciones de Protobuf</span><span class="sxs-lookup"><span data-stu-id="01ec7-103">Protobuf enumerations</span></span>

<span data-ttu-id="01ec7-104">Protobuf admite tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="01ec7-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="01ec7-105">Vio esta compatibilidad en la sección anterior, donde se usaba una enumeración para determinar el tipo de un campo de `Oneof`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="01ec7-106">Puede definir sus propios tipos de enumeración y protobuf los compilará C# en tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="01ec7-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="01ec7-107">Dado que puede usar protobuf con varios lenguajes, las convenciones de nomenclatura para las enumeraciones son C# diferentes de las convenciones.</span><span class="sxs-lookup"><span data-stu-id="01ec7-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="01ec7-108">Sin embargo, el generador de código convierte los nombres en el C# caso tradicional.</span><span class="sxs-lookup"><span data-stu-id="01ec7-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="01ec7-109">Si el equivalente en mayúsculas y minúsculas Pascal del nombre de campo comienza con el nombre de la enumeración, se quita.</span><span class="sxs-lookup"><span data-stu-id="01ec7-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="01ec7-110">Por ejemplo, en la siguiente enumeración protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="01ec7-111">Este prefijo es equivalente al nombre de enumeración de mayúsculas y minúsculas Pascal, `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="01ec7-112">El generador crea una C# enumeración equivalente al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="01ec7-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="01ec7-113">Las definiciones de enumeración protobuf *deben* tener una constante cero como primer campo.</span><span class="sxs-lookup"><span data-stu-id="01ec7-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="01ec7-114">Como en C#, puede declarar varios campos con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="01ec7-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="01ec7-115">Pero debe habilitar explícitamente esta opción mediante la opción `allow_alias` en la enumeración:</span><span class="sxs-lookup"><span data-stu-id="01ec7-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="01ec7-116">Puede declarar enumeraciones en el nivel superior de un archivo `.proto`, o anidadas en una definición de mensaje.</span><span class="sxs-lookup"><span data-stu-id="01ec7-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="01ec7-117">Las enumeraciones anidadas, como los mensajes anidados, se declararán dentro de `.Types` clase estática en la clase de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="01ec7-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="01ec7-118">No hay ninguna manera de aplicar el atributo [[flags]](xref:System.FlagsAttribute) a una enumeración generada por protobuf y protobuf no entiende las combinaciones de enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="01ec7-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="01ec7-119">Observe el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01ec7-119">Look at the following example:</span></span>

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

<span data-ttu-id="01ec7-120">Si establece `product.AvailableIn` en `Region.NorthAmerica | Region.SouthAmerica`, se serializa como el valor entero `3`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="01ec7-121">Cuando un cliente o un servidor intenta deserializar el valor, no encontrará ninguna coincidencia en la definición de enumeración para `3`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="01ec7-122">El resultado será `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="01ec7-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="01ec7-123">La mejor manera de trabajar con varios valores de enumeración en protobuf es usar un campo `repeated` del tipo enum.</span><span class="sxs-lookup"><span data-stu-id="01ec7-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="01ec7-124">[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="01ec7-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
