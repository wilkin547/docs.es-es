---
title: Procedimiento para exponer un contrato a clientes web y de SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: 303367c85e311ac5c07c11b849b5586354980a3c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636154"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="f5754-102">Procedimiento para exponer un contrato a clientes web y de SOAP</span><span class="sxs-lookup"><span data-stu-id="f5754-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="f5754-103">De forma predeterminada, Windows Communication Foundation (WCF) hace que los puntos de conexión que estén disponibles sólo para clientes SOAP.</span><span class="sxs-lookup"><span data-stu-id="f5754-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="f5754-104">En [Cómo: Crear un servicio de WCF Web HTTP básico](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), un punto de conexión está disponible para los clientes que no sea SOAP.</span><span class="sxs-lookup"><span data-stu-id="f5754-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="f5754-105">Puede haber veces en las que desee poner el mismo contrato a disposición de ambos modos, como, por ejemplo, un punto de conexión web y un punto de conexión SOAP.</span><span class="sxs-lookup"><span data-stu-id="f5754-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="f5754-106">En este tema se muestra un ejemplo sobre cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f5754-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="f5754-107">Para definir el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="f5754-107">To define the service contract</span></span>

1. <span data-ttu-id="f5754-108">Defina un contrato de servicio mediante una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> y <xref:System.ServiceModel.Web.WebGetAttribute> atributos, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="f5754-109">De forma predeterminada, <xref:System.ServiceModel.Web.WebInvokeAttribute> asigna las llamadas POST a la operación.</span><span class="sxs-lookup"><span data-stu-id="f5754-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="f5754-110">Sin embargo, puede especificar el método para asignar a la operación especificando un parámetro “method=”.</span><span class="sxs-lookup"><span data-stu-id="f5754-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="f5754-111"><xref:System.ServiceModel.Web.WebGetAttribute> no tiene un parámetro “method=” y solo asigna llamadas GET a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="f5754-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="f5754-112">Implemente el contrato de servicio, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="f5754-113">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="f5754-113">To host the service</span></span>

1. <span data-ttu-id="f5754-114">Crear un <xref:System.ServiceModel.ServiceHost> de objeto, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="f5754-115">Agregar un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.BasicHttpBinding> para el extremo SOAP, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="f5754-116">Agregar un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.WebHttpBinding> para el punto de conexión no SOAP y agregue el <xref:System.ServiceModel.Description.WebHttpBehavior> al punto de conexión, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="f5754-117">Llame a `Open()` en un <xref:System.ServiceModel.ServiceHost> instancia para abrir el host del servicio, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5754-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="f5754-118">Para llamar a las operaciones de servicio asignadas a GET en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f5754-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="f5754-119">Abra Internet Explorer y escriba "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f5754-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="f5754-120">La dirección URL contiene la dirección base del servicio (`http://localhost:8000/`), la dirección relativa del punto de conexión (""), la operación de servicio para llamar ("EchoWithGet") y un signo de interrogación seguido de una lista de parámetros con nombre separados por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="f5754-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="f5754-121">Realización de llamadas a las operaciones de servicio en el extremo web mediante código</span><span class="sxs-lookup"><span data-stu-id="f5754-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="f5754-122">Cree una instancia de <xref:System.ServiceModel.Web.WebChannelFactory%601> dentro de un bloque `using`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5754-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="f5754-123">Se llama al método `Close()` de manera automática en el canal al final del bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="f5754-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="f5754-124">Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5754-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="f5754-125">Realización de llamadas a operaciones de servicio en el extremo SOAP</span><span class="sxs-lookup"><span data-stu-id="f5754-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="f5754-126">Cree una instancia de <xref:System.ServiceModel.ChannelFactory> dentro de un bloque `using`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5754-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="f5754-127">Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5754-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="f5754-128">Cierre del host de servicio</span><span class="sxs-lookup"><span data-stu-id="f5754-128">To close the service host</span></span>

1. <span data-ttu-id="f5754-129">Cierre el host de servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5754-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="f5754-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5754-130">Example</span></span>

<span data-ttu-id="f5754-131">Este es el listado de este tema de código completo:</span><span class="sxs-lookup"><span data-stu-id="f5754-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="f5754-132">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="f5754-132">Compiling the code</span></span>

 <span data-ttu-id="f5754-133">Cuando se compila Service.cs, haga una referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="f5754-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5754-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5754-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="f5754-135">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f5754-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
