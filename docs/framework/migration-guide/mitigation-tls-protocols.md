---
title: 'Mitigación: protocolos TLS'
description: Obtenga información sobre el impacto y la mitigación de los cambios del protocolo TLS a partir de .NET Framework 4.6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: bb5aab3361663d7b5401d7e68688265fbc65b36f
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475364"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="0559c-103">Mitigación: protocolos TLS</span><span class="sxs-lookup"><span data-stu-id="0559c-103">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="0559c-104">A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> pueden usar uno de los siguientes tres protocolos: Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="0559c-104">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="0559c-105">No se admite el protocolo SSL 3.0 ni el cifrado RC4.</span><span class="sxs-lookup"><span data-stu-id="0559c-105">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="0559c-106">Impacto</span><span class="sxs-lookup"><span data-stu-id="0559c-106">Impact</span></span>  
 <span data-ttu-id="0559c-107">Este cambio afecta a:</span><span class="sxs-lookup"><span data-stu-id="0559c-107">This change affects:</span></span>  
  
- <span data-ttu-id="0559c-108">Cualquier aplicación que use SSL para comunicarse con un servidor HTTPS o con un servidor de socket mediante cualquiera de los siguientes tipos: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> y <xref:System.Net.Security.SslStream>.</span><span class="sxs-lookup"><span data-stu-id="0559c-108">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="0559c-109">Cualquier aplicación del lado servidor que no se pueda actualizar para admitir Tls1.0, Tls1.1 o Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="0559c-109">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="0559c-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="0559c-110">Mitigation</span></span>  
 <span data-ttu-id="0559c-111">La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls 1.0, Tls1.1 o Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="0559c-111">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="0559c-112">Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext> para descartar esta característica de cualquiera de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="0559c-112">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="0559c-113">Mediante programación, usando un fragmento de código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0559c-113">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="0559c-114">Dado que el objeto <xref:System.Net.ServicePointManager> se inicializa una sola vez, la primera cosa que debe hacer la aplicación es definir esta configuración de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="0559c-114">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="0559c-115">Mediante la adición de la línea siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="0559c-115">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="0559c-116">Debe tener en cuenta que no se recomienda excluir el comportamiento predeterminado, ya que hace que la aplicación sea menos segura.</span><span class="sxs-lookup"><span data-stu-id="0559c-116">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0559c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0559c-117">See also</span></span>

- [<span data-ttu-id="0559c-118">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0559c-118">Application compatibility</span></span>](application-compatibility.md)
