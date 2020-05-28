---
title: Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: 179ccf97ce4f5e2aa3e132db7e77c93259d5e4ac
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144947"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="d1a1f-102">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d1a1f-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="d1a1f-103">Este es uno de los dos temas de procedimientos que muestran los metadatos de publicación para un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d1a1f-103">This is one of two how-to topics that demonstrate publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="d1a1f-104">Hay dos maneras de especificar cómo debería publicar metadatos un servicio: mediante un archivo de configuración y mediante código.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="d1a1f-105">En este tema se muestra cómo publicar metadatos para un servicio mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="d1a1f-106">En este tema se muestra cómo publicar metadatos de forma no segura.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="d1a1f-107">Cualquier cliente puede recuperar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="d1a1f-108">Si necesita que el servicio publique los metadatos de forma segura, consulte [punto de conexión de metadatos seguro personalizado](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="d1a1f-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="d1a1f-109">Para obtener más información sobre la publicación de metadatos en el código, vea [Cómo: publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span><span class="sxs-lookup"><span data-stu-id="d1a1f-109">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="d1a1f-110">La publicación de metadatos permite a los clientes recuperar los metadatos mediante una solicitud GET WS-Transfer o mediante una solicitud HTTP/GET usando la cadena de solicitud `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="d1a1f-111">Para asegurarse de que el código funciona, cree un servicio WCF básico.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-111">To be sure that the code is working, create a basic WCF service.</span></span> <span data-ttu-id="d1a1f-112">Para simplificar, se proporciona un servicio autohospedado básico en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="d1a1f-113">Este servicio es un servicio autohospedado que se configura usando un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="d1a1f-114">El archivo de configuración siguiente sirve de punto de partida.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-114">The following configuration file serves as a starting point.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="d1a1f-115">Publicación de metadatos para un servicio WCF mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d1a1f-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1. <span data-ttu-id="d1a1f-116">Dentro del archivo App.config, después del elemento `</services>` de cierre, cree un elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  

2. <span data-ttu-id="d1a1f-117">En el elemento `<behaviors>`, agregue un elemento `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  

3. <span data-ttu-id="d1a1f-118">Agregue un elemento `<behavior>` al elemento `<serviceBehaviors>` y especifique un valor para el atributo `name` del elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  

4. <span data-ttu-id="d1a1f-119">Agregue un elemento `<serviceMetadata>` al elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="d1a1f-120">Establezca el atributo `httpGetEnabled` en `true` y el atributo `policyVersion` en Policy15.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> <span data-ttu-id="d1a1f-121">`httpGetEnabled` permite que el servicio responda a las solicitudes de metadatos realizadas por una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-121">`httpGetEnabled` allows the service to respond to metadata requests made by an HTTP GET request.</span></span> <span data-ttu-id="d1a1f-122">`policyVersion` indica al servicio que se ajuste a WS-Policy 1.5 al generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-122">`policyVersion` tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  

5. <span data-ttu-id="d1a1f-123">Agregue un atributo `behaviorConfiguration` al elemento `<service>` y especifique el atributo `name` del elemento `<behavior>` agregado en el paso 1, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6. <span data-ttu-id="d1a1f-124">Agregue uno o varios elementos `<endpoint>` con el contrato establecido en `IMetadataExchange`, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7. <span data-ttu-id="d1a1f-125">Para los puntos de conexión de metadatos agregados en el paso anterior, establezca el atributo `binding` en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d1a1f-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    - <span data-ttu-id="d1a1f-126">`mexHttpBinding` para la publicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-126">`mexHttpBinding` for HTTP publication.</span></span>  
  
    - <span data-ttu-id="d1a1f-127">`mexHttpsBinding` para la publicación HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-127">`mexHttpsBinding` for HTTPS publication.</span></span>  
  
    - <span data-ttu-id="d1a1f-128">`mexNamedPipeBinding` para la publicación de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-128">`mexNamedPipeBinding` for named pipe publication.</span></span>  
  
    - <span data-ttu-id="d1a1f-129">`mexTcpBinding` para la publicación TCP.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-129">`mexTcpBinding` for TCP publication.</span></span>  
  
8. <span data-ttu-id="d1a1f-130">Para los puntos de conexión de metadatos agregados en un paso anterior, establezca la dirección en:</span><span class="sxs-lookup"><span data-stu-id="d1a1f-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    - <span data-ttu-id="d1a1f-131">Una cadena vacía para utilizar la dirección base de la aplicación host como el punto de publicación si la dirección base es igual que el enlace de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    - <span data-ttu-id="d1a1f-132">Una dirección relativa si la aplicación host tiene una dirección base.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-132">A relative address if the host application has a base address.</span></span>  
  
    - <span data-ttu-id="d1a1f-133">Una dirección absoluta.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="d1a1f-134">Compilación y ejecución de la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="d1a1f-135">Use Internet Explorer para ir a la dirección base del servicio ( `http://localhost:8001/MetadataSample` en este ejemplo) y compruebe que la publicación de metadatos está activada.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-135">Use Internet Explorer to browse to the base address of the service (`http://localhost:8001/MetadataSample` in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="d1a1f-136">Si no, un mensaje en la parte superior de la página resultante muestra: "La publicación de metadatos para este servicio está deshabilitad actualmente".</span><span class="sxs-lookup"><span data-stu-id="d1a1f-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="d1a1f-137">Para usar puntos de conexión predeterminados</span><span class="sxs-lookup"><span data-stu-id="d1a1f-137">To use default endpoints</span></span>  
  
1. <span data-ttu-id="d1a1f-138">Para configurar metadatos en un servicio que usa puntos de conexión predeterminados, especifique el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el archivo de configuración como en el ejemplo anterior, pero no especifique ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="d1a1f-139">El archivo de configuración debería tener el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-139">The configuration file would then look like this.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="d1a1f-140">Dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> con `httpGetEnabled` establecido en `true`, el servicio tiene metadatos de publicación habilitados y como no se agregó ningún punto de conexión explícitamente, el tiempo de ejecución agrega los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="d1a1f-141">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1a1f-141">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1a1f-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1a1f-142">Example</span></span>  
 <span data-ttu-id="d1a1f-143">En el ejemplo de código siguiente se muestra la implementación de un servicio WCF básico y el archivo de configuración que publica los metadatos para el servicio.</span><span class="sxs-lookup"><span data-stu-id="d1a1f-143">The following code example shows the implementation of a basic WCF service and the configuration file that publishes metadata for the service.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1a1f-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1a1f-144">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="d1a1f-145">Procedimiento para hospedar un servicio WCF en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="d1a1f-145">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="d1a1f-146">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="d1a1f-146">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="d1a1f-147">Información general de la arquitectura de metadatos</span><span class="sxs-lookup"><span data-stu-id="d1a1f-147">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="d1a1f-148">Utilización de los metadatos</span><span class="sxs-lookup"><span data-stu-id="d1a1f-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="d1a1f-149">Procedimiento para publicar metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="d1a1f-149">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
