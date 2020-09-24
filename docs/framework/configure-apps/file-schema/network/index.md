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
ms.openlocfilehash: 8071fcfcdb16b6e71d8d7af05a704d8842b3e963
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158921"
---
# <a name="network-settings-schema"></a>Esquema de la configuración de red

La configuración de red especifica cómo se conecta .NET Framework a Internet.

La \<system.net> configuración especifica cómo el .NET Framework se conecta a la red. En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<system.Net> elemento (configuración de red)](system-net-element-network-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<authenticationModules> (configuración de red)](authenticationmodules-element-network-settings.md)|Especifica los módulos usados para autenticar solicitudes de Internet.|  
|[Elemento \<connectionManagement> (configuración de red)](connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a hosts de Internet.|  
|[Elemento \<defaultProxy> (configuración de red)](defaultproxy-element-network-settings.md)|Especifica el servidor proxy usado para las solicitudes HTTP a Internet.|  
|[Elemento \<mailSettings> (configuración de red)](mailsettings-element-network-settings.md)|Contiene la configuración de opciones de envío de correo.|  
|[Elemento \<requestCaching> (configuración de red)](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
|[Elemento \<webRequestModules> (configuración de red)](webrequestmodules-element-network-settings.md)|Especifica los módulos usados para solicitar información de hosts de Internet.|  
  
La \<uri> configuración especifica cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI). En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<uri> elemento (configuración de URI)](uri-element-uri-settings.md).  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<idn> Elemento (configuración de URI)](idn-element-uri-settings.md)|Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.|  
|[\<iriParsing> Elemento (configuración de URI)](iriparsing-element-uri-settings.md)|Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.|  
|[\<schemeSettings> Elemento (configuración de URI)](schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
## <a name="see-also"></a>Vea también

- [Configuración de aplicaciones de Internet](../../../network-programming/configuring-internet-applications.md)
- [Esquema de los archivos de configuración](../index.md)
