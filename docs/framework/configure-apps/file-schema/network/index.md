---
title: Esquema de la configuración de red
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 0f5d762a2b688bebcb7c027be6c639b6d64c069d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664115"
---
# <a name="network-settings-schema"></a>Esquema de la configuración de red
La configuración de red especifica cómo se conecta .NET Framework a Internet. En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<system.Net> (configuración de red)](system-net-element-network-settings.md).  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[Elemento \<authenticationModules> (configuración de red)](authenticationmodules-element-network-settings.md)|Especifica los módulos usados para autenticar solicitudes de Internet.|  
|[Elemento \<connectionManagement> (configuración de red)](connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a hosts de Internet.|  
|[Elemento \<defaultProxy> (configuración de red)](defaultproxy-element-network-settings.md)|Especifica el servidor proxy usado para las solicitudes HTTP a Internet.|  
|[Elemento \<mailSettings> (configuración de red)](mailsettings-element-network-settings.md)|Contiene la configuración de opciones de envío de correo.|  
|[Elemento \<requestCaching> (configuración de red)](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
|[Elemento \<webRequestModules> (configuración de red)](webrequestmodules-element-network-settings.md)|Especifica los módulos usados para solicitar información de hosts de Internet.|  
  
 La configuración de URI especifica la manera en que .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI). En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<Uri> (configuración de URI)](uri-element-uri-settings.md).  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[Elemento \<idn> (Configuración de URI)](idn-element-uri-settings.md)|Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.|  
|[Elemento \<iriParsing> (Configuración de URI)](iriparsing-element-uri-settings.md)|Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.|  
|[Elemento \<schemeSettings> (configuración de URI)](schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
## <a name="see-also"></a>Vea también

- [Configuración de aplicaciones de Internet](../../../network-programming/configuring-internet-applications.md)
- [Esquema de los archivos de configuración](../index.md)
