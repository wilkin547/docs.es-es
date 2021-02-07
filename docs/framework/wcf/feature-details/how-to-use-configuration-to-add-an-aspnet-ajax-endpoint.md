---
description: 'Más información acerca de cómo: usar la configuración para agregar un punto de conexión de ASP.NET AJAX'
title: Procedimiento para usar la configuración para agregar un punto de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 629df635e9b19148db317a2d953bed9034556cd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734352"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="a8dc8-103">Procedimiento para usar la configuración para agregar un punto de conexión AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a8dc8-103">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>

<span data-ttu-id="a8dc8-104">Windows Communication Foundation (WCF) le permite crear un servicio que hace que un punto de conexión habilitado para ASP.NET AJAX esté disponible al que se puede llamar desde JavaScript en un sitio web del cliente.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-104">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="a8dc8-105">Para crear este tipo de punto de conexión, puede usar un archivo de configuración, como con todos los demás extremos de Windows Communication Foundation (WCF), o bien usar un método que no requiera ningún elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-105">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="a8dc8-106">En este tema se muestra el enfoque de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-106">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="a8dc8-107">La parte del procedimiento que permite que el punto de conexión de servicio se convierta en ASP.NET AJAX habilitado consiste en configurar el punto de conexión para que utilice <xref:System.ServiceModel.WebHttpBinding> y para agregar el [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-107">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="a8dc8-108">Después de configurar el punto de conexión, los pasos para implementar y hospedar el servicio son similares a los utilizados por cualquier servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-108">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="a8dc8-109">Para obtener un ejemplo práctico, vea el [servicio Ajax mediante http post](../samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc8-109">For a working example, see the [AJAX Service Using HTTP POST](../samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="a8dc8-110">Para obtener más información sobre cómo configurar un punto de conexión de ASP.NET AJAX sin usar la configuración, vea [Cómo: agregar un punto de conexión de AJAX de ASP.net sin usar la configuración](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc8-110">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
## <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="a8dc8-111">Para crear un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="a8dc8-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="a8dc8-112">Defina un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="a8dc8-113">Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="a8dc8-114">Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="a8dc8-115">Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. <span data-ttu-id="a8dc8-116">Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="a8dc8-117">Creación de un punto de conexión de AJAX de ASP.NET para el servicio.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-117">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="a8dc8-118">Cree una configuración de comportamiento y especifique el [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) comportamiento de los puntos de conexión habilitados para ASP.net Ajax del servicio.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-118">Create a behavior configuration and specify the [\<enableWebScript>](../../configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="a8dc8-119">Cree un punto de conexión para el servicio que utilice el <xref:System.ServiceModel.WebHttpBinding> y el comportamiento de AJAX de ASP.NET definido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-119">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>
    ```  
  
## <a name="to-host-the-service-in-iis"></a><span data-ttu-id="a8dc8-120">Hospedaje del servicio en IIS</span><span class="sxs-lookup"><span data-stu-id="a8dc8-120">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="a8dc8-121">Para hospedar el servicio en IIS, cree un nuevo archivo denominado service con extensión .svc en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-121">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="a8dc8-122">Edite este archivo agregando la información de directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-122">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="a8dc8-123">Por ejemplo, el contenido del archivo de servicio para el ejemplo de `CalculatorService` contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a8dc8-123">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```aspx-csharp
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="a8dc8-124">Para obtener más información sobre el hospedaje en IIS, consulte [How to: host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc8-124">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="to-call-the-service"></a><span data-ttu-id="a8dc8-125">Realización de llamadas al servicio</span><span class="sxs-lookup"><span data-stu-id="a8dc8-125">To call the service</span></span>  
  
1. <span data-ttu-id="a8dc8-126">El punto de conexión se configura en una dirección vacía relativa al archivo. SVC, por lo que el servicio ahora está disponible y se puede invocar enviando solicitudes a Service. SVC/ \<operation> -por ejemplo, Service. SVC/Add para la `Add` operación.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-126">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="a8dc8-127">Puede utilizarlo introduciendo la URL del punto de conexión en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a8dc8-127">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="a8dc8-128">Para obtener un ejemplo, vea el [servicio Ajax mediante http post](../samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc8-128">For an example, see the [AJAX Service Using HTTP POST](../samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8dc8-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8dc8-129">See also</span></span>

- [<span data-ttu-id="a8dc8-130">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a8dc8-130">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="a8dc8-131">Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="a8dc8-131">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
