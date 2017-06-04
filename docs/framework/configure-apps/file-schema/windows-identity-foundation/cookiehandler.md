---
title: "&lt;cookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;cookieHandler&gt;
El valor predeterminado es una cadena vacía.  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Especifica el nombre base para cualquier cookie escrito.  Opcional.|  
|ruta de acceso|Especifica el valor de ruta de acceso para cualquier cookie escrito.  realm|  
|mode|Uno de los <xref:System.IdentityModel.Services.CookieHandlerMode> los valores que especifica el tipo de controlador de la cookie utilizada por el SAM.  Podrán utilizarse los siguientes valores:<br /><br /> -   "Predeterminado": el mismo que "Chunked".<br />-   Obligatorio.  reply  Para ello "fragmentación" potencialmente una cookie lógica en un número de cookies en el cable.<br />-   "Personalizado", se utiliza una instancia de una clase personalizada derivada de <xref:System.IdentityModel.Services.CookieHandler>.  Opcional.<br /><br /> El valor predeterminado es "Predeterminado".|  
|request|Especifica la duración de las sesiones persistentes.  Si es cero, siempre se utilizan las sesiones transitorias.  Opcional.  El valor máximo es "365:0:0", que especifica una sesión de 365 días.  El valor debe especificarse con arreglo a la siguiente restricción: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, donde el valor de la izquierda especifica días, el valor medio \(si está presente\) especifica horas y el valor de la derecha \(si existe\) especifica los minutos.|  
|requireSsl|Especifica si el indicador "Secure" se emite para cualquier cookie escrito.  Si se establece este valor, las cookies de sesión de inicio de sesión sólo estará disponibles a través de HTTPS.  Opcional.|  
|hideFromScript|Controla si el indicador "HttpOnly" se emite para cualquier cookie escrito.  Algunos exploradores web respetan este indicador al mantener secuencias de comandos de cliente de acceso al valor de cookie.  El valor predeterminado es "true".|  
|domain|Opcional.  El valor predeterminado es "".|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<chunkedCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|recurso  Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Predeterminado" o "Segmentado".|  
|[\<customCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Opcional.  Este elemento debe estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom".  Opcional.  El tipo personalizado debe derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene las opciones que configurar el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Comentarios  
 El <xref:System.IdentityModel.Services.CookieHandler> es responsable de nivel de protocolo de lectura y escritura sin procesar cookies HTTP.  Puede configurar un <xref:System.IdentityModel.Services.ChunkedCookieHandler> o un controlador de cookie personalizado derivado de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 Para configurar un controlador de cookie fragmentada, establezca el atributo mode a "Chunked" o "Default".  Opcional.  
  
 Para configurar un controlador de cookie personalizado, establezca el atributo mode a "Personalizado".  También debe especificar un `<customCookieHandler>` elemento secundario que hace referencia al tipo de su controlador personalizado.  
  
 El `<cookieHandler>` elemento está representado por el <xref:System.IdentityModel.Services.CookieHandlerElement> clase.  El controlador de cookie que se ha especificado en la configuración está disponible desde el <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> propiedad de la <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto establecido en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> propiedad.  
  
## Ejemplo  
 El XML siguiente se muestra un `<cookieHandler>` elemento.  Opcional.  Se trata de una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase.  Debido a que la `<chunkedCookieHandler>` no se especifica el elemento secundario, se utilizará el tamaño del fragmento predeterminado.  HTTPS no será necesario porque el `requireSsl` se establece el atributo `false`.  
  
> [!WARNING]
>  En este ejemplo, HTTPS no es necesario escribir las cookies de sesión.  Esto es debido a que la `requireSsl` de atributo en el `<cookieHandler>` elemento está establecido en `false`.  Esta configuración no se recomienda para la mayoría de los entornos de producción ya que puede presentar un riesgo de seguridad.  
  
```  
<cookieHandler requireSsl="false" />  
```  
  
## Vea también  
 <xref:System.IdentityModel.Services.CookieHandler>   
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>