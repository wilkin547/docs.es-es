---
title: Mensajes de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga más información sobre cómo se definen los mensajes de Protobuf en el IDL y se generan en C.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147989"
---
# <a name="protobuf-messages"></a>Mensajes de Protobuf

En esta sección se explica cómo declarar mensajes `.proto` de búfer de protocolo (Protobuf) en archivos. En él se explican los conceptos fundamentales de los tipos `protoc` y números de campo y se examina el código de C- que genera el compilador.

El resto del capítulo examinará con más detalle cómo se representan los diferentes tipos de datos en Protobuf.

## <a name="declaring-a-message"></a>Declarar un mensaje

En Windows Communication Foundation `Stock` (WCF), una clase para una aplicación de trading en el mercado de valores podría definirse como en el ejemplo siguiente:

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

Para implementar la clase equivalente en Protobuf, `.proto` debe declararla en el archivo. A `protoc` continuación, el compilador generará la clase .NET como parte del proceso de compilación.

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

La primera línea declara la versión de sintaxis que se está utilizando. La versión 3 del idioma fue lanzada en 2016. Es la versión que recomendamos para los servicios gRPC.

La `option csharp_namespace` línea especifica el espacio de nombres que se usará para los tipos generados de C. Esta opción se omitirá cuando el `.proto` archivo se compile para otros idiomas. Los archivos Protobuf a menudo contienen opciones específicas del idioma para varios idiomas.

La `Stock` definición del mensaje especifica cuatro campos. Cada uno tiene un tipo, un nombre y un número de campo.

## <a name="field-numbers"></a>Números de campo

Los números de campo son una parte importante de Protobuf. Se usan para identificar campos en los datos codificados binarios, lo que significa que no pueden cambiar de versión a versión del servicio. La ventaja es que la compatibilidad con versiones anteriores y la compatibilidad hacia delante son posibles. Los clientes y servicios simplemente ignorarán los números de campo que no conocen, siempre y cuando se maneje la posibilidad de que falten valores.

En el formato binario, el número de campo se combina con un identificador de tipo. Los números de campo del 1 al 15 se pueden codificar con su tipo como un solo byte. Los números de 16 a 2.047 toman 2 bytes. Puede ir más alto si necesita más de 2.047 campos en un mensaje por cualquier motivo. Los identificadores de bytes únicos para los números de campo 1 a 15 ofrecen un mejor rendimiento, por lo que debe usarlos para los campos más básicos y de uso frecuente.

## <a name="types"></a>Tipos

Las declaraciones de tipo utilizan los tipos de datos escalares nativos de Protobuf, que se describen con más detalle en [la sección siguiente.](protobuf-data-types.md) El resto de este capítulo tratará los tipos integrados de Protobuf y mostrará cómo se relacionan con los tipos comunes de .NET.

> [!NOTE]
> Protobuf no admite de `decimal` forma nativa `double` un tipo, por lo que se usa en su lugar. Para aplicaciones que requieren precisión decimal completa, consulte la [sección decimal en](protobuf-data-types.md#decimals) la siguiente parte de este capítulo.

## <a name="the-generated-code"></a>El código generado

Al compilar la aplicación, Protobuf crea clases para cada uno de los mensajes, asignando sus tipos nativos a tipos de C. El tipo `Stock` generado tendría la siguiente firma:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

El código real que se genera es mucho más complicado que esto. La razón es que cada clase contiene todo el código necesario para serializar y deserializarse al formato de cable binario.

### <a name="property-names"></a>Nombres de propiedad

Tenga en cuenta que `PascalCase` el compilador Protobuf `snake_case` se `.proto` aplicó a los nombres de propiedad, aunque estaban en el archivo. La guía de estilo `snake_case` [Protobuf](https://developers.google.com/protocol-buffers/docs/style) recomienda usar en las definiciones de mensajes para que la generación de código para otras plataformas genere el caso esperado para sus convenciones.

>[!div class="step-by-step"]
>[Anterior](protocol-buffers.md)
>[Siguiente](protobuf-data-types.md)
