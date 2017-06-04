---
title: "Configuraci&#243;n de proxy | Microsoft Docs"
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
helpviewer_keywords: 
  - "servidores proxy adaptable"
  - "Internet, configuración de proxy"
  - "Recursos de red"
  - "red, configuración de proxy"
  - "Conexión de red"
  - "servidores proxy"
  - "servidores proxy, configurar"
  - "servidores proxy estáticos"
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Configuraci&#243;n de proxy
Un servidor proxy controla las solicitudes de cliente de recursos.  Un proxy puede devolver un recurso solicitado de su caché o reenviar la solicitud al servidor donde reside el recurso.  Los servidores proxy pueden mejorar el rendimiento de la red al reducir el número de solicitudes enviadas a servidores remotos.  Los servidores proxy también pueden usarse para restringir el acceso a los recursos.  
  
## Servidores proxy adaptables  
 En .NET Framework, los servidores proxy son de dos tipos: adaptable y estático.  Los servidores proxy adaptables ajustan su configuración cuando cambia la configuración de red.  Por ejemplo, si un usuario de un portátil inicia una conexión de red de acceso telefónico, un proxy adaptable podría reconocer este cambio, descubrir y ejecutar su nuevo script de configuración y ajustar su configuración de manera adecuada.  
  
 Los servidores proxy adaptables se configuran por medio de un script de configuración \(vea [Detección automática de proxy](../../../docs/framework/network-programming/automatic-proxy-detection.md)\).  El script genera un conjunto de protocolos de aplicación y un proxy para cada protocolo.  
  
 Varias opciones controlan cómo se ejecuta el script de configuración.  Puede especificar los siguientes elementos:  
  
-   Con qué frecuencia se descarga y se ejecuta el script de configuración.  
  
-   Cuánto tiempo debe esperar a que se descargue el script.  
  
-   Qué credenciales debe usar el sistema deben para tener acceso al proxy.  
  
-   Qué credenciales debe usar el sistema para descargar el script de configuración.  
  
 Los cambios en el entorno de red pueden requerir que el sistema use un nuevo conjunto de servidores proxy.  Si una conexión de red deja de funcionar o se inicializa una nueva conexión de red, el sistema debe descubrir el origen adecuado del script de configuración en el nuevo entorno y ejecutar el script nuevo.  
  
 La siguiente tabla muestra las opciones de configuración para un proxy adaptable.  
  
|Parámetro, atributo o propiedad del archivo de configuración|Descripción|  
|------------------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|Tiempo transcurrido en segundos entre las descargas de scripts.|  
|`scriptDownloadTimeout`|Tiempo de espera \(en segundos\) para que se descargue el script.|  
|`useDefaultCredentials` o <xref:System.Net.WebProxy.UseDefaultCredentials>|Controla si el sistema usa las credenciales de red predeterminadas para tener acceso a un proxy.|  
|`useDefaultCredentialForScriptDownload`|Controla si el sistema usa las credenciales de red predeterminadas para descargar el script de configuración.|  
|`usesystemdefaults`|Controla si la configuración de proxy estática \(dirección de proxy, lista de omisión y omitir para las direcciones locales\) debe leerse de la configuración de proxy de Internet Explorer para el usuario.  Si este valor se establece en "true", se usará la configuración de proxy estática de Internet Explorer.<br /><br /> Si este valor es "false" o no se establece, la configuración de proxy estática se pueden especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.  Este valor debe establecerse en "false" o no establecerse para que se habiliten los servidores proxy adaptables.|  
  
 En el ejemplo siguiente se muestra una configuración típica de proxy adaptable.  
  
```  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## Servidores proxy estáticos  
 Los servidores proxy estáticos se suelen configurar explícitamente por medio de una aplicación o cuando una aplicación o el sistema invoca un archivo de configuración.  Los servidores proxy estáticos son útiles en las redes en las que la topología cambia con poca frecuencia, como un equipo de escritorio conectado a una red corporativa.  
  
 Varias opciones controlan el funcionamiento de un proxy estático.  Puede especificar los siguientes elementos:  
  
-   La dirección del proxy.  
  
-   Si debe omitirse el proxy para direcciones locales.  
  
-   Si debe omitirse el proxy para un conjunto de direcciones.  
  
 En la siguiente tabla se muestran las opciones de configuración de un proxy estático.  
  
|Parámetro, atributo o propiedad del archivo de configuración|Descripción|  
|------------------------------------------------------------------|-----------------|  
|`proxyaddress` o <xref:System.Net.WebProxy.Address>|La dirección de proxy que se va a usar.|  
|`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal>|Controla si se omite el proxy para direcciones locales.|  
|`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList>|Describe, con expresiones regulares, un conjunto de direcciones que omiten el proxy.|  
|`usesystemdefaults`|Controla si la configuración de proxy estática \(dirección de proxy, lista de omisión y omitir para las direcciones locales\) debe leerse de la configuración de proxy de Internet Explorer para el usuario.  Si este valor se establece en "true", se usará la configuración de proxy estática de Internet Explorer.  En .NET Framework 2.0, cuando este valor se establece en "true", la configuración de proxy de Internet Explorer no se reemplaza por otros parámetros de proxy del archivo de configuración.  En .NET Framework 1.1, la configuración de proxy de Internet Explorer puede reemplazarse por otra configuración de proxy en el archivo de configuración.<br /><br /> Si este valor es "false" o no se establece, la configuración de proxy estática se pueden especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.  Este valor debe establecerse en "false" o no establecerse para que se habiliten los servidores proxy adaptables.|  
  
 En el ejemplo siguiente se muestra una configuración típica de proxy estático.  
  
```  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## Vea también  
 <xref:System.Net.WebProxy>   
 <xref:System.Net.GlobalProxySelection>   
 [Detección automática de proxy](../../../docs/framework/network-programming/automatic-proxy-detection.md)