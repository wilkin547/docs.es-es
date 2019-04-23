---
title: 'Mitigación: Servicios WCF y autenticación de certificados'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdacf5fc4a5c73fc60df961432089ee65dd0cfaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079544"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="2c3a5-102">Mitigación: Servicios WCF y autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="2c3a5-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="2c3a5-103">.NET Framework 4.6 agrega TLS 1.1 y TLS 1.2 a la lista predeterminada de protocolos SSL de WCF.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="2c3a5-104">Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o posterior instalado, se usa TLS 1.2 para la negociación.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2c3a5-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="2c3a5-105">Impact</span></span>  
 <span data-ttu-id="2c3a5-106">TLS 1.2 no admite la autenticación de certificado MD5.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="2c3a5-107">Como resultado, si un cliente utiliza un certificado SSL que utiliza MD5 para el algoritmo hash, el cliente WCF no se puede conectar al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="2c3a5-108">Para más información, vea [Mitigación: Servicios WCF y autenticación de certificados](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2c3a5-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="2c3a5-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="2c3a5-109">Mitigation</span></span>  
 <span data-ttu-id="2c3a5-110">Puede evitar este problema para que el cliente WCF pueda conectarse a un servidor WCF realizando alguno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="2c3a5-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
-   <span data-ttu-id="2c3a5-111">Actualizar el certificado para que no use el algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="2c3a5-112">Esta es la solución recomendada.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-112">This is the recommended solution.</span></span>  
  
-   <span data-ttu-id="2c3a5-113">Si la vinculación no se configura dinámicamente en el código fuente, actualice el archivo de configuración de la aplicación para usar TLS 1.1 o una versión anterior del protocolo.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="2c3a5-114">Esto le permite seguir usando un certificado con el algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2c3a5-115">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="2c3a5-116">El archivo de configuración siguiente realiza esta tarea:</span><span class="sxs-lookup"><span data-stu-id="2c3a5-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="2c3a5-117">Si la vinculación se configura dinámicamente en el código fuente, actualice la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> para usar TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versión anterior del protocolo en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2c3a5-118">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="2c3a5-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3a5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c3a5-119">See also</span></span>

- [<span data-ttu-id="2c3a5-120">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="2c3a5-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
