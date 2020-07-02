---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621443"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="d2a81-101">Servicios de WCF que usan NETTCP con seguridad SSL y autenticación de certificados MD5</span><span class="sxs-lookup"><span data-stu-id="d2a81-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="d2a81-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2a81-102">Details</span></span>

<span data-ttu-id="d2a81-103">.NET Framework 4.6 añade TLS 1.1 y TLS 1.2 a la lista de protocolos predeterminados de SSL de WCF.</span><span class="sxs-lookup"><span data-stu-id="d2a81-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="d2a81-104">Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o una versión posterior instalada, se usa TLS 1.2 para la negociación. TLS 1.2 no admite la autenticación de certificados MD5.</span><span class="sxs-lookup"><span data-stu-id="d2a81-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="d2a81-105">Como consecuencia, si un cliente utiliza un certificado MD5, el cliente de WCF no se podrá conectar al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d2a81-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d2a81-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d2a81-106">Suggestion</span></span>

<span data-ttu-id="d2a81-107">Puede evitar este problema para que el cliente WCF pueda conectarse a un servidor WCF realizando alguno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="d2a81-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="d2a81-108">Actualizar el certificado para que no use el algoritmo MD5.</span><span class="sxs-lookup"><span data-stu-id="d2a81-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="d2a81-109">Esta es la solución recomendada.</span><span class="sxs-lookup"><span data-stu-id="d2a81-109">This is the recommended solution.</span></span>
- <span data-ttu-id="d2a81-110">Si la vinculación no se configura dinámicamente en el código fuente, actualice el archivo de configuración de la aplicación para usar TLS 1.1 o una versión anterior del protocolo.</span><span class="sxs-lookup"><span data-stu-id="d2a81-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="d2a81-111">Esto le permite seguir usando un certificado con el algoritmo hash MD5.</span><span class="sxs-lookup"><span data-stu-id="d2a81-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="d2a81-112">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="d2a81-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="d2a81-113">El archivo de configuración siguiente realiza esta tarea:</span><span class="sxs-lookup"><span data-stu-id="d2a81-113">The following configuration file does this:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- <span data-ttu-id="d2a81-114">Si la vinculación se configura dinámicamente en el código fuente, actualice la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> para usar TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versión anterior del protocolo en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="d2a81-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="d2a81-115">Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.</span><span class="sxs-lookup"><span data-stu-id="d2a81-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="d2a81-116">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d2a81-116">Name</span></span>    | <span data-ttu-id="d2a81-117">Valor</span><span class="sxs-lookup"><span data-stu-id="d2a81-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="d2a81-118">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d2a81-118">Scope</span></span>   | <span data-ttu-id="d2a81-119">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d2a81-119">Minor</span></span>   |
| <span data-ttu-id="d2a81-120">Versión</span><span class="sxs-lookup"><span data-stu-id="d2a81-120">Version</span></span> | <span data-ttu-id="d2a81-121">4.6</span><span class="sxs-lookup"><span data-stu-id="d2a81-121">4.6</span></span>     |
| <span data-ttu-id="d2a81-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2a81-122">Type</span></span>    | <span data-ttu-id="d2a81-123">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d2a81-123">Runtime</span></span> |
