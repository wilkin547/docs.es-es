---
title: Procedimiento para exponer un contrato a clientes web y de SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: fa02260976c710401a05cce3d723cc0f66804c6e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593138"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="262b4-102">Procedimiento para exponer un contrato a clientes web y de SOAP</span><span class="sxs-lookup"><span data-stu-id="262b4-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="262b4-103">De forma predeterminada, Windows Communication Foundation (WCF) hace que los extremos estén disponibles solo para los clientes SOAP.</span><span class="sxs-lookup"><span data-stu-id="262b4-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="262b4-104">En [Cómo: crear un servicio básico web http de WCF](how-to-create-a-basic-wcf-web-http-service.md), se pone un punto de conexión a disposición de los clientes que no son SOAP.</span><span class="sxs-lookup"><span data-stu-id="262b4-104">In [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="262b4-105">Puede haber veces en las que desee poner el mismo contrato a disposición de ambos modos, como, por ejemplo, un punto de conexión web y un punto de conexión SOAP.</span><span class="sxs-lookup"><span data-stu-id="262b4-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="262b4-106">En este tema se muestra un ejemplo sobre cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="262b4-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="262b4-107">Para definir el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="262b4-107">To define the service contract</span></span>

1. <span data-ttu-id="262b4-108">Defina un contrato de servicios mediante una interfaz marcada con <xref:System.ServiceModel.ServiceContractAttribute> los <xref:System.ServiceModel.Web.WebInvokeAttribute> atributos, y <xref:System.ServiceModel.Web.WebGetAttribute> , tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="262b4-109">De forma predeterminada, <xref:System.ServiceModel.Web.WebInvokeAttribute> asigna las llamadas POST a la operación.</span><span class="sxs-lookup"><span data-stu-id="262b4-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="262b4-110">Sin embargo, puede especificar el método para asignar a la operación especificando un parámetro “method=”.</span><span class="sxs-lookup"><span data-stu-id="262b4-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="262b4-111"><xref:System.ServiceModel.Web.WebGetAttribute> no tiene un parámetro “method=” y solo asigna llamadas GET a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="262b4-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="262b4-112">Implemente el contrato de servicio, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="262b4-113">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="262b4-113">To host the service</span></span>

1. <span data-ttu-id="262b4-114">Cree un <xref:System.ServiceModel.ServiceHost> objeto, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="262b4-115">Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.BasicHttpBinding> para el extremo SOAP, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="262b4-116">Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.WebHttpBinding> para el extremo que no sea SOAP y agregue el <xref:System.ServiceModel.Description.WebHttpBehavior> al extremo, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="262b4-117">Llame a `Open()` en una <xref:System.ServiceModel.ServiceHost> instancia de para abrir el host de servicio, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="262b4-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="262b4-118">Para llamar a las operaciones de servicio asignadas a GET en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="262b4-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="262b4-119">Abra Internet Explorer y escriba " `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` " y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="262b4-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="262b4-120">La dirección URL contiene la dirección base del servicio ( `http://localhost:8000/` ), la dirección relativa del punto de conexión (""), la operación de servicio que se va a llamar ("EchoWithGet") y un signo de interrogación seguido de una lista de parámetros con nombre separados por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="262b4-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="262b4-121">Realización de llamadas a las operaciones de servicio en el extremo web mediante código</span><span class="sxs-lookup"><span data-stu-id="262b4-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="262b4-122">Cree una instancia de <xref:System.ServiceModel.Web.WebChannelFactory%601> dentro de un bloque `using`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="262b4-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="262b4-123">Se llama al método `Close()` de manera automática en el canal al final del bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="262b4-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="262b4-124">Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="262b4-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="262b4-125">Realización de llamadas a operaciones de servicio en el extremo SOAP</span><span class="sxs-lookup"><span data-stu-id="262b4-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="262b4-126">Cree una instancia de <xref:System.ServiceModel.ChannelFactory> dentro de un bloque `using`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="262b4-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="262b4-127">Cree un canal y llame al servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="262b4-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="262b4-128">Cierre del host de servicio</span><span class="sxs-lookup"><span data-stu-id="262b4-128">To close the service host</span></span>

1. <span data-ttu-id="262b4-129">Cierre el host de servicio, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="262b4-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="262b4-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="262b4-130">Example</span></span>

<span data-ttu-id="262b4-131">A continuación se muestra la lista de código completa de este tema:</span><span class="sxs-lookup"><span data-stu-id="262b4-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="262b4-132">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="262b4-132">Compiling the code</span></span>

 <span data-ttu-id="262b4-133">Cuando se compila Service.cs, haga una referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="262b4-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="262b4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="262b4-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="262b4-135">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="262b4-135">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
