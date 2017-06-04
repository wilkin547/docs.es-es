---
title: "&lt;httpWebRequest&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<httpWebRequest> (elemento)"
  - "httpWebRequest (elemento)"
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# &lt;httpWebRequest&gt; (Elemento, Configuraci&#243;n de red)
Personaliza los parámetros de solicitud Web.  
  
## Sintaxis  
  
```  
  
      <httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`maximumResponseHeadersLength`|Especifica la longitud máxima de un encabezado de respuesta \(en kilobytes\).  El valor predeterminado es 64.  Un valor de \-1 indica que no va a imponerse ningún límite de tamaño a los encabezados de respuesta.|  
|`maximumErrorResponseLength`|Especifica la longitud máxima de una respuesta de error \(en kilobytes\).  El valor predeterminado es 64.  Un valor de \-1 indica que no va a imponerse ningún límite de tamaño a la respuesta de error.|  
|`maximumUnauthorizedUploadLength`|Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado \(en bytes\).  El valor predeterminado es \-1.  Un valor \-1 indica que no se impondrá límite de tamaño a la carga.|  
|`useUnsafeHeaderParsing`|Especifica si está habilitado el análisis de encabezados que no son seguros.  El valor predeterminado es `false`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
 De forma predeterminada, .NET Framework aplica inflexiblemente la especificación RFC 2616 para el análisis de identificadores uniformes de recursos \(URI\).  Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, que harán que el método <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> produzca una excepción <xref:System.Net.WebException>.  Si **useUnsafeHeaderParsing** se establece en **true**, el método <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=fullName> no producirá ninguna excepción en este caso. Sin embargo, la aplicación será vulnerable a distintas formas de ataques de análisis de identificadores uniformes de recursos \(URI\).  La mejor solución es modificar el servidor para que la respuesta no incluya caracteres de control.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo especificar una longitud de encabezado máxima de mayor tamaño que el habitual.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)