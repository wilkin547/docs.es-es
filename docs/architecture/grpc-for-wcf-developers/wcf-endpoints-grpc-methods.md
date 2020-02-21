---
title: 'Extremos de WCF y métodos de gRPC: gRPC para desarrolladores de WCF'
description: Comparación de los puntos de conexión de WCF declarados con los atributos ServiceContract y OperationContract, y los métodos gRPC declarados en protobuf
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503430"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>Extremos de WCF y métodos gRPC

En Windows Communication Foundation (WCF), cuando se escribe el código de aplicación, se usa uno de los métodos siguientes:

- El código de aplicación se escribe en una clase y se decoran los métodos con el atributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .
- Se declara una interfaz para el servicio y se agregan atributos [OperationContract](xref:System.ServiceModel.OperationContractAttribute) a la interfaz.

Por ejemplo, el equivalente de WCF del servicio `greet.proto` Greeter podría escribirse de la siguiente manera:

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

En el capítulo 3 se mostró que las definiciones de mensaje de protobuf se usan para generar clases de datos. Las declaraciones de servicio y método se utilizan para generar las clases base de las que se hereda para implementar el servicio. Solo tiene que declarar los métodos que se van a implementar en el archivo `.proto` y el compilador genera una clase base con métodos virtuales que debe reemplazar.

## <a name="operationcontract-properties"></a>Propiedades OperationContract

El atributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) tiene propiedades para controlar o ajustar su funcionamiento. los métodos de gRPC no ofrecen este tipo de control. En la tabla siguiente se enumeran las propiedades de `OperationContract` y se describe cómo se trata la funcionalidad que especifican (o no) en gRPC:

| Propiedad `OperationContract` | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | Un URI identifica la operación. gRPC usa el nombre de `package`, `service`y `rpc` del archivo de `.proto`. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Todos los métodos de servicio de gRPC devuelven objetos `Task`. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Vea el párrafo que aparece después de esta tabla. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | Los métodos de gRPC unidireccionales devuelven `Empty` resultados o utilizan el streaming de cliente. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Vea el párrafo que aparece después de esta tabla. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Esta propiedad está relacionada con SOAP y no tiene ningún significado en gRPC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | No hay cifrado de mensajes. El cifrado de red se controla en el nivel de transporte (TLS sobre HTTP/2). |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Esta propiedad está relacionada con SOAP y no tiene ningún significado en gRPC. |

La propiedad `IsInitiating` permite indicar que un método dentro de [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) no puede ser el primer método al que se llama como parte de una sesión. La propiedad `IsTerminating` hace que el servidor cierre la sesión después de que se llame a una operación (o el cliente, si la propiedad se usa en un cliente de devolución de llamada). En gRPC, los flujos se crean mediante métodos únicos y se cierran explícitamente. Consulte [streaming de gRPC](rpc-types.md#grpc-streaming).

Para obtener más información sobre la seguridad y el cifrado de gRPC, consulte el [capítulo 6](security.md).

>[!div class="step-by-step"]
>[Anterior](wcf-services-to-grpc-comparison.md)
>[Siguiente](wcf-bindings.md)
