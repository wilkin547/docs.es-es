---
title: '&lt;SMTP&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 362c5ba479c845a8183fe705e72ea3a12fb7a94c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195650"
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;SMTP&gt; elemento (configuración de red)
Configura el formato de entrega, el método de entrega y de dirección para el envío de mensajes de correo electrónico.  
  
 \<configuration>  
\<System.NET >  
\<mailSettings >  
\<SMTP >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`deliveryFormat`|Especifica el formato de entrega de mensajes de correo electrónico salientes. Los valores aceptables son SevenBit e International.|  
|`deliveryMethod`|Especifica el método de entrega de mensajes de correo electrónico. Los valores aceptables son Network, PickupDirectoryFromIis y SpecifiedPickupDirectory.|  
|`from`|Especifica la desde la dirección de correo saliente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).|  
|`network`|Configura las opciones de red de un servidor SMTP externo.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Elemento \<mailSettings> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Configura opciones de envío de correo.|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente especifica los parámetros SMTP adecuados para enviar correo electrónico utilizando las credenciales de red predeterminadas.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
- <xref:System.Net.Mail.SmtpDeliveryFormat>  
- <xref:System.Net.Mail.SmtpDeliveryMethod>  
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
