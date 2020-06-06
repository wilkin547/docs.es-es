---
title: Elemento <mailSettings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089231"
---
# <a name="mailsettings-element-network-settings"></a>Elemento \<mailSettings> (configuración de red)
Configura opciones de envío de correo.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[\<smtp>(Elemento, configuración de red)](smtp-element-network-settings.md)|Configura opciones de Protocolo simple de transporte de correo.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[\<system.Net>(Elemento, configuración de red)](system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.Mail.SmtpClient>
- [Esquema de la configuración de red](index.md)
