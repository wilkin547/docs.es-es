---
title: "Protecci&#243;n de mensajes dentro de sesiones confiables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Protecci&#243;n de mensajes dentro de sesiones confiables
En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.Puede habilitar una sesión confiable y segura de manera imperativa mediante código o de manera declarativa mediante configuración.Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.  
  
 Este procedimiento está compuesto por tres tareas clave:  
  
1.  Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.  
  
2.  Requiera la seguridad de mensajes dentro de la sesión confiable.  
  
3.  Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.  
  
 Es importante en la primera tarea que el elemento de configuración del extremo contenga un atributo `bindingConfiguration` que haga referencia a una configuración de enlace denominada \(en este ejemplo\) "MessageSecurity". El elemento de configuración [\<enlace\>](../../../../docs/framework/misc/binding.md)`enabled puede hacer referencia a continuación a este nombre para habilitar las sesiones confiables estableciendo el atributo` [reliableSession del elemento](http://msdn.microsoft.com/es-es/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)`true en` .Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.  
  
 Para ver la copia del origen del ejemplo en el que se basa este procedimiento de configuración, vea [Sesión de confianza de WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).  
  
 Los elementos esenciales de la segunda tarea se logran estableciendo el atributo `mode` del elemento \<`security`\> contenido en el elemento \<`binding`\> del cliente y servicio en `Message`.  
  
 Los elementos esenciales de la tercera tarea se logran estableciendo el atributo `clientCredentialType` del elemento \<`message`\> contenido en el elemento \<`security`\> del cliente y servicio en `Certificate`.  
  
> [!NOTE]
>  Al utilizar el modo de seguridad con sesiones confiables, si no se autentica el cliente, la mensajería confiable intenta autenticar el cliente hasta que se supere un tiempo de espera en lugar de producir una excepción tras el primer error.  
  
### Configuración del servicio con WSHttpBinding para utilizar una sesión confiable  
  
1.  Este procedimiento se describe en [Intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).  
  
### Configuración del cliente con un WSHttpBinding para utilizar una sesión confiable  
  
1.  Este procedimiento se describe en [Intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).  
  
### Establecimiento del modo y de la propiedad ClientCredentialType mediante configuración  
  
1.  Agregue un elemento de enlace apropiado al elemento [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración.El siguiente ejemplo agrega un elemento [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
2.  Agregue un elemento \<`binding`\> y defina su atributo `name` en un valor adecuado.  
  
3.  Agregue un elemento `<security>``mode y establezca el atributo` `Message en` .  
  
     El siguiente ejemplo establece el modo en “`Message`, y, a continuación, establece el atributo `clientCredentialType` del \<`message`\> en “`Certificate`.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = " Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```