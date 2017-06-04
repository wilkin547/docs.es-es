---
title: "&lt;bypasslist&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist> (elemento)"
  - "bypasslist (elemento)"
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;bypasslist&gt; (Elemento, Configuraci&#243;n de red)
Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un servidor proxy.  
  
## Sintaxis  
  
```  
  
      <bypasslist>   
</bypasslist>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[agregar](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Agrega una dirección IP o un nombre DNS a la lista de omisión del proxy.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Borra la lista de omisión.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto \(HTTP\).|  
  
## Comentarios  
 La lista de omisiones contiene expresiones regulares que describen los identificadores URI a los que tiene acceso directo una instancia de <xref:System.Net.WebRequest>, en lugar de utilizar el servidor proxy.  
  
 Se debería tener cuidado al especificar una expresión regular para este elemento.  La expresión regular "\[a\-z\]\+\\.contoso\\.com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.  Para coincidir sólo con un host del dominio contoso.com, utilice un delimitador \("$"\): "\[a\-z\]\+\\.contoso\\.com$".  
  
 Para obtener más información sobre expresiones regulares, vea .[Expresiones regulares de .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se agregan dos direcciones a la lista de omisión.  La primera omite el proxy para todos los servidores del dominio contoso.com y la segunda omite el proxy para todos los servidores cuyas direcciones IP empiecen por 192.168.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)