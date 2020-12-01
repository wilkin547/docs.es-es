---
title: 'Mitigación: protocolos TLS'
description: Obtenga información sobre el impacto y la mitigación de los cambios del protocolo TLS a partir de .NET Framework 4.6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 492315d43043c83d17eab330e8d589d1cffe7ad2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273872"
---
# <a name="mitigation-tls-protocols"></a>Mitigación: protocolos TLS

A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> pueden usar uno de los siguientes tres protocolos: Tls1.0, Tls1.1 o Tls 1.2. No se admite el protocolo SSL 3.0 ni el cifrado RC4.  
  
## <a name="impact"></a>Impacto  

 Este cambio afecta a:  
  
- Cualquier aplicación que use SSL para comunicarse con un servidor HTTPS o con un servidor de socket mediante cualquiera de los siguientes tipos: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> y <xref:System.Net.Security.SslStream>.  
  
- Cualquier aplicación del lado servidor que no se pueda actualizar para admitir Tls1.0, Tls1.1 o Tls 1.2.  
  
## <a name="mitigation"></a>Mitigación  

 La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls 1.0, Tls1.1 o Tls1.2. Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext> para descartar esta característica de cualquiera de estas dos maneras:  
  
- Mediante programación, usando un fragmento de código similar al siguiente:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Dado que el objeto <xref:System.Net.ServicePointManager> se inicializa una sola vez, la primera cosa que debe hacer la aplicación es definir esta configuración de compatibilidad.  
  
- Mediante la adición de la línea siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Debe tener en cuenta que no se recomienda excluir el comportamiento predeterminado, ya que hace que la aplicación sea menos segura.  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
