---
title: Esquema de la configuración de red
description: Obtenga información acerca del esquema de la configuración de red que especifica cómo el .NET Framework se conecta a Internet y controla los URI.
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
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504581"
---
# <a name="network-settings-schema"></a>Esquema de la configuración de red
La configuración de red especifica cómo se conecta .NET Framework a Internet.

La \<system.net> configuración especifica cómo el .NET Framework se conecta a la red. En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<system.Net> elemento (configuración de red)](system-net-element-network-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<authenticationModules>(Elemento, configuración de red)](authenticationmodules-element-network-settings.md)|Especifica los módulos usados para autenticar solicitudes de Internet.|  
|[\<connectionManagement>(Elemento, configuración de red)](connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a hosts de Internet.|  
|[\<defaultProxy>(Elemento, configuración de red)](defaultproxy-element-network-settings.md)|Especifica el servidor proxy usado para las solicitudes HTTP a Internet.|  
|[\<mailSettings>(Elemento, configuración de red)](mailsettings-element-network-settings.md)|Contiene la configuración de opciones de envío de correo.|  
|[\<requestCaching>(Elemento, configuración de red)](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
|[\<webRequestModules>(Elemento, configuración de red)](webrequestmodules-element-network-settings.md)|Especifica los módulos usados para solicitar información de hosts de Internet.|  
  
La \<uri> configuración especifica cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI). En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<uri> elemento (configuración de URI)](uri-element-uri-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<idn>Elemento (configuración de URI)](idn-element-uri-settings.md)|Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.|  
|[\<iriParsing>Elemento (configuración de URI)](iriparsing-element-uri-settings.md)|Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.|  
|[\<schemeSettings>Elemento (configuración de URI)](schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
## <a name="see-also"></a>Consulte también:

- [Configuración de aplicaciones de Internet](../../../network-programming/configuring-internet-applications.md)
- [Esquema de los archivos de configuración](../index.md)
