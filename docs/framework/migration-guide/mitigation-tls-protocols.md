---
title: 'Mitigación: protocolos TLS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457839"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="1ec12-102">Mitigación: protocolos TLS</span><span class="sxs-lookup"><span data-stu-id="1ec12-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="1ec12-103">A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> solo pueden usar uno de los tres protocolos siguientes: Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="1ec12-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="1ec12-104">No se admite el protocolo SSL 3.0 ni el cifrado RC4.</span><span class="sxs-lookup"><span data-stu-id="1ec12-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1ec12-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="1ec12-105">Impact</span></span>  
 <span data-ttu-id="1ec12-106">Este cambio afecta a:</span><span class="sxs-lookup"><span data-stu-id="1ec12-106">This change affects:</span></span>  
  
- <span data-ttu-id="1ec12-107">Cualquier aplicación que use SSL para comunicarse con un servidor HTTPS o con un servidor de socket mediante cualquiera de los siguientes tipos: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> y <xref:System.Net.Security.SslStream>.</span><span class="sxs-lookup"><span data-stu-id="1ec12-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="1ec12-108">Cualquier aplicación del lado servidor que no se pueda actualizar para admitir Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="1ec12-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1ec12-109">Mitigación</span><span class="sxs-lookup"><span data-stu-id="1ec12-109">Mitigation</span></span>  
 <span data-ttu-id="1ec12-110">La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls 1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="1ec12-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="1ec12-111">Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext> para descartar esta característica de cualquiera de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="1ec12-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="1ec12-112">Mediante programación, usando un fragmento de código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ec12-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="1ec12-113">Dado que el objeto <xref:System.Net.ServicePointManager> se inicializa una sola vez, la primera cosa que debe hacer la aplicación es definir esta configuración de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="1ec12-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="1ec12-114">Agregando la siguiente línea a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="1ec12-114">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="1ec12-115">Debe tener en cuenta que no se recomienda excluir el comportamiento predeterminado, ya que hace que la aplicación sea menos segura.</span><span class="sxs-lookup"><span data-stu-id="1ec12-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec12-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ec12-116">See also</span></span>

- [<span data-ttu-id="1ec12-117">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1ec12-117">Application compatibility</span></span>](application-compatibility.md)
