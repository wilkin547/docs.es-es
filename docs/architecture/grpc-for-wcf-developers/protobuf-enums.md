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
# <a name="protobuf-enumerations"></a>Enumeraciones de Protobuf

Protobuf admite tipos de enumeración. Vio esta compatibilidad en la sección anterior, donde se usaba una enumeración para determinar el tipo de un campo de `Oneof`. Puede definir sus propios tipos de enumeración y protobuf los compilará C# en tipos de enumeración. 

Dado que puede usar protobuf con varios lenguajes, las convenciones de nomenclatura para las enumeraciones son C# diferentes de las convenciones. Sin embargo, el generador de código convierte los nombres en el C# caso tradicional. Si el equivalente en mayúsculas y minúsculas Pascal del nombre de campo comienza con el nombre de la enumeración, se quita.

Por ejemplo, en la siguiente enumeración protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`. Este prefijo es equivalente al nombre de enumeración de mayúsculas y minúsculas Pascal, `AccountStatus`.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

El generador crea una C# enumeración equivalente al código siguiente:

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

Las definiciones de enumeración protobuf *deben* tener una constante cero como primer campo. Como en C#, puede declarar varios campos con el mismo valor. Pero debe habilitar explícitamente esta opción mediante la opción `allow_alias` en la enumeración:

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

Puede declarar enumeraciones en el nivel superior de un archivo `.proto`, o anidadas en una definición de mensaje. Las enumeraciones anidadas, como los mensajes anidados, se declararán dentro de `.Types` clase estática en la clase de mensaje generada.

No hay ninguna manera de aplicar el atributo [[flags]](xref:System.FlagsAttribute) a una enumeración generada por protobuf y protobuf no entiende las combinaciones de enumeración bit a bit. Observe el ejemplo siguiente:

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

Si establece `product.AvailableIn` en `Region.NorthAmerica | Region.SouthAmerica`, se serializa como el valor entero `3`. Cuando un cliente o un servidor intenta deserializar el valor, no encontrará ninguna coincidencia en la definición de enumeración para `3`. El resultado será `Region.None`.

La mejor manera de trabajar con varios valores de enumeración en protobuf es usar un campo `repeated` del tipo enum.

>[!div class="step-by-step"]
>[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)
