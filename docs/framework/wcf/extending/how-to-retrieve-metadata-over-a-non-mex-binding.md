---
title: Procedimiento Recuperar metadatos mediante un enlace que no sea - MEX
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: ac0a7d979e6b86933c4acd88b1a2fa11ba5bc991
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689560"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c816f-102">Procedimiento Recuperar metadatos mediante un enlace que no sea - MEX</span><span class="sxs-lookup"><span data-stu-id="c816f-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="c816f-103">En este tema se describe cómo recuperar metadatos de un punto de conexión MEX mediante un enlace que no sea MEX.</span><span class="sxs-lookup"><span data-stu-id="c816f-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="c816f-104">El código en este ejemplo se basa en el [extremo de metadatos personalizada Secure](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c816f-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c816f-105">Para recuperar metadatos mediante un enlace que no sea MEX</span><span class="sxs-lookup"><span data-stu-id="c816f-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1.  <span data-ttu-id="c816f-106">Determine el enlace utilizado por el punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="c816f-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="c816f-107">Para los servicios de Windows Communication Foundation (WCF), puede determinar el enlace MEX obteniendo acceso al archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="c816f-107">For Windows Communication Foundation (WCF) services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="c816f-108">En este caso, el enlace de MEX se define en la configuración de servicio siguiente.</span><span class="sxs-lookup"><span data-stu-id="c816f-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
    ```xml  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2.  <span data-ttu-id="c816f-109">En el archivo de configuración del cliente, configure el mismo enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c816f-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="c816f-110">Aquí, el cliente también define un comportamiento `clientCredentials` para proporcionar un certificado que utilizar para autenticarse en el servicio al solicitar metadatos del punto de conexión MEX.</span><span class="sxs-lookup"><span data-stu-id="c816f-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="c816f-111">Al utilizar Svcutil.exe para solicitar metadatos mediante un enlace personalizado, debería agregar la configuración del punto de conexión MEX al archivo de configuración para Svcutil.exe (Svcutil.exe.config) y el nombre de la configuración del punto de conexión debería coincidir con el esquema del URI de la dirección del punto de conexión MEX, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c816f-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="c816f-112">Cree un `MetadataExchangeClient` y llame a `GetMetadata`:</span><span class="sxs-lookup"><span data-stu-id="c816f-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="c816f-113">Hay dos maneras de hacerlo: puede especificar el enlace personalizado mediante configuración o puede especificarlo mediante código, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c816f-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4.  <span data-ttu-id="c816f-114">Cree una clase `WsdlImporter` y llame a `ImportAllEndpoints`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c816f-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  <span data-ttu-id="c816f-115">En este punto, tiene una colección de puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="c816f-115">At this point, you have a collection of service endpoints.</span></span> <span data-ttu-id="c816f-116">Para obtener más información sobre la importación de metadatos, vea [Cómo: Importar los metadatos en los puntos de conexión de servicio](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="c816f-116">For more information about importing metadata, see [How to: Import Metadata into Service Endpoints](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c816f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c816f-117">See also</span></span>
- [<span data-ttu-id="c816f-118">Metadatos</span><span class="sxs-lookup"><span data-stu-id="c816f-118">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
