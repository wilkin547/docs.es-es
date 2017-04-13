---
title: "&lt;remove&gt; (Elemento para bypasslist, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>, remove (elemento)"
  - "bypasslist, remove (elemento)"
  - "remove (elemento), bypasslist"
  - "remove (elemento), bypasslist"
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;remove&gt; (Elemento para bypasslist, Configuraci&#243;n de red)
Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.  
  
## Sintaxis  
  
```  
  
      <remove   
   name = "regular expression"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`name`|Expresión regular que describe una dirección IP o un nombre DNS.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un servidor proxy.|  
  
## Comentarios  
 El elemento `remove` quita expresiones regulares que describen direcciones IP o nombres de servidores DNS de la lista de direcciones que omiten un servidor proxy.  Las direcciones quedaron definidas anteriormente en el archivo de configuración o en un nivel más alto en la jerarquía de configuración.  
  
 El valor del atributo `name` debería ser una expresión regular que describiera un conjunto de direcciones IP o nombres de host.  
  
 Para obtener más información sobre expresiones regulares, vea .[Expresiones regulares de .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente quita cualquier definición anterior para el dominio adventure\-works.com y, a continuación, agrega el dominio contoso.com a la lista de omisiones.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove name = "[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)