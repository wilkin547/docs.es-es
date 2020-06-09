---
title: 'Cómo: obtener acceso a los servicios con un contrato dúplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597220"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="a7f04-102">Cómo: obtener acceso a los servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="a7f04-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="a7f04-103">Una característica de Windows Communication Foundation (WCF) es la capacidad de crear un servicio que usa un patrón de mensajería dúplex.</span><span class="sxs-lookup"><span data-stu-id="a7f04-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="a7f04-104">Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a7f04-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="a7f04-105">En este tema se muestran los pasos para crear un cliente WCF en una clase de cliente que implementa la interfaz de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a7f04-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="a7f04-106">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="a7f04-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a7f04-107">El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="a7f04-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="a7f04-108">Para ver un tutorial sobre la creación de un servicio y un cliente de WCF básico, consulte [Introducción tutorial](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a7f04-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="a7f04-109">Obtención de acceso a un servicio dúplex</span><span class="sxs-lookup"><span data-stu-id="a7f04-109">To access a duplex service</span></span>

1. <span data-ttu-id="a7f04-110">Cree un servicio que contenga dos interfaces.</span><span class="sxs-lookup"><span data-stu-id="a7f04-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="a7f04-111">La primera interfaz es para el servicio, la segunda es para la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a7f04-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="a7f04-112">Para obtener más información sobre cómo crear un servicio dúplex, consulte [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a7f04-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="a7f04-113">Ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="a7f04-113">Run the service.</span></span>

3. <span data-ttu-id="a7f04-114">Use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar contratos (interfaces) para el cliente.</span><span class="sxs-lookup"><span data-stu-id="a7f04-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="a7f04-115">Para obtener información sobre cómo hacerlo, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="a7f04-115">For information about how to do this, see  [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="a7f04-116">Implemente la interfaz de devolución de llamada en la clase de cliente, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7f04-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="a7f04-117">Cree una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="a7f04-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="a7f04-118">El constructor necesita una instancia de la clase cliente.</span><span class="sxs-lookup"><span data-stu-id="a7f04-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="a7f04-119">Cree una instancia del cliente WCF mediante el constructor que requiere un <xref:System.ServiceModel.InstanceContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="a7f04-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="a7f04-120">El segundo parámetro del constructor es el nombre de un punto de conexión encontrado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7f04-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="a7f04-121">Llame a los métodos del cliente WCF según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a7f04-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="a7f04-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7f04-122">Example</span></span>

<span data-ttu-id="a7f04-123">El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="a7f04-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a7f04-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7f04-124">See also</span></span>

- [<span data-ttu-id="a7f04-125">Tutorial de Introducción</span><span class="sxs-lookup"><span data-stu-id="a7f04-125">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="a7f04-126">Procedimiento para crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="a7f04-126">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="a7f04-127">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="a7f04-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="a7f04-128">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="a7f04-128">How to: Create a Client</span></span>](../how-to-create-a-wcf-client.md)
- [<span data-ttu-id="a7f04-129">Procedimiento para usar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="a7f04-129">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
