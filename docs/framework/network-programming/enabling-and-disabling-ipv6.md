---
title: Habilitar y deshabilitar IPv6
description: Siga estos pasos de configuración para habilitar el uso del protocolo IPv6, que incluyen la modificación del archivo de configuración del equipo o de la aplicación.
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 00a59e25731d276d81ba74af086b3e19e68d5fad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250546"
---
# <a name="enabling-and-disabling-ipv6"></a>Habilitar y deshabilitar IPv6

Para usar el protocolo IPv6, asegúrese de que está ejecutando una versión del sistema operativo que admita IPv6 y asegúrese de que el sistema operativo y las clases de red están configurados correctamente.  
  
## <a name="configuration-steps"></a>Pasos de la configuración  

 En la tabla siguiente se muestran varias configuraciones  
  
|¿El sistema operativo está habilitado para IPv6?|¿Las clases de red están habilitadas para IPv6?|Descripción|  
|-------------------------------------|---------------------------------------|-----------------|  
|No|No|Puede analizar las direcciones de IPv6.|  
|No|Sí|Puede analizar las direcciones de IPv6.|  
|Sí|No|Puede analizar las direcciones de IPv6 y resolver las direcciones de IPv6 mediante métodos de resolución de nombres que no se hayan marcado como obsoletos.|  
|Sí|Sí|Puede analizar y resolver las direcciones de IPv6 con todos los métodos, incluidos los que se hayan marcado como obsoletos.|  
  
 Tenga en cuenta que para habilitar la compatibilidad con IPv6 para todas las clases del espacio de nombres System.Net, debe modificar el archivo de configuración del equipo o el archivo de configuración de la aplicación. El archivo de configuración de la aplicación tiene prioridad sobre el archivo de configuración del equipo.  
  
 Para obtener un ejemplo de cómo modificar el archivo de configuración de equipo, *machine.config*, para permitir la compatibilidad con Ipv6, vea [Cómo: Modificar el archivo de configuración de equipo para habilitar la compatibilidad con Ipv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md). Además, asegúrese de que la compatibilidad con IPv6 está habilitada para el sistema operativo.  
  
 .NET Framework tiene un modificador de configuración establecido en un archivo de configuración como se muestra a continuación:  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 Para .NET Framework versión 1.1 y anterior, el valor del modificador de la configuración **ipv6 enabled** especifica si los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> devuelven las direcciones de IPv6.  
  
 En la versión 2.0 de .NET Framework y versiones posteriores, si Windows admite IPv6, entonces los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>), devolverán las direcciones de IPv6 con una limitación. Los miembros obsoletos del DNS <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leerán y reconocerán el valor en el archivo de configuración para la configuración habilitada para IPv6.  
  
## <a name="see-also"></a>Vea también

- [Protocolo de Internet versión 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
- [Esquema de la configuración de red](../configure-apps/file-schema/network/index.md)
- [Elemento \<ipv6> (configuración de red)](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
