---
title: "C&#243;mo: Establecer un sesgo de reloj m&#225;ximo | Microsoft Docs"
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
  - "Propiedad MaxClockSkew"
  - "WCF, enlaces personalizados"
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo: Establecer un sesgo de reloj m&#225;ximo
Las funciones críticas en el tiempo se pueden desbaratar si los ajustes del reloj en dos equipos son diferentes.  Para mitigar esta posibilidad, puede establecer la propiedad `MaxClockSkew` en <xref:System.TimeSpan>.  Esta propiedad está disponible en dos clases:  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  Importante   Para una conversación segura, los cambios en la propiedad `MaxClockSkew` se deben realizar cuando el servicio o cliente se arranca.  Para ello, debe establecer la propiedad en el objeto <xref:System.ServiceModel.Channels.SecurityBindingElement> devuelto por <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.  
  
 Para cambiar la propiedad en uno de los enlaces proporcionados por el sistema, debe encontrar el elemento de enlace de seguridad en la colección de enlaces y establecer la propiedad `MaxClockSkew` en un nuevo valor.  Dos clases derivan de <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.  Al recuperar el enlace de seguridad de la colección, debe convertir a uno de estos tipos para establecer correctamente la propiedad `MaxClockSkew`.  El siguiente ejemplo usa un <xref:System.ServiceModel.WSHttpBinding>, que utiliza el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  Para obtener una lista que especifica qué tipo de enlace de seguridad utilizar en cada enlace proporcionado por el sistema, consulte [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
### Para crear un enlace personalizado con un nuevo valor de sesgo de reloj en código  
  
1.  > [!WARNING]
    >  Nota: Agregue referencias a los espacios de nombres siguientes en el código: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions> y <xref:System.ServiceModel.Security.Tokens>.  
  
     Cree una instancia de una clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode>.  
  
2.  Cree una nueva instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> llamando al método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3.  Utilice el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> para encontrar el elemento del enlace de seguridad.  
  
4.  Al utilizar el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, convierta al tipo real.  El ejemplo siguiente convierte al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5.  Establezca la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> en el elemento del enlace de seguridad.  
  
6.  Cree un <xref:System.ServiceModel.ServiceHost> con un tipo de servicio y dirección base adecuados.  
  
7.  Utilice el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> para agregar un extremo e incluir el <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### Para establecer MaxClockSkew en la configuración  
  
1.  Cree un elemento [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) en la sección del elemento [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
2.  Cree un elemento [\<enlace\>](../../../../docs/framework/misc/binding.md) y establezca el atributo `name` en un valor adecuado.  El siguiente ejemplo lo define en `MaxClockSkewBinding`.  
  
3.  Agregue un elemento de codificación.  El siguiente ejemplo agrega un elemento [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4.  Agregue un elemento [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) y establezca el atributo `authenticationMode` en un valor adecuado.  El siguiente ejemplo establece el atributo en `Kerberos` para especificar que el servicio usa autenticación de Windows.  
  
5.  Agregue un elemento [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el atributo `maxClockSkew` en un valor con la forma de `"##:##:##"`.  El siguiente ejemplo lo establece en 7 minutos.  De manera opcional, agregue un elemento [\<localServiceSettings\>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el atributo `maxClockSkew` en un valor adecuado.  
  
6.  Agregue un elemento de transporte.  En el ejemplo siguiente se usa un elemento [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7.  Para una conversación segura, la configuración de seguridad se debe producir en la programación previa del elemento [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md).  
  
    ```  
  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    ```  
  
## Vea también  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>   
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)