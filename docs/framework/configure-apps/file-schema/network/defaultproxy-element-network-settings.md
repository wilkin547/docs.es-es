---
title: "&lt;defaultProxy&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultProxy> (elemento)"
  - "defaultProxy (elemento)"
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;defaultProxy&gt; (Elemento, Configuraci&#243;n de red)
Configura el servidor proxy de Protocolo de transferencia de hipertexto \(HTTP\).  
  
## Sintaxis  
  
```  
  
        <defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false"  
  <bypasslist> … </bypasslist>  
  <proxy> … </proxy>  
  <module> … </module>  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|`enabled`|Especifica si se usa un proxy web.  El valor predeterminado es `true`.|  
|`useDefaultCredentials`|Especifica si se usan las credenciales predeterminadas de este host para tener acceso al proxy web.  El valor predeterminado es `false`.|  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen direcciones que no usan el proxy.|  
|[módulo](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|Agrega un nuevo módulo proxy a la aplicación.|  
|[proxy](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|Define un servidor proxy.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[system.  net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## Comentarios  
 Si el elemento defaultProxy está vacío, se usará la configuración de proxy de Internet Explorer.  Este comportamiento es diferente de la versión 1.1 de .NET Framework.  
  
 Se produce una excepción si el elemento [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) especifica un tipo no público, el tipo no deriva de la clase <xref:System.Net.IWebProxy>, se produjo una excepción en el constructor predeterminado de este objeto o se produjo una excepción al recuperar el proxy predeterminado especificado por el sistema.  La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa del error.  
  
## Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local y para contoso.com.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)