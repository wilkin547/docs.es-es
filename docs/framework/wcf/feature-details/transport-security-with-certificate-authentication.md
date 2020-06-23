---
title: Seguridad del transporte con autenticación de certificados
description: Obtenga información acerca de cómo usa WFC los certificados para la autenticación de servidor y cliente cuando se usa la seguridad de transporte.
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: 3da1202a5ad3b953470b50dd5924b2ab45f301eb
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244783"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="d1df9-103">Seguridad del transporte con autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="d1df9-103">Transport Security with Certificate Authentication</span></span>

<span data-ttu-id="d1df9-104">En este artículo se describe el uso de certificados X. 509 para la autenticación de servidor y cliente cuando se usa la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="d1df9-104">This article discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="d1df9-105">Para obtener más información sobre los certificados X.509, vea [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates) (Certificados X.509 de clave pública).</span><span class="sxs-lookup"><span data-stu-id="d1df9-105">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="d1df9-106">Los certificados los debe emitir una entidad de certificación, que suele ser un emisor de certificados de terceros.</span><span class="sxs-lookup"><span data-stu-id="d1df9-106">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="d1df9-107">En un dominio de servidor de Windows, se pueden usar los Servicios de servidor de certificados de Active Directory para emitir certificados a los equipos cliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="d1df9-107">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="d1df9-108">En este escenario, el servicio se hospeda bajo Internet Information Services (IIS) que se configura con capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="d1df9-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="d1df9-109">El servidor se configura con un certificado SSL (X.509) para que los clientes puedan comprobar la identidad del servidor.</span><span class="sxs-lookup"><span data-stu-id="d1df9-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="d1df9-110">El cliente también se configura con un certificado X.509 que permite que el servicio compruebe la identidad del cliente.</span><span class="sxs-lookup"><span data-stu-id="d1df9-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="d1df9-111">El cliente debe confiar en el certificado del servidor y este, en el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="d1df9-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="d1df9-112">La mecánica real de cómo el servicio y el cliente comprueba la identidad de los demás está fuera del ámbito de este artículo.</span><span class="sxs-lookup"><span data-stu-id="d1df9-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this article.</span></span> <span data-ttu-id="d1df9-113">Para obtener más información, consulte [firma digital](https://en.wikipedia.org/wiki/Digital_signature) en Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="d1df9-113">For more information, see [Digital Signature](https://en.wikipedia.org/wiki/Digital_signature) on Wikipedia.</span></span>
  
 <span data-ttu-id="d1df9-114">En este escenario se implementa un patrón de mensaje de solicitud/respuesta como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="d1df9-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="d1df9-115">![Transferencia segura mediante certificados](media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="d1df9-115">![Secure transfer using certificates](media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="d1df9-116">Para obtener más información sobre el uso de un certificado con un servicio, consulte [trabajar con certificados](working-with-certificates.md) y [Cómo: configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d1df9-116">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="d1df9-117">En la tabla siguiente se describen las distintas características del escenario.</span><span class="sxs-lookup"><span data-stu-id="d1df9-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="d1df9-118">Característica</span><span class="sxs-lookup"><span data-stu-id="d1df9-118">Characteristic</span></span>|<span data-ttu-id="d1df9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1df9-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d1df9-120">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="d1df9-120">Security Mode</span></span>|<span data-ttu-id="d1df9-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="d1df9-121">Transport</span></span>|  
|<span data-ttu-id="d1df9-122">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d1df9-122">Interoperability</span></span>|<span data-ttu-id="d1df9-123">Con clientes y servicios de servicios Web existentes</span><span class="sxs-lookup"><span data-stu-id="d1df9-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="d1df9-124">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="d1df9-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="d1df9-125">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="d1df9-125">Authentication (Client)</span></span>|<span data-ttu-id="d1df9-126">Sí (mediante un certificado SSL)</span><span class="sxs-lookup"><span data-stu-id="d1df9-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="d1df9-127">Sí (mediante un certificado X.509)</span><span class="sxs-lookup"><span data-stu-id="d1df9-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="d1df9-128">Integridad de datos</span><span class="sxs-lookup"><span data-stu-id="d1df9-128">Data Integrity</span></span>|<span data-ttu-id="d1df9-129">Yes</span><span class="sxs-lookup"><span data-stu-id="d1df9-129">Yes</span></span>|  
|<span data-ttu-id="d1df9-130">Confidencialidad de los datos</span><span class="sxs-lookup"><span data-stu-id="d1df9-130">Data Confidentiality</span></span>|<span data-ttu-id="d1df9-131">Yes</span><span class="sxs-lookup"><span data-stu-id="d1df9-131">Yes</span></span>|  
|<span data-ttu-id="d1df9-132">Transporte</span><span class="sxs-lookup"><span data-stu-id="d1df9-132">Transport</span></span>|<span data-ttu-id="d1df9-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d1df9-133">HTTPS</span></span>|  
|<span data-ttu-id="d1df9-134">Enlace</span><span class="sxs-lookup"><span data-stu-id="d1df9-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="d1df9-135">Configurar el servicio</span><span class="sxs-lookup"><span data-stu-id="d1df9-135">Configure the Service</span></span>  
 <span data-ttu-id="d1df9-136">Puesto que el servicio de este escenario se hospeda bajo IIS, se configura con un archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="d1df9-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="d1df9-137">El siguiente archivo web.config muestra cómo configurar la clase <xref:System.ServiceModel.WSHttpBinding> para usar la seguridad de transporte y las credenciales de cliente de X.509.</span><span class="sxs-lookup"><span data-stu-id="d1df9-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
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
  
## <a name="configure-the-client"></a><span data-ttu-id="d1df9-138">Configurar el cliente</span><span class="sxs-lookup"><span data-stu-id="d1df9-138">Configure the Client</span></span>  
 <span data-ttu-id="d1df9-139">El cliente se puede configurar en código o en un archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="d1df9-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="d1df9-140">En el ejemplo siguiente se muestra cómo configurar el cliente en código.</span><span class="sxs-lookup"><span data-stu-id="d1df9-140">The following example shows how to configure the client in code.</span></span>  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
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
  
 <span data-ttu-id="d1df9-141">O bien, puede configurar el cliente en un archivo App.config como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1df9-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d1df9-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1df9-142">See also</span></span>

- [<span data-ttu-id="d1df9-143">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="d1df9-143">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="d1df9-144">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d1df9-144">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
