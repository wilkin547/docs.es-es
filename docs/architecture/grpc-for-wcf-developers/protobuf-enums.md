---
title: Enumeraciones protobuf - gRPC para desarrolladores de WCF
description: Aprenda a declarar y usar enumeraciones en Protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148080"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="41ff5-103">Enumeraciones de Protobuf</span><span class="sxs-lookup"><span data-stu-id="41ff5-103">Protobuf enumerations</span></span>

<span data-ttu-id="41ff5-104">Protobuf admite tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="41ff5-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="41ff5-105">Ha visto este soporte en la sección anterior, donde se `Oneof` usó una enumeración para determinar el tipo de un campo.</span><span class="sxs-lookup"><span data-stu-id="41ff5-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="41ff5-106">Puede definir sus propios tipos de enumeración y Protobuf los compilará en tipos de enumeración de C.</span><span class="sxs-lookup"><span data-stu-id="41ff5-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="41ff5-107">Dado que puede usar Protobuf con varios lenguajes, las convenciones de nomenclatura para las enumeraciones son diferentes de las convenciones de C.</span><span class="sxs-lookup"><span data-stu-id="41ff5-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="41ff5-108">Sin embargo, el generador de código convierte los nombres en el caso tradicional de C.</span><span class="sxs-lookup"><span data-stu-id="41ff5-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="41ff5-109">Si el equivalente de mayúsculas y minúsculas del nombre de campo comienza con el nombre de la enumeración, se quita.</span><span class="sxs-lookup"><span data-stu-id="41ff5-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="41ff5-110">Por ejemplo, en la siguiente enumeración Protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="41ff5-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="41ff5-111">Este prefijo es equivalente al nombre de `AccountStatus`enumeración de mayúsculas y minúsculas Pascal, .</span><span class="sxs-lookup"><span data-stu-id="41ff5-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="41ff5-112">El generador crea una enumeración de C- equivalente al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="41ff5-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="41ff5-113">Las definiciones de enumeración de Protobuf *deben* tener una constante cero como su primer campo.</span><span class="sxs-lookup"><span data-stu-id="41ff5-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="41ff5-114">Al igual que en C, puede declarar varios campos con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="41ff5-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="41ff5-115">Pero debe habilitar explícitamente esta `allow_alias` opción mediante la opción de la enumeración:</span><span class="sxs-lookup"><span data-stu-id="41ff5-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="41ff5-116">Puede declarar enumeraciones en el `.proto` nivel superior de un archivo o anidadas dentro de una definición de mensaje.</span><span class="sxs-lookup"><span data-stu-id="41ff5-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="41ff5-117">Las enumeraciones anidadas, como los `.Types` mensajes anidados, se declararán dentro de la clase estática en la clase de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="41ff5-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="41ff5-118">No hay forma de aplicar el atributo [[Flags]](xref:System.FlagsAttribute) a una enumeración generada por Protobuf, y Protobuf no entiende las combinaciones de enumeración bit a bit.</span><span class="sxs-lookup"><span data-stu-id="41ff5-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="41ff5-119">Observe el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="41ff5-119">Look at the following example:</span></span>

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

<span data-ttu-id="41ff5-120">Si establece `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`en , se serializa como `3`el valor entero .</span><span class="sxs-lookup"><span data-stu-id="41ff5-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="41ff5-121">Cuando un cliente o servidor intenta deserializar el valor, no encontrará `3`una coincidencia en la definición de enumeración para .</span><span class="sxs-lookup"><span data-stu-id="41ff5-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="41ff5-122">El resultado `Region.None`será .</span><span class="sxs-lookup"><span data-stu-id="41ff5-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="41ff5-123">La mejor manera de trabajar con varios valores de `repeated` enumeración en Protobuf es utilizar un campo del tipo enum.</span><span class="sxs-lookup"><span data-stu-id="41ff5-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="41ff5-124">[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="41ff5-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
