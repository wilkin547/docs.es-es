---
description: 'Más información acerca de cómo: agregar un punto de conexión de ASP.NET AJAX sin usar la configuración'
title: Procedimiento para agregar un punto de conexión AJAX de ASP.NET sin usar la configuración
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 52f572b8da1358911760808688574b6a1ac1bccd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742776"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="ce897-103">Procedimiento para agregar un punto de conexión AJAX de ASP.NET sin usar la configuración</span><span class="sxs-lookup"><span data-stu-id="ce897-103">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>

<span data-ttu-id="ce897-104">Windows Communication Foundation (WCF) le permite crear un servicio que exponga un punto de conexión habilitado para AJAX de ASP.NET al que se pueda llamar desde JavaScript en un sitio web del cliente.</span><span class="sxs-lookup"><span data-stu-id="ce897-104">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="ce897-105">Para crear este tipo de extremo, puede usar un archivo de configuración, como con todos los otros extremos de WCF, o utilizar un método que no requiera ningún elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="ce897-105">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="ce897-106">En este tema se muestra el segundo enfoque.</span><span class="sxs-lookup"><span data-stu-id="ce897-106">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="ce897-107">Para crear servicios con puntos de conexión de AJAX de ASP.NET sin configuración, Internet Information Services (IIS) debe hospedar los servicios.</span><span class="sxs-lookup"><span data-stu-id="ce897-107">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="ce897-108">Para activar un punto de conexión de ASP.NET AJAX mediante este enfoque, especifique <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> como parámetro de generador en la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) en el archivo. SVC.</span><span class="sxs-lookup"><span data-stu-id="ce897-108">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="ce897-109">Este generador personalizado es el componente que configura automáticamente un punto de conexión de AJAX de ASP.NET para que se le pueda llamar desde JavaScript en un sitio web del cliente.</span><span class="sxs-lookup"><span data-stu-id="ce897-109">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="ce897-110">Para obtener un ejemplo práctico, vea el [servicio Ajax sin configuración](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ce897-110">For a working example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="ce897-111">Para obtener una descripción de cómo configurar un punto de conexión de ASP.NET AJAX mediante los elementos de configuración, consulte [Cómo: usar la configuración para agregar un punto de conexión de ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="ce897-111">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="ce897-112">Para crear un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="ce897-112">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="ce897-113">Defina un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="ce897-113">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="ce897-114">Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ce897-114">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="ce897-115">Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce897-115">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="ce897-116">Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="ce897-116">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="ce897-117">Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ce897-117">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="ce897-118">Hospedaje del servicio en Internet Information Services sin configuración</span><span class="sxs-lookup"><span data-stu-id="ce897-118">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="ce897-119">Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce897-119">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="ce897-120">Edite este archivo agregando la información de directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce897-120">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="ce897-121">Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) para configurar automáticamente un punto de conexión de ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="ce897-121">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="ce897-122">Compile el servicio y llámelo desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="ce897-122">Build the service and call it from the client.</span></span> <span data-ttu-id="ce897-123">Internet Information Services (IIS) activa el servicio cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="ce897-123">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="ce897-124">Para obtener más información sobre el hospedaje en IIS, consulte [How to: host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="ce897-124">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="ce897-125">Realización de llamadas al servicio</span><span class="sxs-lookup"><span data-stu-id="ce897-125">To call the service</span></span>  
  
1. <span data-ttu-id="ce897-126">El punto de conexión se configura en una dirección vacía relativa al archivo. SVC, por lo que el servicio ahora está disponible y se puede invocar enviando solicitudes a Service. SVC/ \<operation> -por ejemplo, Service. SVC/Add para la `Add` operación.</span><span class="sxs-lookup"><span data-stu-id="ce897-126">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="ce897-127">Puede utilizarlo introduciendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ce897-127">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="ce897-128">Para obtener un ejemplo, vea el [servicio Ajax sin configuración](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ce897-128">For an example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce897-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce897-129">Example</span></span>  
  
 <span data-ttu-id="ce897-130">El punto de conexión configurado automáticamente se crea en una dirección vacía relativa a la URL base.</span><span class="sxs-lookup"><span data-stu-id="ce897-130">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="ce897-131">También se puede agregar y utilizar un archivo de configuración con este enfoque.</span><span class="sxs-lookup"><span data-stu-id="ce897-131">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="ce897-132">Si el archivo de configuración contiene las definiciones de punto de conexión, estos puntos de conexión se agregan al punto de conexión configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ce897-132">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="ce897-133">Por ejemplo, service.svc usa <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> y el directorio del servicio contiene un archivo Web.config que define un punto de conexión para el mismo servicio mediante el elemento <xref:System.ServiceModel.BasicHttpBinding> de la dirección relativa de "soap".</span><span class="sxs-lookup"><span data-stu-id="ce897-133">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="ce897-134">En este caso, el servicio contiene dos puntos de conexión: uno en service.svc (que responde a las solicitudes de AJAX de ASP.NET) y otro en service.svc/soap (que responde a las solicitudes SOAP).</span><span class="sxs-lookup"><span data-stu-id="ce897-134">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="ce897-135">Si el archivo de configuración define un punto de conexión en una dirección relativa vacía y se utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, se produce una excepción y el servicio no puede iniciarse.</span><span class="sxs-lookup"><span data-stu-id="ce897-135">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="ce897-136">No puede utilizar la configuración para modificar los valores en el punto de conexión configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ce897-136">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="ce897-137">Si se debe modificar algún valor (como una cuota del lector), no debe utilizar el enfoque sin configuración quitando el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> del archivo .svc y creando una entrada de configuración para el extremo.</span><span class="sxs-lookup"><span data-stu-id="ce897-137">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="ce897-138">Si su servicio requiere el modo de compatibilidad de ASP.NET; por ejemplo, si utiliza la clase <xref:System.Web.HttpContext> o los mecanismos de autorización de ASP.NET, se sigue requiriendo un archivo de configuración para activar este modo.</span><span class="sxs-lookup"><span data-stu-id="ce897-138">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="ce897-139">El elemento de configuración requerido es el [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento, que se debe agregar como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="ce897-139">The configuration element required is the [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="ce897-140">Para obtener más información, vea el tema [servicios WCF y ASP.net](wcf-services-and-aspnet.md) .</span><span class="sxs-lookup"><span data-stu-id="ce897-140">For more information, see the [WCF Services and ASP.NET](wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="ce897-141">La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es una clase derivada de <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="ce897-141">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="ce897-142">Para obtener una explicación detallada del mecanismo de fábrica de host de servicio, consulte el tema [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) .</span><span class="sxs-lookup"><span data-stu-id="ce897-142">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce897-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce897-143">See also</span></span>

- [<span data-ttu-id="ce897-144">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce897-144">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="ce897-145">Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="ce897-145">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
