---
title: 'Mitigación: Servicios WCF y autenticación de certificados'
description: Aprenda a mitigar los problemas de autenticación de certificados derivados de los cambios en la lista predeterminada del protocolo SSL de WCF en .NET Framework 4.6.
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: b6460e58bb32151003430d6573c4bcf1b514081b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475377"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="c594e-103">Mitigación: Servicios WCF y autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="c594e-103">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="c594e-104">.NET Framework 4.6 agrega TLS 1.1 y TLS 1.2 a la lista predeterminada de protocolos SSL de WCF.</span><span class="sxs-lookup"><span data-stu-id="c594e-104">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="c594e-105">Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o posterior instalado, se usa TLS 1.2 para la negociación.</span><span class="sxs-lookup"><span data-stu-id="c594e-105">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="c594e-106">Impacto</span><span class="sxs-lookup"><span data-stu-id="c594e-106">Impact</span></span>

<span data-ttu-id="c594e-107">TLS 1.2 no admite la autenticación de certificado MD5.</span><span class="sxs-lookup"><span data-stu-id="c594e-107">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="c594e-108">Como resultado, si un cliente emplea un certificado SSL que usa MD5 para el algoritmo hash, el cliente WCF no se puede conectar al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c594e-108">As a result, if a customer uses an SSL certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="c594e-109">Para más información, vea [Mitigación: Servicios WCF y autenticación de certificados](mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c594e-109">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="c594e-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="c594e-110">Mitigation</span></span>

<span data-ttu-id="c594e-111">Puede evitar este problema para que el cliente WCF pueda conectarse a un servidor WCF realizando alguno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="c594e-111">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="c594e-112">Actualizar el certificado para que no use el algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="c594e-112">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="c594e-113">Esta es la solución recomendada.</span><span class="sxs-lookup"><span data-stu-id="c594e-113">This is the recommended solution.</span></span>

- <span data-ttu-id="c594e-114">Si la vinculación no se configura dinámicamente en el código fuente, actualice el archivo de configuración de la aplicación para usar TLS 1.1 o una versión anterior del protocolo.</span><span class="sxs-lookup"><span data-stu-id="c594e-114">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="c594e-115">Esto le permite seguir usando un certificado con el algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="c594e-115">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c594e-116">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="c594e-116">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="c594e-117">El archivo de configuración siguiente realiza esta tarea:</span><span class="sxs-lookup"><span data-stu-id="c594e-117">The following configuration file does this:</span></span>

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
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="c594e-118">Si la vinculación se configura dinámicamente en el código fuente, actualice la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> para usar TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versión anterior del protocolo en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="c594e-118">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c594e-119">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="c594e-119">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="c594e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c594e-120">See also</span></span>

- [<span data-ttu-id="c594e-121">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c594e-121">Application compatibility</span></span>](application-compatibility.md)
