---
title: Seguridad del transporte con autenticación de certificados
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- vb
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
caps.latest.revision: 20
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 19b54739d82fe7363319211d3f753416e0966aed
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="transport-security-with-certificate-authentication"></a>Seguridad del transporte con autenticación de certificados
En este tema se tratan los certificados X.509 para la autenticación de servidores y clientes cuando se usa la seguridad de transporte. Para obtener más información acerca de X.509 certificados Consulte [certificados de clave pública X.509](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx). Certificados deben emitirse por una entidad de certificación, que a menudo es un emisor de terceros de certificados. En un dominio de servidor de Windows, se pueden usar los Servicios de servidor de certificados de Active Directory para emitir certificados a los equipos cliente del dominio. Para obtener más información, consulte [servicios de Certificate Server de Windows 2008 R2](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409). En este escenario, el servicio se hospeda bajo Internet Information Services (IIS) que se configura con capa de sockets seguros (SSL). El servidor se configura con un certificado SSL (X.509) para que los clientes puedan comprobar la identidad del servidor. El cliente también se configura con un certificado X.509 que permite que el servicio compruebe la identidad del cliente. El cliente debe confiar en el certificado del servidor y este, en el certificado del cliente. Los mecanismos reales de comprobación por parte del servicio y del cliente de sus respectivas identidades no se trata en el ámbito de este tema. Para obtener más información, consulte [la firma Digital en Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).  
  
 En este escenario se implementa un patrón de mensaje de solicitud/respuesta como se muestra en el siguiente diagrama.  
  
 ![Uso de certificados de transferencia segura](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")  
  
 Para obtener más información sobre el uso de un certificado con un servicio, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md). En la tabla siguiente se describen las distintas características del escenario.  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Transporte|  
|Interoperabilidad|Con clientes y servicios de servicios Web existentes|  
|Autenticación (servidor)<br /><br /> Autenticación (cliente)|Sí (mediante un certificado SSL)<br /><br /> Sí (mediante un certificado X.509)|  
|Integridad de datos|Sí|  
|Confidencialidad de los datos|Sí|  
|Transporte|HTTPS|  
|Enlaces|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a>Configurar el servicio  
 Puesto que el servicio de este escenario se hospeda bajo IIS, se configura con un archivo web.config. El siguiente archivo web.config muestra cómo configurar la clase <xref:System.ServiceModel.WSHttpBinding> para usar la seguridad de transporte y las credenciales de cliente de X.509.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a>Configurar el cliente  
 El cliente se puede configurar en código o en un archivo app.config. En el ejemplo siguiente se muestra cómo configurar el cliente en código.  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 O bien, puede configurar el cliente en un archivo App.config como se muestra en el siguiente ejemplo:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
