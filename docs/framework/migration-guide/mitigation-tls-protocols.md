---
title: "Mitigación: protocolos TLS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 254cbd020881cadd33186f8318aca037456c88ff
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# Mitigación: protocolos TLS
A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager?displayProperty=fullName> y <xref:System.Net.Security.SslStream?displayProperty=fullName> pueden usar uno de los siguientes tres protocolos: Tls1.0, Tls1.1 o Tls 1.2. No se admite el protocolo SSL 3.0 ni el cifrado RC4.  
  
## Impacto  
 Este cambio afecta a:  
  
-   Cualquier aplicación que use SSL para comunicarse con un servidor HTTPS o con un servidor de socket mediante cualquiera de los siguientes tipos: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> y <xref:System.Net.Security.SslStream>.  
  
-   Cualquier aplicación del lado servidor que no se pueda actualizar para admitir Tls1.0, Tls1.1 o Tls 1.2.  
  
## Mitigación  
 La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls 1.0, Tls1.1 o Tls1.2. Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext> para descartar esta característica de cualquiera de estas dos maneras:  
  
-   Mediante programación, usando un fragmento de código similar al siguiente:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]  [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Dado que el objeto <xref:System.Net.ServicePointManager> se inicializa una sola vez, la primera cosa que debe hacer la aplicación es definir esta configuración de compatibilidad.  
  
-   Agregando la siguiente línea a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Debe tener en cuenta que no se recomienda excluir el comportamiento predeterminado, ya que hace que la aplicación sea menos segura.  
  
## Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

