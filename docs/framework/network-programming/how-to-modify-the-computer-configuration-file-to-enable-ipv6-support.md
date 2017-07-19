---
title: "C&#243;mo: modificar el archivo de configuraci&#243;n de equipo para habilitar la compatibilidad con IPv6 | Microsoft Docs"
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
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# C&#243;mo: modificar el archivo de configuraci&#243;n de equipo para habilitar la compatibilidad con IPv6
Las escrituras en el siguiente ejemplo de código cómo modificar el archivo de configuración del equipo, *machine.config*, para habilitar la compatibilidad con IPv6.  El archivo *machine.config* se almacena en la carpeta de *%Windir%\\Microsoft.NET\\Framework* en el directorio donde Windows se instaló.  Hay un archivo *machine.config* independiente en carpetas con *%Windir%\\Microsoft.NET\\Framework* para cada versión de .NET Framework instalada en el equipo \(por ejemplo, *C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config*\).  
  
 Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.  
  
 Para.NET Framework versión 1,1 y anterior, el valor del modificador de la configuración de **ipv6 enabled** especifica si los miembros de la clase de <xref:System.Net.Dns?displayProperty=fullName> devuelven las direcciones de IPv6.  
  
 En la versión 2,0 de .NET Framework y versiones posteriores, si Windows admite IPv6, después todos los miembros de la clase de <xref:System.Net.Dns?displayProperty=fullName> \(por ejemplo, el método de <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> \), devolverá las direcciones de IPv6 con una limitación.  Miembros obsoletos de la clase de <xref:System.Net.Dns?displayProperty=fullName> \(por ejemplo, el método de <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> \) leerán y reconocerán el valor en el archivo de configuración.  
  
> [!NOTE]
>  En la versión 2,0 de .NET Framework y versiones posteriores, IPv6 está habilitada de forma predeterminada.  Para.NET Framework versión 1,1 y anteriores, IPv6 está deshabilitada de forma predeterminada.  
  
## Ejemplo  
  
```  
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
  
## Vea también  
 [Direccionamiento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [Esquema de la configuración de red](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)