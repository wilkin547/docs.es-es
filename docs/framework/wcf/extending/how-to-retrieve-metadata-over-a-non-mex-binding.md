---
title: 'Cómo: Recuperar metadatos mediante un enlace que no sea MEX'
ms.date: 03/30/2017
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
ms.openlocfilehash: a006795c87a2ae845d03db90dce296692c4339fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186446"
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a>Cómo: Recuperar metadatos mediante un enlace que no sea MEX
En este tema se describe cómo recuperar metadatos de un extremo MEX mediante un enlace que no sea MEX. El código de este ejemplo se basa en el ejemplo Deicuando el punto de conexión de [metadatos seguros personalizado.](../samples/custom-secure-metadata-endpoint.md)  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a>Para recuperar metadatos mediante un enlace que no sea MEX  
  
1. Determine el enlace utilizado por el extremo MEX. Para los servicios de Windows Communication Foundation (WCF), puede determinar el enlace MEX accediendo al archivo de configuración del servicio. En este caso, el enlace de MEX se define en la configuración de servicio siguiente.  
  
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
  
2. En el archivo de configuración del cliente, configure el mismo enlace personalizado. Aquí, el cliente también define un comportamiento `clientCredentials` para proporcionar un certificado que utilizar para autenticarse en el servicio al solicitar metadatos del extremo MEX. Al utilizar Svcutil.exe para solicitar metadatos mediante un enlace personalizado, debería agregar la configuración del extremo MEX al archivo de configuración para Svcutil.exe (Svcutil.exe.config) y el nombre de la configuración del extremo debería coincidir con el esquema del URI de la dirección del extremo MEX, tal y como se muestra en el código siguiente:  
  
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
  
3. Cree un `MetadataExchangeClient` y llame a `GetMetadata`: Hay dos maneras de hacerlo: puede especificar el enlace personalizado mediante configuración o puede especificarlo mediante código, tal y como se muestra en el ejemplo siguiente:  
  
    ```csharp
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
  
4. Cree una clase `WsdlImporter` y llame a `ImportAllEndpoints`, como se muestra en el código siguiente.  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5. En este punto, tiene una colección de puntos de conexión de servicio. Para obtener más información acerca de la importación de metadatos, vea [Cómo: Importar metadatos en puntos](../feature-details/how-to-import-metadata-into-service-endpoints.md)de conexión de servicio .  
  
## <a name="see-also"></a>Consulte también

- [Metadatos](../feature-details/metadata.md)
