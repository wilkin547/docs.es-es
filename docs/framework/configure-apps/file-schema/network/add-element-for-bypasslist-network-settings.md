---
title: "&lt;add&gt; (Elemento para bypasslist, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento), bypasslist"
  - "<bypasslist>, add (elemento)"
  - "add (elemento), bypasslist"
  - "bypasslist, add (elemento)"
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;add&gt; (Elemento para bypasslist, Configuraci&#243;n de red)
Agrega una dirección IP o un nombre DNS a la lista de omisión del proxy.  
  
## Sintaxis  
  
```  
  
      <add   
   address = "regular expression"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|**address**|Expresión regular que describe una dirección IP o un nombre DNS.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un servidor proxy.|  
  
## Comentarios  
 El elemento `add` inserta expresiones regulares que describen direcciones IP o nombres de servidores DNS en la lista de direcciones que omiten un servidor proxy.  
  
 El valor del atributo `address` debería ser una expresión regular que describiera un conjunto de direcciones IP o nombres de host.  
  
 Se debería tener cuidado al especificar una expresión regular para este elemento.  La expresión regular "\[a\-z\]\+\\.contoso\\.com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.  Para coincidir sólo con un host del dominio contoso.com, utilice un delimitador \("$"\): "\[a\-z\]\+\\.contoso\\.com$".  
  
 Para obtener más información sobre expresiones regulares, vea .[Expresiones regulares de .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se agregan dos direcciones a la lista de omisión.  La primera omite el proxy para todos los servidores del dominio contoso.com y la segunda omite el proxy para todos los servidores cuya dirección IP empiece por 192.168.  
  
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