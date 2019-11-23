---
title: 'Enumeraciones de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo declarar y usar enumeraciones en protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 4ea4d03bede2a9ebfd1f2c3ee56f299e918800e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971577"
---
# <a name="protobuf-enumerations"></a>Enumeraciones de Protobuf

Protobuf admite tipos de enumeración, como se ha podido ver en la sección anterior, donde se usó una enumeración para determinar el tipo de un campo de `oneof`. Puede definir sus propios tipos de enumeración y protobuf los compilará en tipos de C# enumeración. Dado que protobuf se puede usar con distintos lenguajes, las convenciones de nomenclatura para las enumeraciones C# son diferentes de las convenciones. Sin embargo, el generador de código es Clever y convierte los nombres en el C# caso tradicional. Si el equivalente en mayúsculas y minúsculas Pascal del nombre de campo comienza con el nombre de la enumeración, se quita.

Por ejemplo, en esta enumeración protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`, que es equivalente al nombre de enumeración de mayúsculas y minúsculas Pascal: `AccountStatus`.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Por lo tanto, el generador C# crea una enumeración equivalente al código siguiente:

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

Las definiciones de enumeración protobuf **deben** tener una constante cero como primer campo. Como en C#, puede declarar varios campos con el mismo valor, pero debe habilitar explícitamente esta opción mediante la opción `allow_alias` en la enumeración:

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

No hay ninguna manera de aplicar el atributo [[flags]](xref:System.FlagsAttribute) a una enumeración generada por protobuf y protobuf no entiende las combinaciones de enumeración bit a bit. Eche un vistazo al ejemplo siguiente:

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

Si establece `product.AvailableIn` en `Region.NorthAmerica | Region.SouthAmerica`, se serializa como el valor entero `3`. Cuando un cliente o un servidor intenta deserializar el valor, no encontrará ninguna coincidencia en la definición de enumeración para `3` y se `Region.None`rá el resultado.

La mejor manera de trabajar con varios valores de enumeración en protobuf es usar un campo `repeated` del tipo enum.

>[!div class="step-by-step"]
>[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)
