---
title: "Habilitar y deshabilitar IPv6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Habilitar y deshabilitar IPv6
Para utilizar el protocolo IPv6, asegúrese de que está ejecutando una versión del sistema operativo que admita IPv6 y asegúrese de que el sistema operativo y las clases de red está configurado correctamente.  
  
## Pasos de configuración  
 La tabla siguiente se muestran varias configuraciones  
  
|¿El sistema operativo IPv6\-enabled?|¿La conexión de red ordena IPv6\-enabled?|Descripción|  
|------------------------------------------|-----------------------------------------------|-----------------|  
|No|No|Puede analizar las direcciones de IPv6.|  
|No|Sí|Puede analizar las direcciones de IPv6.|  
|Sí|No|Puede analizar las direcciones de IPv6 y resolver las direcciones de IPv6 mediante obsoleto no marcado de los métodos de resolución de nombres.|  
|Sí|Sí|Puede analizar y resolver las direcciones de IPv6 que utilicen todos los métodos incluidos los marcó obsoleto.|  
  
 Tenga en cuenta que para habilitar la compatibilidad con IPv6 para todas las clases del espacio de nombres System.Net, debe modificar el archivo de configuración del equipo o el archivo de configuración de la aplicación.  El archivo de configuración para una aplicación tiene prioridad sobre el archivo de configuración del equipo.  
  
 Para obtener un ejemplo de cómo modificar el archivo de configuración del equipo, *machine.config*, para habilitar la compatibilidad Ipv6 consulta, [Cómo: Modifique el archivo de configuración del equipo para habilitar la compatibilidad Ipv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  Además, asegúrese de que la compatibilidad de IPv6 habilitado para el sistema operativo.  
  
 .NET Framework tiene un modificador de configuración establecido en un archivo de configuración como sigue  
  
```  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 Para.NET Framework versión 1,1 y anterior, el valor del modificador de la configuración de **ipv6 enabled** especifica si los miembros de la clase de <xref:System.Net.Dns?displayProperty=fullName> devuelven las direcciones de IPv6.  
  
 En la versión 2,0 de .NET Framework y versiones posteriores, si Windows admite IPv6, los miembros de la clase de <xref:System.Net.Dns?displayProperty=fullName> , \(por ejemplo, el método de <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> \), devolverá las direcciones de IPv6 con una limitación.  Miembros obsoletos DNS <xref:System.Net.Dns?displayProperty=fullName> \(por ejemplo, el método de <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> \) leerán y reconocerán el valor en el archivo de configuración por el valor habilitado ipv6.  
  
## Vea también  
 [Protocolo de Internet versión 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)   
 [Esquema de la configuración de red](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)