---
title: Cómo agregar un extremo AJAX de ASP.NET sin usar la configuración
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9935e2a7738796fff9a037b09237a6acbf7bf988
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185130"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="d38c6-102">Cómo agregar un extremo AJAX de ASP.NET sin usar la configuración</span><span class="sxs-lookup"><span data-stu-id="d38c6-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="d38c6-103">Windows Communication Foundation (WCF) permite crear un servicio que expone un extremo habilitado para ASP.NET AJAX que se puede llamar desde JavaScript en un sitio Web cliente.</span><span class="sxs-lookup"><span data-stu-id="d38c6-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="d38c6-104">Para crear este tipo de extremo, puede usar un archivo de configuración, como con todos los otros extremos de WCF, o utilizar un método que no requiera ningún elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="d38c6-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="d38c6-105">En este tema se muestra el segundo enfoque.</span><span class="sxs-lookup"><span data-stu-id="d38c6-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="d38c6-106">Para crear servicios con puntos de conexión de AJAX de ASP.NET sin configuración, Internet Information Services (IIS) debe hospedar los servicios.</span><span class="sxs-lookup"><span data-stu-id="d38c6-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="d38c6-107">Para activar un ASP.NET punto de <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> conexión AJAX mediante este enfoque, especifique el parámetro como Factory en la [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva ServiceHost en el archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="d38c6-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="d38c6-108">Este generador personalizado es el componente que configura automáticamente un punto de conexión de AJAX de ASP.NET para que se le pueda llamar desde JavaScript en un sitio web del cliente.</span><span class="sxs-lookup"><span data-stu-id="d38c6-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="d38c6-109">Para obtener un ejemplo de trabajo, vea el [servicio AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d38c6-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="d38c6-110">Para obtener un resumen de cómo configurar un ASP.NET punto de conexión de AJAX mediante elementos de configuración, consulte [Cómo: usar la configuración para agregar un ASP.NET punto](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)de conexión de AJAX .</span><span class="sxs-lookup"><span data-stu-id="d38c6-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="d38c6-111">Para crear un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="d38c6-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="d38c6-112">Defina un contrato de servicio WCF <xref:System.ServiceModel.ServiceContractAttribute> básico con una interfaz marcada con el atributo.</span><span class="sxs-lookup"><span data-stu-id="d38c6-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="d38c6-113">Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d38c6-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="d38c6-114">Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="d38c6-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="d38c6-115">Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="d38c6-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="d38c6-116">Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d38c6-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="d38c6-117">Hospedaje del servicio en Internet Information Services sin configuración</span><span class="sxs-lookup"><span data-stu-id="d38c6-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="d38c6-118">Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d38c6-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="d38c6-119">Edite este archivo agregando la información de directiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio.</span><span class="sxs-lookup"><span data-stu-id="d38c6-119">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="d38c6-120">Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva ServiceHost para configurar automáticamente un ASP.NET extremo AJAX.</span><span class="sxs-lookup"><span data-stu-id="d38c6-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="d38c6-121">Compile el servicio y llámelo desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="d38c6-121">Build the service and call it from the client.</span></span> <span data-ttu-id="d38c6-122">Internet Information Services (IIS) activa el servicio cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="d38c6-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="d38c6-123">Para obtener más información acerca del hospedaje en IIS, vea [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="d38c6-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="d38c6-124">Realización de llamadas al servicio</span><span class="sxs-lookup"><span data-stu-id="d38c6-124">To call the service</span></span>  
  
1. <span data-ttu-id="d38c6-125">El punto de conexión se configura en una dirección vacía relativa al archivo .svc, por lo\<que el servicio ya está disponible `Add` y se puede invocar enviando solicitudes a service.svc/ operación>, por ejemplo, service.svc/Add para la operación.</span><span class="sxs-lookup"><span data-stu-id="d38c6-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="d38c6-126">Puede utilizarlo introduciendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d38c6-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="d38c6-127">Para obtener un ejemplo, vea el [servicio AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d38c6-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d38c6-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d38c6-128">Example</span></span>  
  
 <span data-ttu-id="d38c6-129">El punto de conexión configurado automáticamente se crea en una dirección vacía relativa a la URL base.</span><span class="sxs-lookup"><span data-stu-id="d38c6-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="d38c6-130">También se puede agregar y utilizar un archivo de configuración con este enfoque.</span><span class="sxs-lookup"><span data-stu-id="d38c6-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="d38c6-131">Si el archivo de configuración contiene las definiciones de punto de conexión, estos puntos de conexión se agregan al punto de conexión configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d38c6-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="d38c6-132">Por ejemplo, service.svc usa <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> y el directorio del servicio contiene un archivo Web.config que define un punto de conexión para el mismo servicio mediante el elemento <xref:System.ServiceModel.BasicHttpBinding> de la dirección relativa de "soap".</span><span class="sxs-lookup"><span data-stu-id="d38c6-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="d38c6-133">En este caso, el servicio contiene dos puntos de conexión: uno en service.svc (que responde a las solicitudes de AJAX de ASP.NET) y otro en service.svc/soap (que responde a las solicitudes SOAP).</span><span class="sxs-lookup"><span data-stu-id="d38c6-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="d38c6-134">Si el archivo de configuración define un punto de conexión en una dirección relativa vacía y se utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, se produce una excepción y el servicio no puede iniciarse.</span><span class="sxs-lookup"><span data-stu-id="d38c6-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="d38c6-135">No puede utilizar la configuración para modificar los valores en el punto de conexión configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d38c6-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="d38c6-136">Si se debe modificar algún valor (como una cuota del lector), no debe utilizar el enfoque sin configuración quitando el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> del archivo .svc y creando una entrada de configuración para el extremo.</span><span class="sxs-lookup"><span data-stu-id="d38c6-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="d38c6-137">Si su servicio requiere el modo de compatibilidad de ASP.NET; por ejemplo, si utiliza la clase <xref:System.Web.HttpContext> o los mecanismos de autorización de ASP.NET, se sigue requiriendo un archivo de configuración para activar este modo.</span><span class="sxs-lookup"><span data-stu-id="d38c6-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="d38c6-138">El elemento de configuración necesario es el [ \<elemento de>serviceHostingEnvironment,](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) que se debe agregar de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="d38c6-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="d38c6-139">Para obtener más información, vea el [temas Servicios WCF y ASP.NET.](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)</span><span class="sxs-lookup"><span data-stu-id="d38c6-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="d38c6-140">La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es una clase derivada de <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="d38c6-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="d38c6-141">Para obtener una explicación detallada del mecanismo de generador de host de servicio, vea el [tema Extender hospedaje mediante ServiceHostFactory.](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)</span><span class="sxs-lookup"><span data-stu-id="d38c6-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38c6-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d38c6-142">See also</span></span>

- [<span data-ttu-id="d38c6-143">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d38c6-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="d38c6-144">Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="d38c6-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
