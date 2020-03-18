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
# <a name="protobuf-enumerations"></a>Enumeraciones de Protobuf

Protobuf admite tipos de enumeración. Ha visto este soporte en la sección anterior, donde se `Oneof` usó una enumeración para determinar el tipo de un campo. Puede definir sus propios tipos de enumeración y Protobuf los compilará en tipos de enumeración de C.

Dado que puede usar Protobuf con varios lenguajes, las convenciones de nomenclatura para las enumeraciones son diferentes de las convenciones de C. Sin embargo, el generador de código convierte los nombres en el caso tradicional de C. Si el equivalente de mayúsculas y minúsculas del nombre de campo comienza con el nombre de la enumeración, se quita.

Por ejemplo, en la siguiente enumeración Protobuf, los campos tienen el prefijo `ACCOUNT_STATUS`. Este prefijo es equivalente al nombre de `AccountStatus`enumeración de mayúsculas y minúsculas Pascal, .

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

El generador crea una enumeración de C- equivalente al código siguiente:

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

Las definiciones de enumeración de Protobuf *deben* tener una constante cero como su primer campo. Al igual que en C, puede declarar varios campos con el mismo valor. Pero debe habilitar explícitamente esta `allow_alias` opción mediante la opción de la enumeración:

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

Puede declarar enumeraciones en el `.proto` nivel superior de un archivo o anidadas dentro de una definición de mensaje. Las enumeraciones anidadas, como los `.Types` mensajes anidados, se declararán dentro de la clase estática en la clase de mensaje generada.

No hay forma de aplicar el atributo [[Flags]](xref:System.FlagsAttribute) a una enumeración generada por Protobuf, y Protobuf no entiende las combinaciones de enumeración bit a bit. Observe el siguiente ejemplo:

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

Si establece `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`en , se serializa como `3`el valor entero . Cuando un cliente o servidor intenta deserializar el valor, no encontrará `3`una coincidencia en la definición de enumeración para . El resultado `Region.None`será .

La mejor manera de trabajar con varios valores de `repeated` enumeración en Protobuf es utilizar un campo del tipo enum.

>[!div class="step-by-step"]
>[Anterior](protobuf-any-oneof.md)
>[Siguiente](protobuf-maps.md)
