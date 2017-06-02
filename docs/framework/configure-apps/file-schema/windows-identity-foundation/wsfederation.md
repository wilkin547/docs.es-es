---
title: "&lt;wsFederation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;wsFederation&gt;
Descripción  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
        freshness=xs:decimal  
        homerealm=xs:string (URI)  
        issuer=xs:string (URI)  
        persistentCookiesOnPassiveRedirects=xs:boolean  
        passiveRedirectEnabled=xs:boolean  
        policy=xs:string (URI)  
        realm=xs:string (URI)  
        reply=xs:string (URI)  
        request=xs:string (URI)  
        requestPtr=xs:string (URI)  
        requireHttps=xs:boolean  
        resource=xs:string (URI)  
        signInQueryString=xs:string  
        signOutQueryString=xs:string  
        signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|authenticationType|URI que especifica el tipo de autenticación.  Establece el parámetro de wauth de solicitud de inicio de sesión de WS\-Federation.  Opcional.  El valor predeterminado es una cadena vacía, que especifica que el parámetro wauth no está incluido en la solicitud.|  
|frescura|La edad máxima de que desee de las solicitudes de autenticación, en minutos.  Establece el parámetro de wfresh de solicitud de inicio de sesión de WS\-Federation.  Opcional.  El valor predeterminado es cero.  Opcional. **Warning:**  En la próxima versión de.NET Framework 4.5, el `freshness` atributo será del tipo `xs:string` y su valor predeterminado es `null`.|  
|homeRealm|El territorio principal del proveedor de identidad \(IP\) para autenticación.  Establece el parámetro de horas de servicio de inicio de sesión de la solicitud de WS\-Federation.  Opcional.  El valor predeterminado es una cadena vacía, que especifica que el parámetro de horas de servicio no está incluido en la solicitud.|  
|emisor|El URI del emisor de símbolo \(token\) deseado.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.|  
|Atributo|Descripción  Opcional.  type|  
|passiveRedirectEnabled|Especifica si la WSFAM está habilitada para redirigir automáticamente las solicitudes no autorizadas a un STS.  Opcional.  None|  
|policy|Elemento  El valor predeterminado es una cadena vacía.  Descripción  Opcional.  El valor predeterminado es una cadena vacía, que especifica que el parámetro de elemento Web no está incluido en la solicitud.|  
|realm|El URI del territorio que solicita.  \(Un identificador URI que identifica la parte que confía \(RP\) para el servicio de token de seguridad \(STS\).\) Establece el parámetro de solicitud de solicitud wtrealm en el signo de WS\-Federation.  Obligatorio.|  
|reply|Una dirección URL que identifica la dirección a la que desea que la aplicación de terceros \(RP\) confía recibir las respuestas desde el servicio de tokens de seguridad \(STS\).  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Opcional.  Atributo|  
|request|Descripción  type  Opcional.  Tipo de notificación.  No incluya el wreq o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de símbolo \(token\) para emitir.|  
|Obligatorio.|optional  Establece el parámetro de wreqptr de la solicitud.  Opcional.  Opcional.  None|  
|Elemento|Descripción  Opcional.  El valor predeterminado es "true", se debe utilizar HTTPS.|  
|recurso|Un identificador URI que identifica el recurso que se tiene acceso, la parte que confía \(RP\), en el que el servicio de token de seguridad \(STS\).  Opcional.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Opcional.  Atributo **Note:**  Descripción  authenticationType|  
|signInQueryString|Proporciona un punto de extensibilidad para especificar los parámetros de consulta de aplicación definida en la dirección URL de solicitud de inicio de sesión de WS\-Federation.  Opcional.  Opcional.  Los parámetros se especifican como un fragmento de la cadena de consulta de la siguiente forma: `“param1=value1&param2=value2&param3=value3”` y así sucesivamente. **Note:**  En un archivo de configuración de la "&" caracteres en la cadena de consulta deben especificarse con su referencia de entidad, `&`.|  
|signOutQueryString|Proporciona un punto de extensibilidad para especificar los parámetros de consulta de aplicación definida en la dirección URL de solicitud de inicio de sesión de WS\-Federation.  Opcional.  Opcional.  El valor predeterminado es cero. **Note:**  Opcional.|  
|signOutReply|Especifica la dirección URL a la que se debe redirigir el cliente por el servicio de token de seguridad \(STS\) durante el cierre de sesión a través del protocolo WS\-Federation pasivo.  Establece el parámetro wreply en una solicitud de cierre de sesión de WS\-Federation.  Opcional.  El valor predeterminado es una cadena vacía, que especifica que no hay parámetros adicionales deben incluirse en la solicitud.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Opcional.|  
  
## Comentarios  
 Puede utilizar el `<wsFederation>` elemento para configurar parámetros de configuración de WS\-Federation de predeterminados y comportamiento predeterminado para el WSFAM.  emisor  Estas propiedades se mantienen para cada solicitud emitida por el WSFAM.  Puede cambiar los parámetros de WS\-Federation dinámicamente durante la solicitud de procesamiento mediante la adición de controladores de eventos para los eventos expuestos por WSFAM; Por ejemplo, la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> evento.  Para obtener más información, vea la documentación de la clase <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
 El `<wsFederation>` elemento está representado por el <xref:System.IdentityModel.Services.Configuration.WSFederationElement> clase.  El propio objeto de configuración está representado por el <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> clase.  Opcional.  
  
## Ejemplo  
 El XML siguiente se muestra un `<wsFederation>` elemento que especifica la configuración de la WSFAM.  
  
> [!WARNING]
>  En este ejemplo, el WSFAM no es necesario para utilizar HTTPS.  Esto es debido a que la `requireHttps` de atributo en el `<wsFederation>` se establece el elemento `false`.  Opcional.  
  
```  
<wsFederation passiveRedirectEnabled="true"   
  issuer="http://localhost:15839/wsFederationSTS/Issue"   
  realm="http://localhost:50969/"   
  reply="http://localhost:50969/"   
  requireHttps="false"   
  signOutReply="http://localhost:50969/SignedOutPage.html"   
  signOutQueryString="Param1=value2&Param2=value2"   
  persistentCookiesOnPassiveRedirects="true" />  
  
```  
  
## Vea también  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>