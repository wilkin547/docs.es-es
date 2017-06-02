---
title: "C&#243;mo: Habilitar la detecci&#243;n de repetici&#243;n de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "detección de la reproducción [WCF]"
  - "Seguridad de WCF"
  - "WCF, enlaces personalizados"
  - "WCF, seguridad"
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# C&#243;mo: Habilitar la detecci&#243;n de repetici&#243;n de mensajes
Un ataque de reproducción se produce cuando un atacante copia una secuencia de mensajes entre dos partes y reproduce la secuencia a una o más partes.A menos que se mitigue, los equipos sujetos al ataque procesarán el flujo como mensajes legítimos, generando un intervalo de consecuencias erróneas, como las órdenes redundantes de un elemento.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la detección de la reproducción de mensajes, vea [Detección de la reproducción de mensajes](http://go.microsoft.com/fwlink/?LinkId=88536).  
  
 El procedimiento siguiente muestra varias propiedades que puede usar para controlar la detección de reproducción mediante [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
### Para controlar la detección de reproducción en el cliente utilizando código  
  
1.  Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> para utilizar en <xref:System.ServiceModel.Channels.CustomBinding>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).En el siguiente ejemplo se utiliza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> creado con <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2.  Utilizar la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> para devolver una referencia a la clase <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> y establecer cualquiera de las propiedades siguientes, según corresponda:  
  
    1.  `DetectReplay`.Valor de tipo booleano .Esto rige si el cliente debería detectar las reproducciones del servidor.El valor predeterminado es `true`.  
  
    2.  `MaxClockSkew`.Un valor <xref:System.TimeSpan>.Rige qué sesgo temporal puede tolerar el mecanismo de reproducción entre el cliente y el servidor.El mecanismo de seguridad examina la marca de tiempo enviada y determina si se fue enviada demasiado lejos en el pasado.El valor predeterminado es 5 minutos.  
  
    3.  `ReplayWindow`.Un valor `TimeSpan`.Esto rige cuánto tiempo un mensaje puede vivir en la red después de que el servidor lo envíe \(a través de los intermediarios\) antes de alcanzar el cliente.El cliente realiza el seguimiento de las firmas de los mensajes enviados dentro del `ReplayWindow` último para los propósitos de detección de reproducción.  
  
    4.  `ReplayCacheSize`.Valor de entero.El cliente almacena las firmas del mensaje en una memoria caché.Este valor especifica cuántas firmas que puede almacenar la memoria caché.Si el número de mensajes enviado dentro de la última ventana de reproducción alcanza el límite de la memoria caché, se rechazan los nuevos mensajes hasta que las firmas almacenadas en memoria caché más antiguas alcancen el límite horario.El valor predeterminado es 500000.  
  
### Para controlar la detección de reproducción en el servicio utilizando código  
  
1.  Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> para utilizar en <xref:System.ServiceModel.Channels.CustomBinding>.  
  
2.  Utilice la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> para devolver una referencia a la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> y establezca las propiedades como descrito previamente.  
  
### Para controlar la detección de reproducción en configuración para el cliente o servicio  
  
1.  Cree un objeto [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2.  Cree un elemento `<security>`.  
  
3.  Cree [\<localClientSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) o [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).  
  
4.  Establezca los siguientes valores de atributo según sea apropiado: `detectReplays`, `maxClockSkew`, `replayWindow`, y `replayCacheSize`.El ejemplo siguiente establece los atributos de `<localServiceSettings>``<localClientSettings> y un elemento` :  
  
    ```  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## Ejemplo  
 El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mediante el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> y establece las propiedades de reproducción del enlace.  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## Ámbito de reproducción: Solo seguridad del mensaje  
 Observe que los procedimientos siguientes solo se aplican al modo de seguridad de los mensajes.Para Transporte y Transporte con modos de credencial de mensaje, los mecanismos de transporte detectan las reproducciones.  
  
## Notas de conversación seguras  
 Para los enlaces que habilitan las conversaciones seguras, puede ajustar estos valores tanto para la aplicación como para el enlace de arranque de conversación segura.Por ejemplo, se pueden desactivar las reproducciones para el canal de la aplicación pero habilitarlas para el canal de arranque que establece la conversación segura.  
  
 Si no utiliza las sesiones de conversación seguras, la detección de reproducción no garantiza la detección de reproducciones en escenarios de granja de servidores y cuando se recicla el proceso.Esto se aplica a los enlaces siguientes proporcionados por el sistema:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>.  
  
-   <xref:System.ServiceModel.WSHttpBinding> con la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> establecida en `false`.  
  
## Compilar el código  
  
-   Los espacios de nombres siguientes son necesarios para compilar el código:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
## Vea también  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>   
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 [Conversaciones y sesiones seguras](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)   
 [\<localClientSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)