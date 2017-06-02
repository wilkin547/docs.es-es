---
title: "&lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84179d77-825d-44b9-895a-ab08e7aa044d
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;webHttpBinding&gt;
Define un elemento de enlace que se utiliza para configurar los extremos para los servicios Web [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que responden a las solicitudes HTTP en lugar de los mensajes SOAP.  
  
## Sintaxis  
  
```  
  
<webHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxBufferSize="integer"  
        maxReceivedMessageSize="Integer"  
        name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        useDefaultWebProxy="Boolean">  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        <security mode="None/Transport/TransportCredentialOnly">  
            <transport clientCredentialType =   
                 "Basic/Certificate/Digest/None/Ntlm/Windows"  
                  proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                  realm="string" />  
        </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</webHttpBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|allowCookies|Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.  El valor predeterminado es false.<br /><br /> Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.  De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.|  
|bypassProxyOnLocal|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.  De manera predeterminada, es `false`.|  
|closeTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.  Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.  El valor predeterminado es 00:01:00.|  
|hostnameComparisonMode|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.  Este atributo es del tipo <xref:System.ServiceModel.HostnameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.  El valor predeterminado es <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|  
|maxBufferPoolSize|Entero que especifica el tamaño máximo del grupo de búferes para este enlace.  El valor predeterminado es 524.288 bytes \(512x1024\).  En muchas partes de Windows Communication Foundation \(WCF\) se utilizan búferes.  Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.  Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.  Así se evita la sobrecarga al crear y destruir búferes.|  
|maxBufferSize|Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.  El valor predeterminado es 524.288 \(0x80000\) bytes.|  
|maxReceivedMessageSize|Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.  El remitente de un mensaje que supere este límite recibirá un error.  El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.  El valor predeterminado es 65536. **Note:**  No basta con aumentar este valor en el modo compatible de ASP.NET.  También debe aumentar el valor de `httpRuntime` \(vea [Elemento httpRuntime \(Esquema de configuración de ASP.NET\)](http://msdn.microsoft.com/es-es/e9b81350-8aaf-47cc-9843-5f7d0c59f369)\).|  
|name|Cadena que contiene el nombre de configuración del enlace.  Este valor debe ser único porque se usa como identificación del enlace.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.  Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.  El valor predeterminado es 00:01:00.|  
|proxyAddress|Un URI que especifica la dirección del proxy HTTP.  Si `useSystemWebProxy` es `true`, este valor debe ser `null`.  De manera predeterminada, es `null`.|  
|receiveTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.  Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.  El valor predeterminado es 00:01:00.|  
|sendTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.  Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.  El valor predeterminado es 00:01:00.|  
|transferMode.|Un valor <xref:System.ServiceModel.TransferMode> que indica si el servicio configurado con el enlace utiliza modos de transmisión o de almacenamiento en búfer \(o ambos\) de transferencia de mensaje.  De manera predeterminada, es `Buffered`.|  
|useDefaultWebProxy|Valor de tipo booleano que especifica si se utiliza el proxy HTTP del sistema configurado automáticamente.  De manera predeterminada, es `true`.|  
|writeEncoding|Especifica la codificación de caracteres que se usa para el texto del mensaje.  Los valores válidos son los siguientes:<br /><br /> UnicodeFffeTextEncoding: codificación de BigEndian de Unicode.<br /><br /> Utf16TextEncoding: codificación de 16 bits.<br /><br /> Utf8TextEncoding: codificación de 8 bits.<br /><br /> El valor predeterminado es Utf8TextEncoding.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Define restricciones en la complejidad de los mensajes POX que pueden ser procesados por los extremos configurados con este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Define la configuración de seguridad del enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.WebHttpSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlaces\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## Comentarios  
 El modelo de programación web de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] permite a los programadores exponer los servicios Web de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] a través de las solicitudes HTTP que usan la mensajería de estilo "XML sin formato" \(POX\) en lugar de la mensajería basada en SOAP.  Para comunicar con un servicio mediante las solicitudes HTTP, un extremo del servicio se debe configurar con [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) que tiene \<WebHttpBehavior\> adjunto.  
  
 La compatibilidad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] para la sindicación e integración de ASP.AJAX se encuentra compilada en el Modelo de programación web.  Para obtener más información sobre este modelo, vea [Modelo de programación de web HTTP de WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## Vea también  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 [Modelo de programación de web HTTP de WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)