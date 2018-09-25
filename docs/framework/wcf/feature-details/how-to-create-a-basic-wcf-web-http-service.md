---
title: 'Cómo: Crear un servicio básico web HTTP de WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
ms.openlocfilehash: 1b76d21cb4f416aae76e7597ad16cfd45e5b7cad
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090560"
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="cfac9-102">Cómo: Crear un servicio básico web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="cfac9-102">How to: Create a Basic WCF Web HTTP Service</span></span>

<span data-ttu-id="cfac9-103">Windows Communication Foundation (WCF) le permite crear un servicio que expone un extremo Web.</span><span class="sxs-lookup"><span data-stu-id="cfac9-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="cfac9-104">Los puntos de conexión web envían los datos por XML o JSON, no hay ninguna envoltura SOAP.</span><span class="sxs-lookup"><span data-stu-id="cfac9-104">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="cfac9-105">En este tema se muestra cómo exponer este tipo de extremos.</span><span class="sxs-lookup"><span data-stu-id="cfac9-105">This topic demonstrates how to expose such an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="cfac9-106">La única manera de proteger un extremo web es exponerlo a través de HTTPS, utilizando la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="cfac9-106">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="cfac9-107">Al usar la seguridad basada en mensaje, la información de seguridad se coloca normalmente en encabezados SOAP, y dado que los mensajes enviados a los extremos que no son SOAP no contienen envoltura SOAP, no hay ningún lugar donde colocar la información de seguridad y debe confiar en la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="cfac9-107">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>

## <a name="to-create-a-web-endpoint"></a><span data-ttu-id="cfac9-108">Para crear un punto de conexión web</span><span class="sxs-lookup"><span data-stu-id="cfac9-108">To create a Web endpoint</span></span>

1. <span data-ttu-id="cfac9-109">Defina un contrato de servicios mediante una interfaz marcada con los atributos <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> y <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cfac9-109">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="cfac9-110">De forma predeterminada, <xref:System.ServiceModel.Web.WebInvokeAttribute> asigna las llamadas POST a la operación.</span><span class="sxs-lookup"><span data-stu-id="cfac9-110">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="cfac9-111">Puede, sin embargo, especificar el método HTTP (por ejemplo, HEAD, PUT o DELETE) para asignar a la operación especificando un parámetro “method=”.</span><span class="sxs-lookup"><span data-stu-id="cfac9-111">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="cfac9-112"><xref:System.ServiceModel.Web.WebGetAttribute> no tiene un parámetro “method=” y solo asigna llamadas GET a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="cfac9-112"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="cfac9-113">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="cfac9-113">Implement the service contract.</span></span>

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="cfac9-114">Para hospedar el servicio</span><span class="sxs-lookup"><span data-stu-id="cfac9-114">To host the service</span></span>

1. <span data-ttu-id="cfac9-115">Crear un objeto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="cfac9-115">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. <span data-ttu-id="cfac9-116">Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> al <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cfac9-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > <span data-ttu-id="cfac9-117">Si no agrega un extremo, <xref:System.ServiceModel.Web.WebServiceHost> crea automáticamente un extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cfac9-117">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="cfac9-118"><xref:System.ServiceModel.Web.WebServiceHost> también agrega <xref:System.ServiceModel.Description.WebHttpBehavior> y deshabilita la página de ayuda de HTTP y la funcionalidad GET del lenguaje de descripción de servicios Web (WSDL) para que el extremo de metadatos no interfiera con el extremo HTTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cfac9-118"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>
    >
    >  <span data-ttu-id="cfac9-119">Agregar un punto de conexión que no es SOAP a una dirección URL de"" causa un comportamiento inesperado cuando se intenta llamar a una operación en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="cfac9-119">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="cfac9-120">La razón de esto es el URI del extremo es el mismo que el URI de la página de ayuda (la página que se muestra al ir a la dirección base de un servicio WCF) de escucha.</span><span class="sxs-lookup"><span data-stu-id="cfac9-120">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a WCF service).</span></span>

     <span data-ttu-id="cfac9-121">Para evitar que esto suceda, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cfac9-121">You can do one of the following actions to prevent this from happening:</span></span>

    - <span data-ttu-id="cfac9-122">Siempre especifique un URI que no esté en blanco para un extremo que no sea SOAP.</span><span class="sxs-lookup"><span data-stu-id="cfac9-122">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>

    - <span data-ttu-id="cfac9-123">Desactive la página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="cfac9-123">Turn off the help page.</span></span> <span data-ttu-id="cfac9-124">Esto puede hacerse con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfac9-124">This can be done with the following code:</span></span>

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. <span data-ttu-id="cfac9-125">Abra el host de servicio y espere hasta que el usuario presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="cfac9-125">Open the service host and wait until the user presses ENTER.</span></span>

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     <span data-ttu-id="cfac9-126">Este ejemplo muestra cómo hospedar un servicio de tipo web con una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="cfac9-126">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="cfac9-127">También puede hospedar este tipo de servicios dentro de IIS.</span><span class="sxs-lookup"><span data-stu-id="cfac9-127">You can also host such a service within IIS.</span></span> <span data-ttu-id="cfac9-128">Para ello, especifique la clase <xref:System.ServiceModel.Activation.WebServiceHostFactory> en un archivo .svc como muestra el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="cfac9-128">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>

    ```
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="cfac9-129">Para llamar a las operaciones de servicio asignadas a GET en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="cfac9-129">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="cfac9-130">Abra Internet Explorer y escriba "`http://localhost:8000/EchoWithGet?s=Hello, world!`" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="cfac9-130">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="cfac9-131">La dirección URL contiene la dirección base del servicio (`http://localhost:8000/`), la dirección relativa del punto de conexión (""), la operación de servicio para llamar ("EchoWithGet") y un signo de interrogación seguido de una lista de parámetros con nombre separados por una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="cfac9-131">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-in-code"></a><span data-ttu-id="cfac9-132">Realización de llamadas a operaciones de servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="cfac9-132">To call service operations in code</span></span>

1. <span data-ttu-id="cfac9-133">Cree una instancia de <xref:System.ServiceModel.ChannelFactory%601> dentro de un bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="cfac9-133">Create an instance of <xref:System.ServiceModel.ChannelFactory%601> within a `using` block.</span></span>

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. <span data-ttu-id="cfac9-134">Agregue <xref:System.ServiceModel.Description.WebHttpBehavior> al extremo que <xref:System.ServiceModel.ChannelFactory%601> llamará.</span><span class="sxs-lookup"><span data-stu-id="cfac9-134">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory%601> calls.</span></span>

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. <span data-ttu-id="cfac9-135">Cree el canal y llame al servicio.</span><span class="sxs-lookup"><span data-stu-id="cfac9-135">Create the channel and call the service.</span></span>

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. <span data-ttu-id="cfac9-136">Cierre el <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="cfac9-136">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a><span data-ttu-id="cfac9-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfac9-137">Example</span></span>

<span data-ttu-id="cfac9-138">A continuación, se muestra una lista de código completa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cfac9-138">The following is the full code listing for this example.</span></span>

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a><span data-ttu-id="cfac9-139">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="cfac9-139">Compiling the code</span></span>

<span data-ttu-id="cfac9-140">Al compilar Service.cs, haga una referencia a System.ServiceModel.dll y a System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="cfac9-140">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfac9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfac9-141">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="cfac9-142">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="cfac9-142">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)