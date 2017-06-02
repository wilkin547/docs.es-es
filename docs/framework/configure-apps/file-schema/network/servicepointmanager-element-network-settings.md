---
title: "&lt;servicePointManager&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<servicePointManager> (elemento)"
  - "servicePointManager (elemento)"
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;servicePointManager&gt; (Elemento, Configuraci&#243;n de red)
Configura las conexiones a los recursos de red.  
  
## Sintaxis  
  
```  
  
      <servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`checkCertificateName`|Especifica si el sistema tiene que comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de utilizar el certificado.  El valor predeterminado es `true`.|  
|`checkCertificateRevocationList`|Especifica si el sistema tiene que comprobar si se ha revocado el certificado antes de utilizarlo.  El valor predeterminado es `false`.|  
|`dnsRefreshTimeout`|Especifica durante cuánto tiempo tienen que almacenarse en caché las resoluciones del Servicio de nombres de dominio \(DNS\) con la opción de operación por turnos DNS \(en milisegundos\).  El valor predeterminado es 120.000 milisegundos \(dos minutos\).|  
|`enableDnsRoundRobin`|Especifica si las resoluciones DNS de nombres de host con varias direcciones de Protocolo de Internet \(IP\) tienen que devolver todas las direcciones o simplemente la primera.  El valor predeterminado es `false`.|  
|`encryptionPolicy`|Especifica la directiva de cifrado aplicada a una sesión SSL\/TLS en una instancia de <xref:System.Net.ServicePointManager> .  Los valores posibles son equivalentes a los valores de la enumeración <xref:System.Net.Security.EncryptionPolicy>.  El uso de <xref:System.Security.Authentication.CipherAlgorithmType> se requiere cuando la directiva de cifrado se establece en `NoEncryption`.  El valor predeterminado es `RequireEncryption`.|  
|`expect100Continue`|Especifica si los métodos POST tienen que esperar una respuesta `100-continue` del servidor.  El valor predeterminado es `true`.|  
|`useNagleAlgorithm`|Especifica si las conexiones controladas por el administrador de puntos de servicio utilizan el algoritmo de Nagle.  El valor predeterminado es `true`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[Valores](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Vea también  
 <xref:System.Net.ServicePointManager>   
 <xref:System.Net.Security.EncryptionPolicy>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)