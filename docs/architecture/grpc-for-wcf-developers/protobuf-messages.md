---
title: 'Mensajes de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo se definen los mensajes de protobuf en el IDL y se generan en C#.
ms.date: 12/15/2020
ms.openlocfilehash: c1f2a3071d45dcbe4b98d747f19fed508bad102f
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938109"
---
# <a name="protobuf-messages"></a>Mensajes de Protobuf

En esta sección se explica cómo declarar mensajes de búfer de protocolo (protobuf) en `.proto` archivos. En él se explican los conceptos fundamentales de los números y tipos de campo, y se examina el código de C# generado por el `protoc` compilador.

En el resto del capítulo veremos con más detalle cómo se representan los distintos tipos de datos en protobuf.

## <a name="declaring-a-message"></a>Declarar un mensaje

En Windows Communication Foundation (WCF), una `Stock` clase para una aplicación bursátil de stock market podría definirse como en el ejemplo siguiente:

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

Para implementar la clase equivalente en protobuf, debe declararla en el `.proto` archivo. `protoc`Después, el compilador generará la clase .net como parte del proceso de compilación.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

La primera línea declara la versión de sintaxis que se está usando. La versión 3 del idioma se lanzó en 2016. Es la versión que recomendamos para gRPC Services.

La `option csharp_namespace` línea especifica el espacio de nombres que se va a usar para los tipos de C# generados. Esta opción se omitirá cuando el `.proto` archivo se compile para otros lenguajes. Los archivos protobuf a menudo contienen opciones específicas del idioma para varios idiomas.

La `Stock` definición del mensaje especifica cuatro campos. Cada tiene un tipo, un nombre y un número de campo.

## <a name="field-numbers"></a>Números de campo

Los números de campo son una parte importante de protobuf. Se usan para identificar los campos en los datos codificados binarios, lo que significa que no pueden cambiar de una versión a la versión del servicio. La ventaja es que es posible la compatibilidad con versiones anteriores y versiones posteriores. Los clientes y servicios omitirán los números de campo que no conozcan, siempre y cuando se controle la posibilidad de que se produzcan valores.

En el formato binario, el número de campo se combina con un identificador de tipo. Los números de campo de 1 a 15 se pueden codificar con su tipo como un solo byte. Los números de 16 a 2.047 toman 2 bytes. Puede continuar si necesita más de 2.047 campos en un mensaje por cualquier motivo. Los identificadores de un solo byte para los números de campo 1 a 15 ofrecen un mejor rendimiento, por lo que debe usarlos para los campos más básicos que se usan con frecuencia.

## <a name="types"></a>Tipos

Las declaraciones de tipos usan los tipos de datos escalares nativos de protobuf, que se describen con más detalle en [la sección siguiente](protobuf-data-types.md). En el resto de este capítulo se tratarán los tipos integrados de protobuf y se mostrará cómo se relacionan con los tipos comunes de .NET.

> [!NOTE]
> Protobuf no admite de forma nativa un `decimal` tipo, por lo que `double` se usa en su lugar. En el caso de las aplicaciones que requieren una precisión decimal completa, consulte la [sección decimales](protobuf-data-types.md#decimals) en la siguiente parte de este capítulo.

## <a name="the-generated-code"></a>El código generado

Al compilar la aplicación, protobuf crea clases para cada uno de los mensajes, asignando sus tipos nativos a tipos de C#. El `Stock` tipo generado tendría la firma siguiente:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

El código real que se genera es mucho más complicado que este. La razón es que cada clase contiene todo el código necesario para serializar y deserializar en el formato de conexión binaria.

### <a name="property-names"></a>Nombres de propiedad

Tenga en cuenta que el compilador protobuf `PascalCase` se aplica a los nombres de propiedad, aunque se encontraban `snake_case` en el `.proto` archivo. La [Guía de estilo de protobuf](https://developers.google.com/protocol-buffers/docs/style) recomienda el uso `snake_case` de en las definiciones de mensaje para que la generación de código para otras plataformas produzca el caso esperado de sus convenciones.

>[!div class="step-by-step"]
>[Anterior](protocol-buffers.md)
>[Siguiente](protobuf-data-types.md)
