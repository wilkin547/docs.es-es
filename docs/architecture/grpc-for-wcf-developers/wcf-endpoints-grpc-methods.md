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
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="9fa84-103">Extremos de WCF y métodos gRPC</span><span class="sxs-lookup"><span data-stu-id="9fa84-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="9fa84-104">En Windows Communication Foundation (WCF), cuando se escribe el código de aplicación, se usa uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9fa84-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="9fa84-105">El código de aplicación se escribe en una clase y se decoran los métodos con el atributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="9fa84-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="9fa84-106">Se declara una interfaz para el servicio y se agregan atributos [OperationContract](xref:System.ServiceModel.OperationContractAttribute) a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="9fa84-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="9fa84-107">Por ejemplo, el equivalente de WCF del servicio `greet.proto` Greeter podría escribirse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9fa84-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="9fa84-108">En el capítulo 3 se mostró que las definiciones de mensaje de protobuf se usan para generar clases de datos.</span><span class="sxs-lookup"><span data-stu-id="9fa84-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="9fa84-109">Las declaraciones de servicio y método se utilizan para generar las clases base de las que se hereda para implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="9fa84-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="9fa84-110">Solo tiene que declarar los métodos que se van a implementar en el archivo `.proto` y el compilador genera una clase base con métodos virtuales que debe reemplazar.</span><span class="sxs-lookup"><span data-stu-id="9fa84-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="9fa84-111">Propiedades OperationContract</span><span class="sxs-lookup"><span data-stu-id="9fa84-111">OperationContract properties</span></span>

<span data-ttu-id="9fa84-112">El atributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) tiene propiedades para controlar o ajustar su funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="9fa84-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="9fa84-113">los métodos de gRPC no ofrecen este tipo de control.</span><span class="sxs-lookup"><span data-stu-id="9fa84-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="9fa84-114">En la tabla siguiente se enumeran las propiedades de `OperationContract` y se describe cómo se trata la funcionalidad que especifican (o no) en gRPC:</span><span class="sxs-lookup"><span data-stu-id="9fa84-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="9fa84-115">Propiedad `OperationContract`</span><span class="sxs-lookup"><span data-stu-id="9fa84-115">`OperationContract` property</span></span> | <span data-ttu-id="9fa84-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="9fa84-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="9fa84-117">Un URI identifica la operación.</span><span class="sxs-lookup"><span data-stu-id="9fa84-117">A URI identifies the operation.</span></span> <span data-ttu-id="9fa84-118">gRPC usa el nombre de `package`, `service`y `rpc` del archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="9fa84-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="9fa84-119">Todos los métodos de servicio de gRPC devuelven objetos `Task`.</span><span class="sxs-lookup"><span data-stu-id="9fa84-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="9fa84-120">Vea el párrafo que aparece después de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="9fa84-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="9fa84-121">Los métodos de gRPC unidireccionales devuelven `Empty` resultados o utilizan el streaming de cliente.</span><span class="sxs-lookup"><span data-stu-id="9fa84-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="9fa84-122">Vea el párrafo que aparece después de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="9fa84-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="9fa84-123">Esta propiedad está relacionada con SOAP y no tiene ningún significado en gRPC.</span><span class="sxs-lookup"><span data-stu-id="9fa84-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="9fa84-124">No hay cifrado de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9fa84-124">There's no message encryption.</span></span> <span data-ttu-id="9fa84-125">El cifrado de red se controla en el nivel de transporte (TLS sobre HTTP/2).</span><span class="sxs-lookup"><span data-stu-id="9fa84-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="9fa84-126">Esta propiedad está relacionada con SOAP y no tiene ningún significado en gRPC.</span><span class="sxs-lookup"><span data-stu-id="9fa84-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="9fa84-127">La propiedad `IsInitiating` permite indicar que un método dentro de [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) no puede ser el primer método al que se llama como parte de una sesión.</span><span class="sxs-lookup"><span data-stu-id="9fa84-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="9fa84-128">La propiedad `IsTerminating` hace que el servidor cierre la sesión después de que se llame a una operación (o el cliente, si la propiedad se usa en un cliente de devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="9fa84-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="9fa84-129">En gRPC, los flujos se crean mediante métodos únicos y se cierran explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9fa84-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="9fa84-130">Consulte [streaming de gRPC](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="9fa84-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="9fa84-131">Para obtener más información sobre la seguridad y el cifrado de gRPC, consulte el [capítulo 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="9fa84-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9fa84-132">[Anterior](wcf-services-to-grpc-comparison.md)
>[Siguiente](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9fa84-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
