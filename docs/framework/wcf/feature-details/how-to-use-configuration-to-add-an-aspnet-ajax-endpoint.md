---
title: Uso de la configuración para agregar un punto de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 5314bb000371ee2d3eef2576e1edfa455aa65b90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184832"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="12344-102">Uso de la configuración para agregar un punto de conexión AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="12344-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="12344-103">Windows Communication Foundation (WCF) permite crear un servicio que hace que un ASP.NET punto de conexión habilitado para AJAX esté disponible que se puede llamar desde JavaScript en un sitio Web cliente.</span><span class="sxs-lookup"><span data-stu-id="12344-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="12344-104">Para crear un punto de conexión de este tipo, puede usar un archivo de configuración, como con todos los demás extremos de Windows Communication Foundation (WCF), o usar un método que no requiera ningún elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="12344-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="12344-105">En este tema se muestra el enfoque de configuración.</span><span class="sxs-lookup"><span data-stu-id="12344-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="12344-106">La parte del procedimiento que permite que el punto de conexión de servicio <xref:System.ServiceModel.WebHttpBinding> se convierta en ASP.NET habilitado para AJAX consiste en configurar el punto de conexión para usar y agregar el [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento del punto de conexión de>enableWebScript.</span><span class="sxs-lookup"><span data-stu-id="12344-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="12344-107">Después de configurar el punto de conexión, los pasos para implementar y hospedar el servicio son similares a los utilizados por cualquier servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="12344-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="12344-108">Para obtener un ejemplo de trabajo, consulte el [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="12344-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="12344-109">Para obtener más información acerca de cómo configurar un ASP.NET extremo de AJAX sin usar la configuración, consulte Cómo: agregar un ASP.NET punto de [conexión de AJAX sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="12344-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
## <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="12344-110">Para crear un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="12344-110">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="12344-111">Defina un contrato de servicio WCF <xref:System.ServiceModel.ServiceContractAttribute> básico con una interfaz marcada con el atributo.</span><span class="sxs-lookup"><span data-stu-id="12344-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="12344-112">Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="12344-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="12344-113">Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="12344-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="12344-114">Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="12344-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
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
  
3. <span data-ttu-id="12344-115">Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="12344-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="12344-116">Creación de un punto de conexión de AJAX de ASP.NET para el servicio.</span><span class="sxs-lookup"><span data-stu-id="12344-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="12344-117">Cree una configuración de [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento y especifique el comportamiento de>enableWebScript para ASP.NET puntos de conexión habilitados para AJAX del servicio.</span><span class="sxs-lookup"><span data-stu-id="12344-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
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
  
2. <span data-ttu-id="12344-118">Cree un punto de conexión para el servicio que utilice el <xref:System.ServiceModel.WebHttpBinding> y el comportamiento de AJAX de ASP.NET definido en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="12344-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
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
  
## <a name="to-host-the-service-in-iis"></a><span data-ttu-id="12344-119">Hospedaje del servicio en IIS</span><span class="sxs-lookup"><span data-stu-id="12344-119">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="12344-120">Para hospedar el servicio en IIS, cree un nuevo archivo denominado service con extensión .svc en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12344-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="12344-121">Edite este archivo agregando la información de directiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="12344-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="12344-122">Por ejemplo, el contenido del archivo de servicio para el ejemplo de `CalculatorService` contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="12344-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="12344-123">Para obtener más información acerca del hospedaje en IIS, vea [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="12344-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="to-call-the-service"></a><span data-ttu-id="12344-124">Realización de llamadas al servicio</span><span class="sxs-lookup"><span data-stu-id="12344-124">To call the service</span></span>  
  
1. <span data-ttu-id="12344-125">El punto de conexión se configura en una dirección vacía relativa al archivo .svc, por lo\<que el servicio ya está disponible `Add` y se puede invocar enviando solicitudes a service.svc/ operación>, por ejemplo, service.svc/Add para la operación.</span><span class="sxs-lookup"><span data-stu-id="12344-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="12344-126">Puede utilizarlo introduciendo la URL del punto de conexión en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="12344-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="12344-127">Para obtener un ejemplo, consulte el [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="12344-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12344-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12344-128">See also</span></span>

- [<span data-ttu-id="12344-129">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="12344-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="12344-130">Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="12344-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
