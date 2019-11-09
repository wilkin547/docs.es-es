---
title: 'Extremos de WCF y métodos de gRPC: gRPC para desarrolladores de WCF'
description: Comparación de los puntos de conexión de WCF declarados con los atributos ServiceContract y OperationContract, y los métodos gRPC declarados en protobuf
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841304"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>Extremos de WCF y métodos gRPC

En WCF, cuando se escribe el código de aplicación, se usa uno de los métodos siguientes:

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

El atributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) tiene propiedades para controlar o ajustar su funcionamiento. los métodos de gRPC no ofrecen este tipo de control. En la tabla siguiente se establecen las propiedades de `OperationContract` y cómo se trata (o no) la funcionalidad que especifican en gRPC:

| Propiedad`OperationContract` | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | Identificador URI que identifica la operación. gRPC usa el nombre del `package`, `service` y `rpc` del archivo de `.proto`. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Todos los métodos de servicio de gRPC devuelven objetos `Task`. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Vea la nota siguiente. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | Los métodos de gRPC unidireccionales devuelven `Empty` resultados o utilizan el streaming de cliente. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Vea la nota siguiente. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Relacionado con SOAP, sin significado en gRPC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Sin cifrado de mensajes; cifrado de red controlado en la capa de transporte (TLS sobre HTTP/2). |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Relacionado con SOAP, sin significado en gRPC. |

La propiedad `IsInitiating` permite indicar que un método dentro de [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) no puede ser el primer método al que se llama como parte de una sesión. La propiedad `IsTerminating` hace que el servidor cierre la sesión después de que se llame a una operación (o el cliente, si se usa en un cliente de devolución de llamada). En gRPC, los flujos se crean mediante métodos únicos y se cierran explícitamente. Consulte [streaming de gRPC](rpc-types.md#grpc-streaming).

Para obtener más información sobre la seguridad y el cifrado de gRPC, consulte el [capítulo 6](security.md).

>[!div class="step-by-step"]
>[Anterior](wcf-services-to-grpc-comparison.md)
>[Siguiente](wcf-bindings.md)
