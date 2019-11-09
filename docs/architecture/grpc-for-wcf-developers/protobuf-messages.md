---
title: 'Mensajes de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo se definen los mensajes de protobuf en el C#IDL y se generan en.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 9943478698acfbb54b3e1dd0e6a856d11b9266c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841472"
---
# <a name="protobuf-messages"></a>Mensajes de Protobuf

En esta sección se describe cómo declarar mensajes protobuf en archivos de `.proto`, se explican los conceptos fundamentales de números y tipos de campo C# y se examina el código generado por el compilador de `protoc`. En el resto del capítulo veremos con más detalle cómo se representan los distintos tipos de datos en protobuf.

## <a name="declaring-a-message"></a>Declarar un mensaje

En WCF, una clase de `Stock` para una aplicación bursátil de stock market podría definirse como en el ejemplo siguiente:

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

Para implementar la clase equivalente en protobuf, se debe declarar en el archivo `.proto`. A continuación, el compilador `protoc` generará la clase .NET como parte del proceso de compilación.

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

La primera línea declara la versión de sintaxis que se está usando. La versión 3 del lenguaje se lanzó en 2016 y es la versión recomendada para gRPC Services.

La línea de `option csharp_namespace` especifica el espacio de nombres que se va C# a usar para los tipos generados. Esta opción se omitirá cuando el archivo de `.proto` se compile para otros idiomas. Es común que los archivos protobuf contengan opciones específicas del idioma para varios idiomas.

La definición del mensaje `Stock` especifica cuatro campos, cada uno con un tipo, un nombre y un número de campo.

## <a name="field-numbers"></a>Números de campo

Los números de campo son una parte importante de protobuf. Se usan para identificar los campos en los datos codificados binarios, lo que significa que no pueden cambiar de una versión a la versión del servicio. La ventaja es que es posible la compatibilidad con versiones anteriores y posteriores. Los clientes y servicios simplemente omitirán los números de campo que no conozcan, siempre y cuando se controle la posibilidad de que se produzcan valores.

En el formato binario, el número de campo se combina con un identificador de tipo. Los números de campo de 1 a 15 se pueden codificar con su tipo como un solo byte. los números de 16 a 2047 toman 2 bytes. Puede continuar si necesita más de 2047 campos en un mensaje por cualquier motivo. Los identificadores de un solo byte para los números de campo 1 a 15 ofrecen un mejor rendimiento, por lo que debe usarlos para los campos más básicos que se usan con frecuencia.

## <a name="types"></a>Tipos

Las declaraciones de tipos usan los tipos de datos escalares nativos de protobuf, que se describen con más detalle en [la sección siguiente](protobuf-data-types.md). En el resto de este capítulo se tratarán los tipos integrados de protobuf y se mostrará cómo se relacionan con los tipos comunes de .NET.

> [!NOTE]
> Protobuf no admite de forma nativa un tipo `decimal`, por lo que en su lugar se usa Double. En el caso de las aplicaciones que requieren una precisión decimal completa, consulte la [sección decimales](protobuf-data-types.md#decimals) en la siguiente parte de este capítulo.

## <a name="the-generated-code"></a>El código generado

Al compilar la aplicación, protobuf crea clases para cada uno de los mensajes, asignando sus C# tipos nativos a los tipos. El tipo de `Stock` generado tendría la siguiente firma:

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

El código real que se genera es mucho más complicado, porque cada clase contiene todo el código necesario para serializar y deserializar a sí mismo en el formato de conexión binaria.

### <a name="property-names"></a>Nombres de propiedad

Tenga en cuenta que el compilador protobuf aplicó `PascalCase` a los nombres de propiedad, aunque se `snake_case` en el archivo `.proto`. La [Guía de estilo de protobuf](https://developers.google.com/protocol-buffers/docs/style) recomienda el uso de `snake_case` en las definiciones de mensaje para que la generación de código para otras plataformas produzca el caso esperado de sus convenciones.

>[!div class="step-by-step"]
>[Anterior](protocol-buffers.md)
>[Siguiente](protobuf-data-types.md)
