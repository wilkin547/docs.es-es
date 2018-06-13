---
title: 'Cómo: modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6'
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: aef2300ccde12ae224e373ca4e19b4d10b9b4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395023"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Cómo: modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6
En el ejemplo de código siguiente se muestra cómo modificar el archivo de configuración de equipo, *machine.config*, para permitir la compatibilidad con IPv6. El archivo *machine.config* se almacena en la carpeta *%Windir%\Microsoft.NET\Framework* en el directorio donde se ha instalado Windows. Hay un archivo *machine.config* distinto en las carpetas bajo *%Windir%\Microsoft.NET\Framework* para cada versión de .NET Framework instalada en el equipo (por ejemplo, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.  
  
 Para .NET Framework versión 1.1 y anterior, el valor del modificador de la configuración **ipv6 enabled** especifica si los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> devuelven las direcciones de IPv6.  
  
 En la versión 2.0 de .NET Framework y versiones posteriores, si Windows admite IPv6, entonces todos los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>), devolverán las direcciones de IPv6 con una limitación. Los miembros obsoletos de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leerán y reconocerán el valor en el archivo de configuración.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework y versiones posteriores, IPv6 está habilitada de manera predeterminada. Para .NET Framework versión 1.1 y anteriores, IPv6 está deshabilitada de manera predeterminada.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a>Vea también  
 [Direccionamiento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)  
 [Esquema de la configuración de red](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [Elemento \<ipv6> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
